# IMAGE TRUTH

**Version: v1.1.5**

A browser-based image format detector and repair tool. It checks file signatures instead of trusting filename extensions.

## Features
- Detect image formats from file signatures, including JPEG, PNG, GIF, WebP, BMP, TIFF, ICO, AVIF, HEIF/HEIC, JPEG 2000, JXL, SVG, and PSD.
- Correct the filename extension and MIME type while preserving the original image bytes.
- Convert supported images to PNG. It first tries the browser native decoders (`createImageBitmap`, WebCodecs `ImageDecoder`, and HTML `Image`). When those fail for HEIC/HEIF, it lazily loads the pinned `libheif-js` 1.23.5 WebAssembly decoder from jsDelivr.
- Generate HEIC/HEIF previews with a small thumbnail path when the browser cannot preview the source natively.
- Release decoded HEIF image handles after processing. HEIF/HEIC WASM processing is sequential and currently limited to files up to 100 MB and images up to 24 megapixels to reduce mobile memory pressure.
- PNG conversion uses one decode-and-encode pass. Canvas re-encoding preserves pixels but does not copy source EXIF or other metadata. Animated formats export the currently decoded frame.
- Show a selected-file preview, filename, dimensions, format, and clear upload/processing feedback.
- Accept files regardless of their filename extension.
- Batch rename files ending in `.apk.1` to `.apk` without changing file contents. The APK tool is placed at the bottom of the page.
- All image processing stays in the browser; source files are not uploaded. The HEIF decoder is downloaded from jsDelivr only when needed.

## Third-party decoder
- [libheif-js 1.23.5](https://www.npmjs.com/package/libheif-js), licensed under LGPL-3.0. Its browser WebAssembly bundle is loaded on demand from [jsDelivr](https://www.jsdelivr.net/).

## GitHub Pages
Repository Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Detection is based on file signatures. Unknown, truncated, encrypted, or unsupported files are not guessed. Preview and PNG conversion for other formats still depend on browser decoder support. The HEIF/HEIC fallback requires an internet connection to load the decoder the first time.
