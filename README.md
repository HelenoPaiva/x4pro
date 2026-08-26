README.md
X4 Pro Lock Screen Converter

A simple browser-based image converter designed for preparing custom lock-screen images for the Xteink X4 Pro, particularly when using firmware such as CrossInk.

The app converts ordinary images into a format that renders more reliably on the X4 Pro's e-ink display.

Features
Runs entirely in the browser
No server or backend required
Mobile-friendly interface
Multiple image upload
Automatically resizes images to 480 × 800 px
Converts images to grayscale
Applies Floyd–Steinberg dithering
Produces strict black-and-white pixel data
Exports as 24-bit uncompressed BMP
Individual BMP downloads
Suitable for deployment with GitHub Pages
Why?

The X4 Pro can render ordinary grayscale lock-screen images poorly under some firmware configurations.

Images containing smooth gradients and intermediate gray levels may appear:

posterized
washed out
overly dark
lacking facial detail
poorly separated in the midtones

A reliable workaround is to perform the grayscale conversion and dithering before the image reaches the device.

This tool uses the following workflow:

Original image
      ↓
Resize / crop to 480 × 800
      ↓
Grayscale conversion
      ↓
Floyd–Steinberg dithering
      ↓
Black / white pixel image
      ↓
24-bit uncompressed BMP

Although the output BMP is stored as a 24-bit image, each pixel is either pure black or pure white. Apparent shades of gray are produced by dithering patterns rather than relying on the device's grayscale rendering.

Usage
Online

Open the GitHub Pages version of the project.

Select one or more images.
Choose the desired resize mode.
Adjust brightness or contrast if necessary.
Press Process selected images.
Preview the result.
Download the generated BMP.
Copy the BMP to the location used by your X4 Pro firmware for custom sleep or lock-screen images.
Default output

The default conversion settings are:

Setting	Value
Resolution	480 × 800 px
Color processing	Grayscale
Dithering	Floyd–Steinberg
Final pixel values	Black / White
File format	BMP
BMP depth	24-bit
Compression	None / BI_RGB

These defaults are intended specifically for reliable rendering on the X4 Pro.

Resize modes
Cover

The image fills the complete 480 × 800 frame.

Parts of the image may be cropped when its aspect ratio differs from the X4 Pro screen.

Contain

The complete image is preserved within the 480 × 800 frame.

White margins may be added when necessary.

Image processing

Grayscale luminance is calculated from the RGB image approximately as:

Y = 0.299R + 0.587G + 0.114B

The resulting grayscale image is then converted to black and white using Floyd–Steinberg error diffusion.

The quantization error is distributed to neighboring pixels using:

        X   7/16
3/16  5/16  1/16

This allows the high-resolution e-ink display to visually reproduce intermediate tones using patterns of black and white pixels.

Privacy

All processing occurs locally in your browser.

Images are not uploaded to a server by this application.

Opening the application through GitHub Pages only downloads the application itself. Image conversion is performed on the user's device using JavaScript and the HTML Canvas API.

Installation

No build process is required.

Clone or download the repository and open:

index.html

in a modern web browser.

For GitHub Pages:

Create a GitHub repository.
Add index.html.
Open Settings → Pages.
Select the repository branch as the deployment source.
Save.
Open the generated GitHub Pages URL.
Browser compatibility

The converter should work in current versions of major browsers including:

Chrome
Edge
Firefox
Safari
Mobile Safari
Chrome for Android

Image formats available for upload depend partly on browser support.

JPEG, PNG, WebP, and BMP should work on most modern browsers.

Limitations

This project is an independent utility and is not affiliated with or endorsed by Xteink or the developers of third-party X4 Pro firmware.

E-ink rendering can vary depending on:

firmware version
display waveform
refresh mode
display controller
image content

The default conversion settings were chosen because they produce reliable results on the X4 Pro, but individual images may benefit from brightness or contrast adjustment.

Contributing

Bug reports, improvements, and pull requests are welcome.

Useful areas for future development include:

alternative dithering algorithms
automatic portrait optimization
contrast presets
batch ZIP export
draggable crop positioning
device presets for other e-ink readers
PWA / offline support
License

This project is released under the MIT License.

See LICENSE for details.

Citation

If you use this software in a publication, project, tutorial, or academic work, please cite the repository.

Citation metadata is provided in CITATION.cff.
