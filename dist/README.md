# dist/ — Build Output

This directory contains the packaged Chrome Extension ready for the Chrome Web Store.

## Contents (after `npm run build`)

```
dist/
├── manifest.json
├── popup.html
├── icons/
│   ├── icon16.png
│   ├── icon48.png
│   └── icon128.png
├── src/
│   ├── js/
│   ├── css/
│   ├── models/
│   ├── utils/
│   └── _locales/
└── HeadSnap-v1.0.0.zip   ← Chrome Web Store upload package
```

## Chrome Web Store Submission

1. Go to [Chrome Web Store Developer Dashboard](https://chrome.google.com/webstore/devconsole/)
2. Click "New Item"
3. Upload `HeadSnap-v1.0.0.zip`
4. Fill in store listing details
5. Submit for review

## Store Listing Checklist

- [ ] Icon (128×128 PNG)
- [ ] Screenshots (1280×800, at least 3)
- [ ] Promotional images (440×280 small, 920×680 large, 1400×560 marquee)
- [ ] Description (max 1000 chars)
- [ ] Privacy policy URL (link to docs/PRIVACY.md)
- [ ] Category: "Photos" or "Productivity"
- [ ] Language: English (primary)
