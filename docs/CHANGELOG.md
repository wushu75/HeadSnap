# Changelog

All notable changes to HeadSnap AI will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Initial Chrome Extension Manifest V3
- WebGPU inference with WASM fallback
- 4 style presets: LinkedIn Pro, Executive, Creative, Casual
- Background options: Studio Gray, Pure White, Soft Gradient, Bokeh
- AI retouching: Skin smoothing, Teeth whitening, Eye enhancement
- 1x–4x upscaling
- Local gallery with chrome.storage
- Social sharing: X/Twitter, LinkedIn, Clipboard
- Before/After generator for viral posts
- Privacy-first opt-in analytics
- Settings panel with WebGPU toggle
- Content script for LinkedIn integration
- i18n support (English)
- GitHub Actions CI/CD

### Security
- CSP with wasm-unsafe-eval for ONNX Runtime
- No external data transmission without explicit consent

## [1.0.0] - 2026-07-23

### Added
- Initial release
- All features listed in Unreleased

---

[Unreleased]: https://github.com/wushu75/HeadSnap/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/wushu75/HeadSnap/releases/tag/v1.0.0
