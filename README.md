# IMAGE TRUTH

**Version: v1.1.1**

A browser-based image format detector and repair tool. It checks file signatures instead of trusting filename extensions.

## Features
- Detect image formats from file bytes, including JPEG, PNG, GIF, WebP, BMP, TIFF, ICO, AVIF, HEIF/HEIC, JPEG 2000, JXL, SVG, and PSD.
- Correct the filename extension and MIME type while preserving the original image bytes.
- Try PNG conversion for any selected file the browser can decode; PNG conversion re-encodes the image. Animated formats export the currently decoded frame.
- Show a selected-file preview, filename, dimensions, format, and clear upload/processing feedback.
- Accept files regardless of their filename extension.
- Batch rename files ending in `.apk.1` to `.apk` without changing file contents. The APK tool is placed at the bottom of the page.
- All processing stays in the browser; files are not uploaded.

## GitHub Pages
Repository Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Detection is based on file signatures. Unknown, truncated, encrypted, or unsupported files are not guessed. Preview and PNG conversion depend on the browser's image decoder.
