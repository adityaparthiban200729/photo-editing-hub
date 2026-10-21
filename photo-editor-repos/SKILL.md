---
name: photo-editor-repos
description: Build and extend browser/React photo editors with Filerobot Image Editor as the default core. Use when adding crop, resize, rotate, filters, annotations, text, watermarking, image export or saved editing state to a React/Next.js app, or choosing optional image-processing, background-removal and upscaling tools. Includes ranked, linked add-ons with licence and integration caveats; do not merge upstream repositories or impose a photographic style.
---

# Filerobot Photo Editor

## Default choice

Use [Filerobot Image Editor](https://github.com/scaleflex/filerobot-image-editor)
(**MIT**) as the browser editor. Prefer its React package,
`react-filerobot-image-editor`, for React applications. Use the vanilla
`filerobot-image-editor` bridge only for non-React hosts. It supplies the
interactive crop, resize, rotate/flip, adjustment, filter, annotation, text,
watermark and undo/redo surface without building a second editor.

Treat this as a curated workflow, not a bundled application or a tool already
running. Link upstream repositories; never vendor, merge, fork or add them as
submodules unless the user separately requests it. Install only necessary
published dependencies in the target application, not into this skill.

## Workflow

1. Inspect the target app, package manager, React version, existing image flow
   and requested output. Preserve its framework, design system and original
   images. Ask only about consequential missing requirements.
2. Read [the integration guide](references/integration.md) before implementing.
   Check the current upstream README and package peer dependencies for the
   selected version; pin a compatible set and keep the lockfile. Do not force
   peer resolution or assume the latest React major is supported.
3. Mount one Filerobot editing surface client-side. Supply a valid image source,
   explicit container dimensions, the required font and only the relevant tabs.
   Prefer local files/object URLs for personal photos; revoke URLs after use.
4. Implement real save/download handling through `onSave`, not console logging.
   Preserve the original separately. Save editable state only when required and
   only with its source identity and editor version. Warn that design-state
   serialization is experimental upstream; do not promise portable PSD-like layers.
5. Add a specialist only when Filerobot lacks a requested capability. Consult
   the ranked list below. Keep server, GPU and desktop workloads outside the
   browser bundle. Never claim these projects are drop-in Filerobot plug-ins.
6. Test the requested edits, undo/redo, save/download, actual exported image
   dimensions/type/transparency, image-load failures, close/reopen and narrow
   layouts. Run the project's build/tests. Report what was actually exercised.

## Style and privacy

Ignore the earlier dark/moody/matte style line. Apply no preset photographic
look or forced UI theme. Follow the user's current brief and existing app; keep
image adjustments neutral until requested.

Keep user images local by default. Do not silently upload photos to third-party
AI or cloud services. For strict local processing, disable Filerobot's backend
translation requests (`useBackendTranslations: false`) and use local fonts/assets;
verify the app's network behavior before claiming offline operation. Preserve
originals, avoid logging image data, and handle CORS errors explicitly.

## Optional add-ons — most useful to least for this stack

Rank by incremental value to a **Filerobot-centered React editor**, not by
popularity or overall project quality. None is installed by this skill.

| Rank | Project and upstream link | Licence | Good for / when to use |
| --- | --- | --- | --- |
| 1 | [sharp](https://github.com/lovell/sharp) | Apache-2.0; audit bundled dependencies separately | Fast Node.js backend resizing, format conversion, thumbnails and delivery optimization after export. Never import it into client code. Highest-value production pipeline companion when a backend exists. |
| 2 | [rembg](https://github.com/danielgatis/rembg) | MIT for code; model licences separate | Background removal via a local Python library, CLI or explicitly approved self-hosted service. Return a transparent raster to the editor; avoid undisclosed cloud paths. |
| 3 | [fabric.js](https://github.com/fabricjs/fabric.js) | MIT | Custom object/canvas interactions, selection and serialization that the existing Filerobot surface cannot supply. Use a separate, deliberate surface; its scene graph is not Filerobot state. Avoid duplicating existing annotations. |
| 4 | [cropperjs](https://github.com/fengyuanchen/cropperjs) | MIT | Dedicated crop-only upload/avatar flows outside the full editor. Skip when Filerobot's built-in crop suffices. Check v1/v2 API compatibility before choosing a wrapper. |
| 5 | [Pillow](https://github.com/python-pillow/Pillow) | MIT-CMU (see [official licence](https://github.com/python-pillow/Pillow/blob/main/LICENSE)); not simply generic MIT | Python-side format handling, validation, thumbnails and batch transforms, especially beside rembg. Usually redundant alongside sharp in a Node-only app. |
| 6 | [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) | BSD-3-Clause for repository code; model/dependency terms separate | Optional super-resolution/restoration as a Python/CLI worker or GPU job. Budget for memory, runtime and visual artifacts; no browser-native React integration. |
| 7 | [miniPaint](https://github.com/viliusle/miniPaint) | README declares MIT; GitHub does not identify a standard SPDX licence, so verify the actual files before redistribution | Full browser editor with layers and drawing. Consider only as an alternative/isolated iframe sidecar when full-editor needs exceed Filerobot, not a native React add-on. |
| 8 | [IOPaint](https://github.com/Sanster/IOPaint) | Apache-2.0 for code; model licences separate | Specialist object removal/inpainting. Upstream is archived; do not choose as a new default dependency. Consider only an isolated, reviewed self-hosted sidecar with a maintenance plan. |
| 9 | [Upscayl](https://github.com/upscayl/upscayl) | AGPL-3.0 for application source; model terms separate | Manual desktop upscaling on compatible Vulkan hardware. Useful to an end user, but the weakest fit as a browser/React integration; do not bundle into the web app. |

Recheck upstream licence files, maintenance and runtime requirements at adoption.
Permissive licences still require notices and compliance; code licences do not
automatically cover model weights, fonts, datasets or every dependency. Review
copyleft obligations before distributing or hosting modified covered software.

## Keep out of the default stack

Exclude desktop RAW/painting/photo-management apps, native mobile SDKs,
generative-AI suites and extra complete editors from the default browser stack.
They solve different problems or duplicate the chosen core; this is not a claim
that they are poor projects. Keep archived tools and unverifiable generic names
out of default recommendations. Do not select a package from stars alone, label
source-available software as open source without checking its licence, or
conflate distinct projects such as rembg and BackgroundRemover.

## Completion

Report the core selected, add-ons actually needed, dependency/version choices,
changed files and test results. Distinguish a documented option from a working
integration. If delivering an edited photo, provide the actual image output,
not just instructions. If no app or image was requested, deliver the skill and
links without inventing a deployment or a finished editor.
