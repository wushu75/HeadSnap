# HeadSnap AI — Privacy Policy

**Effective Date:** July 23, 2026

## Our Promise

**HeadSnap AI processes everything locally in your browser.** Your photos never leave your device. Period.

## What We Collect

### By Default: Nothing
- No photos uploaded to any server
- No account required
- No email, name, or phone number collected
- No cookies or tracking pixels
- No device fingerprinting

### With Your Consent (Opt-In Analytics)
If you explicitly enable analytics in Settings:
- Anonymous feature usage (e.g., "generate button clicked")
- Performance metrics (generation time, model load time)
- Error types (no error messages or stack traces)
- Hardware capability (WebGPU support: yes/no)

**What we NEVER collect even with analytics:**
- Your photos or any image data
- Facial features or biometric data
- Browsing history
- Personally identifiable information

## Data Storage

| Data | Location | Duration |
|------|----------|----------|
| Uploaded selfies | Browser memory only | Until popup closes |
| Generated headshots | `chrome.storage.local` | Until you delete them |
| AI models | Browser Cache API | Until cache cleared |
| Settings | `chrome.storage.local` | Until extension removed |

## Third Parties

We use these services **only for model downloads**:
- **Hugging Face** — ONNX model files (no personal data transmitted)
- **jsDelivr CDN** — ONNX Runtime WASM files (no personal data transmitted)

No other third-party services are contacted.

## Your Rights

- **Delete everything:** Clear cache in Settings → Clear Cache
- **Remove extension:** Uninstalling deletes all stored data
- **Opt out:** Disable analytics anytime in Settings
- **Export data:** All your headshots are PNG files you own

## Contact

Questions? [team@headsnap.ai](mailto:team@headsnap.ai)

---

*This policy is open source — view the code to verify every claim.*
