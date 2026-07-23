# Contributing to HeadSnap AI

First off, thank you for considering contributing to HeadSnap AI! 🎉

We believe that **everyone deserves a professional headshot** — and that building it should be a collaborative, open effort. Whether you're fixing a bug, adding a feature, improving docs, or sharing the project, you're helping democratize AI-powered photography.

---

## 🚀 Quick Start

1. **Fork** the repository on GitHub
2. **Clone** your fork locally
3. **Install** dependencies: `npm install`
4. **Create** a branch: `git checkout -b feature/your-feature-name`
5. **Make** your changes
6. **Test** thoroughly
7. **Submit** a Pull Request

---

## 📋 Development Setup

### Prerequisites

- Node.js 18+
- Chrome 113+ (for WebGPU testing)
- Git

### Local Development

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/HeadSnap.git
cd HeadSnap

# Install dependencies
npm install

# Run in development mode (auto-reload)
npm run dev

# This opens Chrome with the extension loaded from dist/
# Make changes to src/ files and the extension will reload automatically
```

### Building for Production

```bash
npm run build
# Outputs: dist/HeadSnap-v1.0.0.zip
```

---

## 🧪 Testing

We use **Jest** for unit tests. Please write tests for new features.

```bash
# Run all tests
npm test

# Run tests in watch mode
npm test -- --watch

# Run with coverage
npm test -- --coverage
```

### Manual Testing Checklist

Before submitting a PR, please verify:

- [ ] Upload works with 1–3 images (JPG, PNG, WebP)
- [ ] All 4 style presets generate successfully
- [ ] Background options apply correctly
- [ ] Retouching toggles work
- [ ] Upscale 1x–4x produces correct sizes
- [ ] Downloads work (single + all)
- [ ] Share buttons open correct platforms
- [ ] Gallery persists across sessions
- [ ] Settings save/load correctly
- [ ] WebGPU detection works (or falls back gracefully)
- [ ] No console errors in popup or background

---

## 🎨 Code Style

We use **ESLint** with a relaxed, readable config.

```bash
# Check code style
npm run lint

# Auto-fix issues
npm run lint -- --fix
```

### Style Guidelines

- Use **ES6+** syntax (async/await, modules, destructuring)
- Prefer **const** over **let**, avoid **var**
- Use **camelCase** for variables/functions, **PascalCase** for classes
- Write **JSDoc comments** for public APIs
- Keep functions **small and focused** (<50 lines when possible)
- Add **error handling** for all async operations
- Never log sensitive data (filenames are OK, image data is not)

---

## 🏷️ Commit Convention

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types:**
- `feat` — New feature
- `fix` — Bug fix
- `docs` — Documentation changes
- `style` — Code style (formatting, no logic change)
- `refactor` — Code refactoring
- `perf` — Performance improvement
- `test` — Adding or updating tests
- `chore` — Build process, dependencies, etc.

**Examples:**
```
feat(inference): add face enhancement pipeline
fix(ui): resolve gallery overflow on small screens
docs(readme): update installation instructions
perf(models): lazy-load ONNX models to reduce memory
```

---

## 🐛 Reporting Bugs

Before creating a bug report, please:

1. Check if the issue already exists
2. Try the latest version from the main branch
3. Test in a fresh Chrome profile (no other extensions)

**Bug report template:**

```markdown
**Description:**
A clear description of the bug.

**Steps to Reproduce:**
1. Go to '...'
2. Click on '...'
3. See error

**Expected Behavior:**
What you expected to happen.

**Actual Behavior:**
What actually happened.

**Screenshots:**
If applicable, add screenshots.

**Environment:**
- OS: [e.g., macOS 14, Windows 11]
- Chrome Version: [e.g., 120.0.6099.129]
- GPU: [e.g., NVIDIA RTX 3060, Apple M2]
- Extension Version: [e.g., 1.0.0]

**Console Errors:**
Paste any errors from the popup console or background service worker.
```

---

## 💡 Feature Requests

We love new ideas! When requesting a feature:

1. Check if it's already been requested
2. Explain the **use case** — who benefits and how?
3. Describe the **expected behavior**
4. If possible, include **mockups or wireframes**

Use the label `enhancement` for feature requests.

---

## 🔒 Security

If you discover a security vulnerability, **please do not open a public issue**.

Instead, email us at [security@headsnap.ai](mailto:security@headsnap.ai) with:
- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

We will respond within 48 hours and work with you to resolve the issue responsibly.

---

## 🌍 Translation & Localization

Want to help translate HeadSnap AI? We'd love that!

1. Check `src/_locales/` for existing translations
2. Create a new folder with your language code (e.g., `es`, `fr`, `de`)
3. Copy `messages.json` from `en/` and translate
4. Submit a PR

**Priority languages:** Spanish, French, German, Portuguese, Japanese, Korean, Chinese

---

## 🏆 Recognition

Contributors will be:
- Listed in our [CONTRIBUTORS.md](CONTRIBUTORS.md) file
- Mentioned in release notes
- Eligible for swag (stickers, t-shirts) after 3+ merged PRs

---

## 📜 Code of Conduct

This project adheres to a **Code of Conduct** adapted from the [Contributor Covenant](https://www.contributor-covenant.org/):

- Be respectful and inclusive
- Welcome newcomers and help them learn
- Focus on constructive feedback
- Respect different viewpoints and experiences

Harassment, trolling, or abusive behavior will not be tolerated.

---

## ❓ Questions?

- **Discord:** [Join our community](https://discord.gg/headsnap) *(coming soon)*
- **GitHub Discussions:** [Ask here](https://github.com/wushu75/HeadSnap/discussions)
- **Email:** [team@headsnap.ai](mailto:team@headsnap.ai)

---

Thank you for making HeadSnap AI better! 💙
