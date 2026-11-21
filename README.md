# IMAGE TRUTH

A browser-only image file signature detector that ignores the filename extension and offers a download with the detected extension.

## Features
- Detect format from file bytes, not filename suffix
- Drag/drop and batch scanning
- Reports image dimensions when browser decoding is supported
- Download with corrected extension while preserving original bytes (no recompression)
- Local-only: files are not uploaded

## GitHub Pages
Repository Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Supported signatures include JPEG, PNG, GIF, WebP, BMP, TIFF, ICO, AVIF, HEIF/HEIC, JPEG 2000, JXL, SVG, and PSD.

Detection is signature-based; unknown or truncated files may be reported as unknown. Browser preview/decode support varies by format.
