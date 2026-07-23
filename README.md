<div align="center">

<img src="icons/icon128.svg" width="96" height="96" alt="HeadSnap AI Logo">

# HeadSnap AI

### Selfies to Studio Headshots. 100% Free. Private. Instant.

[![Chrome Web Store](https://img.shields.io/badge/Chrome_Web_Store-Coming_Soon-4285F4?logo=googlechrome&logoColor=white)](https://chrome.google.com/webstore)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/wushu75/HeadSnap?style=social)](https://github.com/wushu75/HeadSnap/stargazers)
[![Contributors](https://img.shields.io/github/contributors/wushu75/HeadSnap)](https://github.com/wushu75/HeadSnap/graphs/contributors)
[![WebGPU](https://img.shields.io/badge/WebGPU-Supported-76B900?logo=webgpu)](https://webgpu.io)
[![Transformers.js](https://img.shields.io/badge/Transformers.js-v3-FF6F00?logo=huggingface)](https://huggingface.co/docs/transformers.js)

</div>

---

## 🚀 What is HeadSnap AI?

**HeadSnap AI** is a **100% free, open-source, browser-native AI headshot generator** that runs entirely on your device. No cloud uploads. No subscriptions. No privacy concerns.

Upload 1–3 selfies, pick a style, and get professional studio-quality headshots in seconds — powered by **WebGPU** and **Stable Diffusion** running locally in your browser.


---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📸 **1-Click Upload** | Drag & drop 1–3 selfies. Supports JPG, PNG, WebP. |
| 🎨 **Style Presets** | LinkedIn Pro, Executive, Creative, Casual — instant professional looks. |
| 🖼️ **Smart Backgrounds** | Studio gray, pure white, soft gradient, or bokeh blur. |
| ✨ **AI Retouching** | Skin smoothing, teeth whitening, eye enhancement — all local. |
| 🔍 **AI Upscale** | 1x–4x super-resolution for print-ready quality. |
| 🔒 **100% Private** | Your photos never leave your device. No servers, no uploads. |
| ⚡ **WebGPU Accelerated** | GPU inference for ~1–3 second generation on modern hardware. |
| 📤 **One-Click Share** | Built-in X/Twitter and LinkedIn sharing with auto-captions + `#HeadSnap`. |
| 🔄 **Before/After Generator** | Create viral social comparison posts in one click. |
| 🗂️ **Local Gallery** | All your headshots saved locally, organized by date. |
| ☁️ **Cloud Fallback** | Optional cloud GPU for older devices (opt-in, privacy-preserving). |

---

## 🖼️ Screenshots

> *Placeholder — replace with actual screenshots before Chrome Web Store submission*

| Upload | Styles | Results | Share |
|--------|--------|---------|-------|
| ![Upload](assets/screenshots/upload-placeholder.png) | ![Styles](assets/screenshots/styles-placeholder.png) | ![Results](assets/screenshots/results-placeholder.png) | ![Share](assets/screenshots/share-placeholder.png) |

---

## 🛠️ Tech Stack

```
┌─────────────────────────────────────────────────────────────┐
│  HeadSnap AI Architecture                                   │
├─────────────────────────────────────────────────────────────┤
│  Frontend    │  Vanilla JS + CSS (no framework bloat)       │
│  Extension   │  Chrome Extension Manifest V3                │
│  AI Engine   │  Transformers.js + ONNX Runtime Web          │
│  GPU Backend │  WebGPU (fallback: WASM CPU)                 │
│  Models      │  Stable Diffusion Turbo (ONNX, quantized)  │
│  Storage     │  chrome.storage.local + Cache API            │
│  Analytics   │  Opt-in, anonymous, privacy-first            │
└─────────────────────────────────────────────────────────────┘
```

- **[Transformers.js](https://huggingface.co/docs/transformers.js)** — Run Hugging Face models in the browser
- **[ONNX Runtime Web](https://onnxruntime.ai/docs/tutorials/web/)** — Cross-platform ML inference with WebGPU acceleration
- **[WebGPU](https://webgpu.io)** — Modern GPU compute API for the web
- **[Stable Diffusion Turbo](https://huggingface.co/stabilityai/sd-turbo)** — One-step image generation

---

## 📦 Installation

### From Chrome Web Store *(Coming Soon)*

1. Visit the [Chrome Web Store page](https://chrome.google.com/webstore) *(link TBD)*
2. Click **"Add to Chrome"**
3. Pin the extension for quick access

### From Source (Developer Mode)

```bash
# 1. Clone the repo
git clone https://github.com/wushu75/HeadSnap.git
cd HeadSnap

# 2. Install dependencies
npm install

# 3. Build the extension
npm run build

# 4. Load in Chrome
#    - Open chrome://extensions/
#    - Enable "Developer mode"
#    - Click "Load unpacked"
#    - Select the `dist/` folder
```

### Prerequisites

- **Chrome 113+** or **Edge 113+** (WebGPU support)
- **~2GB free RAM** for model loading
- **GPU with WebGPU support** recommended (Intel Arc, NVIDIA RTX 20+, AMD RDNA2+)

---

## 🎯 Usage

1. **Click the HeadSnap icon** in your Chrome toolbar
2. **Upload 1–3 selfies** — drag & drop or click to browse
3. **Pick a style** — LinkedIn Pro, Executive, Creative, or Casual
4. **Customize** — choose background, toggle retouching, set upscale
5. **Click "Generate"** — wait 1–5 seconds
6. **Download or share** — one-click exports or social sharing

---

## 🏗️ Project Structure

```
HeadSnap/
├── manifest.json          # Extension manifest (V3)
├── popup.html             # Main popup UI
├── package.json           # Build scripts & dependencies
├── LICENSE                # MIT License
├── README.md              # This file
├── CONTRIBUTING.md        # Contribution guidelines
├── ROADMAP.md             # Product roadmap
├── icons/                 # Extension icons (SVG + PNG)
│   ├── icon16.svg
│   ├── icon48.svg
│   └── icon128.svg
├── src/
│   ├── js/
│   │   ├── popup.js       # Popup UI controller
│   │   ├── background.js  # Service worker
│   │   ├── inference.js   # WebGPU inference engine
│   │   ├── gallery.js     # Local gallery manager
│   │   ├── share.js       # Social sharing utilities
│   │   ├── offscreen.js   # Offscreen WebGPU document
│   │   └── offscreen.html # Offscreen document shell
│   ├── css/
│   │   └── popup.css      # Popup styles
│   ├── models/            # Local ONNX models (optional)
│   └── utils/
│       └── analytics.js   # Privacy-first analytics
├── docs/
│   ├── PRIVACY.md         # Privacy policy
│   └── ARCHITECTURE.md    # Technical deep-dive
├── assets/
│   └── screenshots/       # Store screenshots
└── dist/                  # Build output (generated)
```

---

## 🤝 Contributing

We love contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Quick Start for Contributors

```bash
# Fork & clone
git clone https://github.com/YOUR_USERNAME/HeadSnap.git
cd HeadSnap

# Install & dev
npm install
npm run dev        # Auto-reloads extension in Chrome

# Before submitting PR
npm run lint
npm test
```

### Areas We Need Help

- 🎨 **UI/UX Design** — Polish the popup interface
- 🤖 **Model Optimization** — Smaller/faster ONNX models
- 🌍 **Localization** — Translate to other languages
- 📱 **Mobile Support** — Optimize for mobile Chrome
- 🧪 **Testing** — Unit tests, E2E tests
- 📖 **Documentation** — Tutorials, blog posts

---

## 📋 Roadmap

See [ROADMAP.md](ROADMAP.md) for the full product roadmap.

### v1.0.0 (Current) — MVP
- [x] Basic selfie upload & generation
- [x] 4 style presets
- [x] WebGPU + WASM fallback
- [x] Local gallery & downloads
- [x] X/LinkedIn sharing

### v1.1.0 — Polish
- [ ] Batch generation (multiple styles at once)
- [ ] Custom prompt editing
- [ ] Face swap / identity preservation
- [ ] Dark mode


---

## 🔒 Privacy

**HeadSnap AI is privacy-first by design:**

- ✅ All inference runs **locally** in your browser
- ✅ Your photos **never leave your device**
- ✅ No account required, no email collected
- ✅ Analytics are **opt-in** and fully anonymous
- ✅ No tracking pixels, no cookies, no fingerprinting
- ✅ Open source — audit the code yourself

Read our full [Privacy Policy](docs/PRIVACY.md).

---

---

## 🙏 Acknowledgments

- [Hugging Face](https://huggingface.co) for Transformers.js and the model hub
- [Microsoft](https://microsoft.com) for ONNX Runtime Web
- [Stability AI](https://stability.ai) for Stable Diffusion
- The open-source community for making browser AI possible

---

<div align="center">

**Made with 💙 by the HeadSnap AI community**

[⭐ Star us on GitHub](https://github.com/wushu75/HeadSnap) • [🐛 Report Bug](https://github.com/wushu75/HeadSnap/issues) • [💡 Request Feature](https://github.com/wushu75/HeadSnap/issues)

`#HeadSnap` `#AIHeadshot` `#FreeAI` `#WebGPU` `#OpenSource`

</div>
