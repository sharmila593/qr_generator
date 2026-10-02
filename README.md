# qr_generator


A single-file, browser-based QR code generator with support for multiple content types, custom styling, logo embedding, and export to PNG/SVG. No build step, no backend — just open the HTML file.

## Features

- **Multiple content types**
  - Plain text / URL
  - Wi-Fi network (SSID, password, security type) — scan to auto-connect
  - Contact card (vCard) — scan to save to contacts
  - Email (prefilled "to", subject, body)
  - Phone number
- **Styling** — custom module color, background color, size, and error-correction level (L/M/Q/H)
- **Logo embedding** — place a center logo on the code (use error correction level Q or H so it still scans reliably)
- **Export** — download as PNG or SVG
- **History** — recently generated codes are saved locally in your browser for quick re-use

## Getting started

1. Download `index.html` (or `qr-generator.html`).
2. Open it in any modern browser — Chrome, Firefox, Safari, Edge.
3. Pick a content type, fill in the fields, and the preview updates live.
4. Adjust colors, size, and error correction as needed.
5. Click **Download PNG** or **Download SVG** to save the code.

No installation, dependencies to manage, or server required.

## Project structure

```
qr-forge/
└── index.html   # entire app: markup, styles, and logic in one file
```

## How it works

QR encoding is handled client-side by the [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) library (loaded from a CDN). The generated modules are drawn onto an HTML `<canvas>` for the live preview and PNG export, and the same module data is used to build an SVG for vector export.

History is stored in your browser's `localStorage`, so it's private to your device and isn't sent anywhere.

## Browser support

Works in any modern browser with Canvas and `localStorage` support. An internet connection is needed on first load to fetch the QR encoding library from the CDN.

## License

Free to use, modify, and distribute.
