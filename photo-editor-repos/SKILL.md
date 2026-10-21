---
name: photo-editor-repos
description: >-
  Curated catalog of 44 open-source photo editing projects, grouped by
  purpose and ordered by usefulness: desktop editors, web/JavaScript
  editors and components, image-processing libraries and CLIs, AI photo
  tools, and mobile SDKs. Each entry has a one-line summary, license,
  stars and link, and every project is also linked as a git submodule
  (upstream code is referenced, never copied). Use when picking a photo
  editor to use, building an image editor or photo feature in an app or
  website, choosing an image-processing library, or finding AI tools for
  upscaling, background removal, inpainting or generative editing.
---

# Photo Editor Repos

A curated catalog of 44 open-source photo editing projects. The source code
itself is **not** copied here - each project is linked as a git submodule
pointing to its upstream repo, pinned to a recent commit.

Get everything:

```bash
git clone --recurse-submodules https://github.com/adityaparthiban200729/photo-editing-hub.git
```

Or pull a single project, e.g.:

```bash
git submodule update --init ai/rembg
```

Stars are approximate, as of October 2026.

## Best picks

Judgment calls - the ten most useful projects for most people:

| Pick | Why | License |
| --- | --- | --- |
| [darktable](https://github.com/darktable-org/darktable) | Best free Lightroom replacement: full RAW workflow and pro color grading | GPL-3.0 |
| [GIMP](https://github.com/GNOME/gimp) | The full Photoshop-style editor, mature and extensible | GPL-3.0 |
| [RapidRAW](https://github.com/CyberTimon/RapidRAW) | Modern, fast, non-destructive Lightroom-style editor | AGPL-3.0 |
| [miniPaint](https://github.com/viliusle/miniPaint) | Full photo editor that runs entirely in the browser | MIT |
| [fabric.js](https://github.com/fabricjs/fabric.js) | Canvas toolkit for building your own web editor | MIT |
| [Squoosh](https://github.com/GoogleChromeLabs/squoosh) | Best-in-class image compression, in the browser | Apache-2.0 |
| [Upscayl](https://github.com/upscayl/upscayl) | One-click AI image upscaling app | AGPL-3.0 |
| [rembg](https://github.com/danielgatis/rembg) | One-command AI background removal | MIT |
| [IOPaint](https://github.com/Sanster/IOPaint) | AI inpainting: erase objects, defects, people from photos | Apache-2.0 |
| [ComfyUI](https://github.com/Comfy-Org/ComfyUI) | Node-based generative AI image workflows | GPL-3.0 |

## Desktop editors

Full applications you install and use.

| Project | What it is | License | Stars |
| --- | --- | --- | --- |
| [darktable](https://github.com/darktable-org/darktable) | Photography workflow app and RAW developer | GPL-3.0 | 13.3k |
| [GIMP](https://github.com/GNOME/gimp) | Full-featured image editor (mirror of the GNOME GitLab home) | GPL-3.0 | 6.5k |
| [Krita](https://github.com/KDE/krita) | Digital painting and illustration studio | GPL-3.0 | 10.6k |
| [RapidRAW](https://github.com/CyberTimon/RapidRAW) | GPU-accelerated, non-destructive RAW editor (React + Rust) | AGPL-3.0 | 10.6k |
| [RawTherapee](https://github.com/RawTherapee/RawTherapee) | Deep RAW processing and color control | GPL-3.0 | 4.2k |
| [Graphite](https://github.com/GraphiteEditor/Graphite) | 2D graphics editor, procedural and node-based | Apache-2.0 | 27.7k |
| [Pinta](https://github.com/PintaProject/Pinta) | Simple paint/editor, Paint.NET-style | MIT | 4.1k |
| [MyPaint](https://github.com/mypaint/mypaint) | Painting app for graphics tablets | GPL-2.0 | 3.0k |
| [digiKam](https://github.com/KDE/digikam) | Photo management with built-in editing | GPL-2.0 | 0.8k |

## Web / JavaScript editors and components

Drop-in editors and building blocks for web apps.

| Project | What it is | License | Stars |
| --- | --- | --- | --- |
| [Squoosh](https://github.com/GoogleChromeLabs/squoosh) | Image compression with modern codecs, in-browser | Apache-2.0 | 26.1k |
| [tui.image-editor](https://github.com/nhn/tui.image-editor) | Full-featured canvas photo editor component | MIT | 7.7k |
| [miniPaint](https://github.com/viliusle/miniPaint) | Complete online image editor | MIT | 3.5k |
| [filerobot-image-editor](https://github.com/scaleflex/filerobot-image-editor) | Embeddable editor: resize, filters, annotations | MIT | 1.9k |
| [unlayer/react-image-editor](https://github.com/unlayer/react-image-editor) | React editor component: crop, filters, draw, text, stickers | MIT | 0.3k |
| [react-photo-editor](https://github.com/musama619/react-photo-editor) | React component/hook: brightness, contrast, saturation | MIT | 85 |
| [react-konva-image-editor](https://github.com/wormwlrm/react-konva-image-editor) | Image editor built on React + Konva | MIT | 51 |
| [ascentspark/react-image-editor](https://github.com/ascentspark/react-image-editor) | Lightweight React image editor component | MIT | 3 |
| [ente photo-editor-sdk](https://github.com/ente/photo-editor-sdk) | Extensible React photo editor SDK | MIT | 15 |
| [Photova](https://github.com/phishy/photova) | Photo editor SDK plus self-hosted asset management | BSL-1.1 (not OSI-open) | 3 |
| [fabric.js](https://github.com/fabricjs/fabric.js) | Canvas object model and editor framework | MIT | 31.5k |
| [Cropper.js](https://github.com/fengyuanchen/cropperjs) | The standard JS image cropper | MIT | 13.9k |
| [PixiJS](https://github.com/pixijs/pixijs) | Fast 2D WebGL renderer for image effects | MIT | 48.4k |
| [CamanJS](https://github.com/meltingice/CamanJS) | Canvas manipulation and filters (unmaintained) | BSD-3-Clause | 3.6k |
| [Jimp](https://github.com/jimp-dev/jimp) | Pure-JS image processing for Node | MIT | 14.7k |
| [sharp](https://github.com/lovell/sharp) | Fastest Node image resize/convert (libvips) | Apache-2.0 | 32.8k |
| [pica](https://github.com/nodeca/pica) | High-quality image resize in the browser | MIT | 4.2k |

## Image libraries and CLIs

Server-side and scripting workhorses.

| Project | What it is | License | Stars |
| --- | --- | --- | --- |
| [OpenCV](https://github.com/opencv/opencv) | The computer-vision and image-processing library | Apache-2.0 | 91.3k |
| [ImageMagick](https://github.com/ImageMagick/ImageMagick) | CLI suite to convert, edit, compose images | ImageMagick (Apache-2.0-compatible) | 17.7k |
| [libvips](https://github.com/libvips/libvips) | Fast, low-memory image processing | LGPL-2.1 | 11.8k |
| [Pillow](https://github.com/python-pillow/Pillow) | The Python imaging library | HPND (MIT-CMU) | 13.9k |
| [scikit-image](https://github.com/scikit-image/scikit-image) | Image processing algorithms in Python | BSD-3-Clause | 6.6k |

## AI photo tools

Upscaling, restoration, background and object removal, generative editing.

| Project | What it is | License | Stars |
| --- | --- | --- | --- |
| [Upscayl](https://github.com/upscayl/upscayl) | Desktop AI upscaler app | AGPL-3.0 | 50.8k |
| [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) | Practical image/video restoration and upscaling models | BSD-3-Clause | 37.2k |
| [GFPGAN](https://github.com/TencentARC/GFPGAN) | Real-world face restoration | Apache-2.0 | 37.7k |
| [rembg](https://github.com/danielgatis/rembg) | Background removal CLI/library (also published as BackgroundRemover) | MIT | 25.1k |
| [IOPaint](https://github.com/Sanster/IOPaint) | Inpainting: remove objects, defects, watermarks | Apache-2.0 | 23.3k |
| [Segment Anything](https://github.com/facebookresearch/segment-anything) | Meta's segmentation model, the basis of smart cutouts | Apache-2.0 | 55.0k |
| [Stable Diffusion web UI](https://github.com/AUTOMATIC1111/stable-diffusion-webui) | Full generative image UI: img2img, inpaint, upscale | AGPL-3.0 | 165k |
| [ComfyUI](https://github.com/Comfy-Org/ComfyUI) | Node-based diffusion GUI and backend | GPL-3.0 | 141k |
| [InstructPix2Pix](https://github.com/timothybrooks/instruct-pix2pix) | Edit images with text instructions | MIT | 6.9k |

## Mobile SDKs

| Project | What it is | License | Stars |
| --- | --- | --- | --- |
| [PhotoEditor](https://github.com/burhanrashid52/PhotoEditor) | Android editor library: paint, text, filters, stickers | MIT | 4.5k |
| [android-gpuimage](https://github.com/wasabeef/android-gpuimage) | OpenGL image filters for Android | Apache-2.0 | 9.2k |
| [GPUImage](https://github.com/BradLarson/GPUImage) | GPU image/video processing for iOS (Objective-C) | BSD-3-Clause | 20.3k |
| [GPUImage3](https://github.com/BradLarson/GPUImage3) | GPUImage rewritten in Swift/Metal | BSD-3-Clause | 2.9k |

## Notes and caveats

- **Licenses matter.** GPL/AGPL projects (darktable, GIMP, Krita, RapidRAW, Upscayl, ComfyUI, Stable Diffusion web UI) are copyleft: shipping derivatives means publishing source. MIT/Apache/BSD projects are safe to embed anywhere. Photova is BSL-1.1, which restricts production use until its change date.
- **Archived projects:** Squoosh and CamanJS are no longer actively maintained but remain useful references.
- "Brighten" from the original list could not be matched to a real repository, so it is not included.
- "danielgatis BackgroundRemover" is the same project as rembg (listed once, above).
- Upstreams that moved and are linked at their current homes: RawTherapee (Beep6581 -> RawTherapee org), ComfyUI (comfyanonymous -> Comfy-Org), ente photo-editor-sdk (ente-io -> ente), android-gpuimage (cats-oss -> wasabeef).
