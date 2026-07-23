# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| 1.0.x   | ✅ Yes |
| < 1.0   | ❌ No   |

## Reporting a Vulnerability

If you discover a security vulnerability in HeadSnap AI, please follow these steps:

1. **Do NOT** open a public GitHub issue
2. Email [security@headsnap.ai](mailto:security@headsnap.ai) with:
   - Description of the vulnerability
   - Steps to reproduce
   - Potential impact assessment
   - Suggested fix (if any)

## Response Timeline

- **Acknowledgment:** Within 48 hours
- **Initial assessment:** Within 7 days
- **Fix released:** Within 30 days (critical), 60 days (high), 90 days (medium/low)
- **Public disclosure:** After fix is released and users have had time to update

## Security Measures

- All code is open source and auditable
- No external network requests with user data
- CSP restricts script execution to extension origin only
- WASM execution is sandboxed by the browser
- Model files are verified via checksum before loading

## Known Limitations

- WebGPU shaders execute on the GPU with the same privileges as the browser process
- Large model files (~1-2GB) are downloaded from Hugging Face; use SRI or local models for air-gapped environments
- `wasm-unsafe-eval` CSP directive is required for ONNX Runtime Web
