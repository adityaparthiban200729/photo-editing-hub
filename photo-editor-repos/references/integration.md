# Filerobot integration guide

Read this before implementing the skill in a target application. Use the
[upstream README and configuration API](https://github.com/scaleflex/filerobot-image-editor)
as the authority for the version actually selected. These are original integration
instructions, not copied repository source.

## Choose and verify dependencies

Use `react-filerobot-image-editor` in React. Inspect its published `version`,
`peerDependencies` and `engines` before installing. Inspect the app's React,
React DOM, react-konva and styled-components versions together. Upstream documents
React/React DOM, react-konva and styled-components prerequisites and a version
compatibility table; do not turn the README's old minimums into a guarantee for
newer major versions. If incompatible, explain a safe compatible version choice
rather than using `--force` or `--legacy-peer-deps`. Do not rewrite the existing
app's React major without a reason and approval when the change is substantial.

Use the app's package manager, pin selected versions, commit the lockfile, and
inspect install/build output. There is no reason to clone upstream source.

## Mount and load safely

For React, manage editor visibility and image source in application state.
For Next.js, put browser-dependent loading behind a client component; use a
client-side dynamic import with SSR disabled when necessary. Keep Node/Python
processing out of that component's dependency graph.

Give the wrapper a real width and height: upstream fills its container rather
than providing a complete responsive host. Ensure controls remain usable on a
small screen. Load the configured font in normal/medium weights, or explicitly
choose locally available fonts; the library does not bundle its default Roboto.

Prefer a selected local file mapped to an object URL. Revoke the old URL on
replacement/unmount after consumers finish. Validate type, byte size and decoded
pixel count, and give a readable error for corrupt or unsupported input. Do not
promise RAW/HEIC/PSD support without an explicit, tested conversion path.

For remote images, check CORS before allowing canvas export. Do not suggest an
open proxy as a workaround. If a backend fetcher is necessary, enforce an
allowlist, block private/internal network destinations and validate the download.

## Configure only requested features

Use the exported `TABS` and `TOOLS` constants, a subset in `tabsIds` when needed,
and consistent `defaultTabId` / `defaultToolId`. An empty tab list means all tabs
in upstream documentation, not no tabs. Prefer built-in crop and annotations
before adding Cropper.js or Fabric.js. Do not attempt to exchange Fabric scene
JSON directly with Filerobot's internal design state.

Leave image adjustments neutral. Do not restore an earlier dark/moody/matte
style or impose an aesthetic as a hidden default. Apply UI theming only to meet
the current brief or the host application's design system.

## Export and saved editing state

Implement `onSave(editedImageObject, designState)` according to the installed
version's object schema. Choose the supported image data/canvas output for a
real download or an explicitly approved upload. Verify available fields before
using them; never infer that a field exists from an unrelated library. A save
callback that logs data is not a finished save feature.

Honor requested pixel dimensions, output format and quality. Test saved files,
not only the preview. Confirm transparent pixels survive PNG/WebP export; give
an explicit background choice for JPEG, which cannot preserve alpha. Check
orientation, aspect ratio, sharpness, download name and MIME type. Inspect the
selected version's pixel-ratio/export settings before accepting device-scaled
output. Avoid repeated lossy re-encoding.

Retain the source separately from the rendered output. If editable sessions are
needed, store design state with the original asset identity and editor version,
and use the documented reload configuration for that version. Test reload after
closing the editor. Upstream labels state export/reload experimental: it is not
a stable interchange format or a promise of Photoshop-compatible layers.

## Optional backend operations

Start with Filerobot alone. Add sharp only for a Node server's conversion or
image-delivery work. Add rembg only for requested background removal, preferably
beside Pillow in an existing Python service. Wrap Real-ESRGAN in bounded jobs
only for requested upscaling/restoration. Treat miniPaint and IOPaint as separate
applications, and Upscayl as a manual desktop workflow.

For any processing endpoint, bound upload size, decoded dimensions, model choice,
timeout, concurrency and temporary-file lifetime. Enforce authentication where
needed. Treat uploads as untrusted and avoid command injection. Model loading
may involve large downloads; verify licences and explain hardware requirements
before provisioning. Do not silently send photos to a cloud provider.

Pass the resulting raster back as a new image source while preserving the
original and existing export. Define whether AI processing starts a new editing
session; do not promise earlier annotations will remap automatically.

## Acceptance checks

- Load a normal local photo, a corrupt file and an oversized input.
- Exercise each requested tool, undo/redo, reset, close and reopen.
- Test remote-image failure/CORS handling if URLs are supported.
- Download and decode a real exported image; verify dimensions, type and alpha.
- Verify saved design-state reload only if implemented.
- Check narrow layout, visible labels, keyboard/focus behavior and cancellation.
- Run build, type checks and existing tests; inspect browser errors if available.
- If promising local/offline behavior, disable backend translations, use local
  fonts/assets, inspect network traffic and test without connectivity.
- State exactly which tests passed, failed or were not run.
