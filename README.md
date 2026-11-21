# IMAGE TRUTH

**Version: v1.1.0**

A browser-only image format detector and repair tool. It checks file signatures instead of trusting filename extensions.

## Features
- Detect formats from file bytes, including JPEG, PNG, GIF, WebP, BMP, TIFF, ICO, AVIF, HEIF/HEIC, JPEG 2000, JXL, SVG, and PSD.
- Correct the filename extension and MIME type while preserving the original image bytes.
- Optionally convert browser-decodable images to PNG for better compatibility. PNG conversion re-encodes the image; animated formats are exported as the currently decoded frame.
- Batch image selection and drag-and-drop.
- Batch rename files ending in `.apk.1` to `.apk` without changing file contents.
- All processing stays in the browser; files are not uploaded.

## GitHub Pages
Repository Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Detection is based on file signatures. Unknown, truncated, encrypted, or unsupported files are not guessed. Preview and PNG conversion depend on the browser's image decoder.
