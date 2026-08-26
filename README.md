# README.md

# X4 Pro Lock Screen Converter

A simple browser-based tool for preparing custom lock-screen images for the **Xteink X4 Pro**, particularly when using **CrossInk**.

It converts ordinary images into a format that renders more reliably on the X4 Pro's e-ink display.

## Features

- Runs entirely in your browser
- Mobile friendly
- No server or installation required
- Supports multiple image uploads
- Resizes images to **480 × 800 px**
- Converts images to grayscale
- Applies **Floyd–Steinberg dithering**
- Exports **24-bit uncompressed BMP**
- Individual image preview and download
- Works as a single `index.html` file
- Ready for GitHub Pages

## Why?

The X4 Pro may render conventional grayscale lock-screen images poorly, with posterization, lost midtones, or excessive contrast.

This converter preprocesses the image as:

**Image → 480×800 → Grayscale → Floyd–Steinberg dithering → Black/White pixels → 24-bit BMP**

Instead of asking the e-ink display to reproduce intermediate gray values, apparent shades of gray are created using patterns of black and white pixels.

## Usage

1. Open the converter in your browser.
2. Upload one or more images.
3. Choose **Cover** or **Contain**.
4. Adjust brightness or contrast if needed.
5. Select **Process selected images**.
6. Preview the result.
7. Download the generated `.bmp` file.
8. Copy it to your X4 Pro for use as a lock/sleep screen.

## Default Output

| Setting | Value |
| --- | --- |
| Resolution | 480 × 800 px |
| Grayscale | Yes |
| Dithering | Floyd–Steinberg |
| Output pixels | Black / White |
| Format | BMP |
| Color depth | 24-bit |
| Compression | None |

## Privacy

All processing happens **locally in your browser**.

Your images are not uploaded to a server.

## Deployment

The application is contained entirely in:

`index.html`

It can be hosted directly using **GitHub Pages** with no backend or build process.

## License

Released under the **MIT License**.

## Disclaimer

This is an independent project and is not affiliated with or endorsed by Xteink or CrossInk.

E-ink rendering may vary depending on firmware version, refresh mode, display waveform, and image content.
```
