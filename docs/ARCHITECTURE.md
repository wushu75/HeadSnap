# HeadSnap AI — Technical Architecture

## System Overview

```
┌─────────────────────────────────────────────────────────────┐
│                      Chrome Browser                         │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐  │
│  │   Popup UI  │  │   Service   │  │  Offscreen Document│  │
│  │  (popup.js) │  │   Worker    │  │   (offscreen.js)   │  │
│  │             │  │(background.js)│  │                    │  │
│  │ • Upload    │  │             │  │ • WebGPU access    │  │
│  │ • Styles    │  │ • Cache mgmt│  │ • ONNX inference   │  │
│  │ • Gallery   │  │ • Analytics │  │ • Model execution  │  │
│  │ • Share     │  │ • Context   │  │                    │  │
│  │             │  │   menus     │  │                    │  │
│  └──────┬──────┘  └──────┬──────┘  └────────────────────┘  │
│         │                │                ▲                  │
│         └────────────────┴────────────────┘                  │
│              chrome.runtime messaging                        │
└─────────────────────────────────────────────────────────────┘
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
            ┌──────────────┐   ┌──────────────┐
            │  HuggingFace  │   │   jsDelivr   │
            │  Model Hub    │   │   CDN        │
            │  (ONNX files) │   │  (WASM bins) │
            └──────────────┘   └──────────────┘
```

## Key Design Decisions

### 1. Manifest V3 + Offscreen Document
WebGPU is unavailable in service workers. We use `chrome.offscreen` API to create a hidden document where WebGPU inference runs.

### 2. Transformers.js + ONNX Runtime Web
- Transformers.js provides the high-level pipeline API
- ONNX Runtime Web handles the low-level tensor operations
- WebGPU execution provider for GPU acceleration
- WASM fallback for CPU-only devices

### 3. Model Strategy
| Model | Purpose | Size | Source |
|-------|---------|------|--------|
| SD Turbo ONNX | Fast generation | ~1.5GB | `onnx-community/Stable-Diffusion-Turbo-ONNX` |
| SD 1.5 ONNX | Quality generation | ~2GB | `onnx-community/Stable-Diffusion-1.5-ONNX` |
| CodeFormer ONNX | Face enhancement | ~300MB | `onnx-community/CodeFormer-ONNX` |

### 4. Privacy Architecture
- All image processing in `OffscreenCanvas` or `createImageBitmap`
- No `fetch()` calls with image data
- No `FormData` or multipart uploads
- `chrome.storage.local` (not sync) for persistence

## Performance Targets

| Metric | WebGPU (RTX 3060) | WASM (M1 CPU) |
|--------|-------------------|---------------|
| Model load | 3-5s | 8-12s |
| Generation | 1-2s | 5-10s |
| Memory peak | 3GB | 2GB |

## Security Considerations

- CSP: `script-src 'self' 'wasm-unsafe-eval'` — required for WASM
- No `eval()`, no inline scripts
- All external resources from trusted CDNs with SRI
- Model validation before execution
