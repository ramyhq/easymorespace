# Easy More Space v9.1 — Save 70% of Your Image Size

**Preserve memories for a lifetime. No quality loss. No metadata lost. No rotation.**

---

## What It Does

Easy More Space is a free, open-source desktop application that compresses your images without destroying their quality. It preserves every pixel of metadata — EXIF data, camera info, date taken, GPS coordinates — and never rotates your photos.

Built for Windows and macOS. No ads. No tracking. No paywalls.

---

## Key Features

### Smart Compression
- Resize images down to your chosen maximum dimension (width or height)
- Adjustable JPEG quality slider — 85% is the sweet spot
- Supports **JPG, PNG, WebP, BMP, TIFF** — output to **JPG, PNG, WebP, or AVIF**
- Preserves all EXIF metadata perfectly
- Zero rotation — your images keep their original orientation

### Two Flexible Modes
- **Folder Mode:** select an entire folder and compress everything inside
- **Files Mode:** hand-pick individual images to compress

### Batch Rename Engine
- Powerful pattern-based renaming: `{prefix}_{date}_{num}`
- Supported tokens: `{prefix}`, `{date}`, `{num}`, `{num:4}`, `{original}`, `{ext}`
- **Smart date extraction** — reads dates from filenames (e.g., `20200102_190117.jpg` → `2020-01-02`) or EXIF metadata
- 7 date output formats
- Custom start number and zero-padding
- Live preview before execution
- Quick presets: Vacation, IMG_0001, Date+Num, Keep Original

### Two Rename Workflows
- **Compress + Rename:** compress images first, then rename the output
- **Rename Only:** rename files without any compression — perfect when images are already optimized

### Real-Time Activity Log
- See every file being processed as it happens
- Green = success, Red = error, Yellow = warning
- Copy any text with right-click
- Full summary on completion

### Ad System
- Image-only rotating banner (every 60 seconds)
- Works offline with bundled images
- Automatically fetches updated ads when online
- Green/red dot shows connection status
- "Advertise Here" link for sponsors

### Polish & UX
- 3 languages: English, Arabic, French
- Tooltips on every control (hover to learn)
- Single-instance — no duplicate windows
- Scrollbar only appears when needed
- Mute/unmute completion sound
- Right-click copy on all text fields
- Clean, modern light interface

---

## Cross-Platform

One codebase. Runs natively on:

| Platform | Status |
|----------|--------|
| Windows 10/11 | Fully supported (`.exe`) |
| macOS | Fully supported (`.app`) |
| Linux | Compatible (untested) |

---

## Technical

**No installation required.** The `.exe` is a single self-contained file — Python, Pillow, tkinter, and all libraries bundled inside.

- **Engine:** Pillow (PIL) with LANCZOS resampling
- **EXIF:** full byte-level preservation — no stripping, no modification
- **Audio:** custom embedded beep sound (cross-platform)
- **Performance:** multi-threaded — UI stays responsive during compression
- **Size:** ~18 MB (exe)

---

## Who Is This For?

- Photographers archiving thousands of photos
- Anyone running out of cloud storage
- Families preserving decades of memories
- Developers needing a reliable image pipeline
- Anyone who hates bloated, ad-ridden software

---

## Links

- **Website:** [dev.ifeps.net](https://dev.ifeps.net)
- **Support the developer:** [ko-fi.com/ramydmk](https://ko-fi.com/ramydmk)
- **Contact:** [dev.ifeps.net/contact.html](https://dev.ifeps.net/contact.html)

---

**Easy More Space — because your memories deserve to last.**
