# Photo Editing Hub

A focused **Filerobot-first skill for building browser/React photo editors**.
This repository contains original instructions and upstream links—not copies
of other projects, submodules, model weights or a finished editor application.

## Best fit: Filerobot Image Editor

[**Filerobot Image Editor**](https://github.com/scaleflex/filerobot-image-editor)
(MIT) is the selected core: an embeddable browser editor with an official React
package, crop/resize/rotate, adjustments, filters, annotations, text, watermarking
and undo/redo. It fits this use case better than assembling multiple complete
editors or starting with a low-level canvas engine.

Open the [skill](photo-editor-repos/SKILL.md) for the workflow and the
[implementation guide](photo-editor-repos/references/integration.md) for
integration and testing details. **Ignore the earlier dark/moody/matte style
line:** no photographic look or UI theme is imposed.

## Optional add-ons, ranked

The [ranked add-on section](photo-editor-repos/SKILL.md#optional-add-ons--most-useful-to-least-for-this-stack)
lists all nine requested projects with upstream links, licences and uses:

1. **sharp** — Node backend resizing/conversion and delivery optimization.
2. **rembg** — background removal through a Python service/library.
3. **fabric.js** — custom canvas/object interactions beyond built-in tools.
4. **cropperjs** — dedicated crop-only upload flows, when needed outside Filerobot.
5. **Pillow** — Python image utilities, especially beside rembg.
6. **Real-ESRGAN** — optional worker-based super-resolution/restoration.
7. **miniPaint** — alternative full browser editor or isolated sidecar.
8. **IOPaint** — archived inpainting sidecar; not a new default dependency.
9. **Upscayl** — manual desktop/Vulkan upscaling, not a browser add-on.

Order reflects incremental usefulness to this React stack, not general quality.
Use **Filerobot alone first**; add only what a requested feature requires.

## What is excluded from the default stack

The previous broad catalog and its 44 git submodule entries are replaced by
plain links and focused instructions. The old state remains in Git history.
No upstream project is deleted or changed.

- **Desktop RAW, painting and management apps** such as GIMP, darktable, Krita,
  RawTherapee, MyPaint and digiKam are not embeddable React components.
- **Native mobile SDKs** target Android/iOS rather than the browser.
- **Extra full editors and generative suites** duplicate the chosen core or add
  substantial runtime/operational complexity; they are not default dependencies.
- **Archived tools, unclear project identities and source-available licences**
  need separate verification rather than automatic adoption.

These are poor *fits for this task*, not a claim that otherwise capable projects
are intrinsically bad. miniPaint, IOPaint and Upscayl remain listed because they
were explicitly requested, but are not recommended as default integrations.

## Add the skill to Cue

In Cue: **Settings → Skills → Add Skills → Import from GitHub** (desktop:
**Settings → Skills → Add → Import from GitHub**). Use this repository and select
`photo-editor-repos/SKILL.md` if asked for a path. Turn the skill on after import.

A file in GitHub or a local skill directory alone does not prove that Cue's
account-level skill catalog has been updated. Import through Cue to synchronize
it for future chats and Agents. This repository deliberately preserves the
existing `photo-editor-repos` skill name/path for continuity with earlier imports.

## Licensing and boundaries

Upstream projects retain their own licences. The skill links each project and
calls out model/dependency terms where relevant; no third-party source code is
included. A permissive code licence does not automatically license downloaded
models, fonts or datasets. Check actual licence files before adoption or
redistribution. This skill does not install, deploy or activate the optional tools.
