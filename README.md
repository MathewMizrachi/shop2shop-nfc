# Shop2Shop NFC — Universal Links Host

Static site hosted on GitHub Pages that serves the Apple App Site Association (AASA) file for iOS Universal Links.

## What it does

When an iPhone reads an NFC tag with a Shop2Shop payment URL (`https://mathewmizrachi.github.io/shop2shop-nfc/pay?...`), iOS checks the AASA file at `.well-known/apple-app-site-association` to determine which app should handle the link.

## Setup

1. Push this repo to `mathewmizrachi/shop2shop-nfc` on GitHub
2. Go to **Settings → Pages** and enable GitHub Pages on the `main` branch
3. Replace `TEAMID` in `.well-known/apple-app-site-association` with your actual Apple Developer Team ID

## File structure

```
.well-known/apple-app-site-association  — AASA file for iOS Universal Links
_config.yml                             — Jekyll config (ensures .well-known is served)
index.html                              — Fallback page for browser visits
```

## Verification

After deploying, confirm the AASA file is accessible:

```
curl https://mathewmizrachi.github.io/shop2shop-nfc/.well-known/apple-app-site-association
```

The response should return the JSON with `Content-Type: application/json`.
