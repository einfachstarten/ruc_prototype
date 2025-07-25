# ADAC OEM Data Consent Prototype

This repository contains a single–page prototype of a progressive web app (PWA) that demonstrates a possible workflow for obtaining customer consent to transfer vehicle data to ADAC. The prototype is entirely self‑contained in `index.html` and does not depend on any external backend services.

## Features

1. **VIN Capture and Decoder**
   - Users can scan the Vehicle Identification Number (VIN) with their device camera.
   - OCR is performed via [Tesseract.js](https://github.com/naptha/tesseract.js).
   - Manual VIN entry is also supported.
   - The file includes a simplified VIN decoder with manufacturer, country, region and model year lookups.
2. **System Verification**
   - After a VIN is recognised, the system runs a short “compatibility check” animation.
3. **Member Login (Prototype Only)**
   - Step four simulates an ADAC member login.
   - The demo accepts the credentials `1234567` / `pass1234`.
4. **Consent Confirmation**
   - Users grant consent to transmit diagnostic data.
   - A reference number is generated for confirmation.
5. **PWA Capabilities**
   - A service worker is injected at runtime to enable offline support and caching.
   - An install prompt allows the app to be added to the device home screen.

## Development

The project consists of only two files:

- `index.html` – the complete application, including CSS and JavaScript.
- `README.md` – documentation.

To try the prototype locally, simply open `index.html` in a modern browser with camera access enabled. When testing on a smartphone, you can add it to your home screen to experience the app-like behaviour.

### Customisation

- Update the base64-encoded manifest inside `index.html` if you need to change icons or names.
- The VIN database and decoding rules are defined in JavaScript blocks beginning around line 1230.
- Service-worker logic starts near line 1916 and can be extended with additional caching rules.

## Disclaimer

This repository is intended for demonstration and experimentation purposes. It does not implement any real authentication or backend connectivity and should not be used as-is in production.
