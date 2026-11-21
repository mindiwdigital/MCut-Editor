MCut Editor — Desktop Upgrade Package
=====================================

PACKAGE CONTENTS
----------------
index.html                 Updated MCut editor application
manifest.webmanifest       Desktop PWA metadata
sw.js                      Offline app-shell service worker (cache v8)
logo.png                   Official logo — used for the app brand, favicon and PWA icons

WHAT WAS IMPROVED
-----------------
- Desktop-only access now uses user-agent/platform signals and iPadOS detection, not screen width or touch support alone. Windows touchscreen laptops remain supported.
- Unsupported mobile/tablet devices receive the requested desktop/laptop-only message. The mobile app no longer attaches its PWA manifest or installs its service worker.
- Clip keyframes now interpolate position, scale, rotation and opacity with smooth ease-in/ease-out motion in preview and canvas export. Keyframes can be revisited and removed in the Inspector.
- Masks are now editable rectangle/ellipse regions with mosaic or blur, position/size controls, feathering, inversion, and preview dragging.
- Radial and directional blur now have render paths. The background-blur option applies blur to the base video layer while titles and PiP remain sharp.
- Imported audio playback/export now applies fade-in/fade-out, a bass shelf and a lightweight noise gate. These are processed in the Web Audio graph when supported.
- PWA assets and service-worker cache versions/paths have been aligned with the actual packaged files.

PUBLISH ON GITHUB PAGES
-----------------------
1. Upload the CONTENTS of this folder to the repository root.
2. Keep index.html, manifest.webmanifest, sw.js and logo.png in the root.
3. Keep the icons folder with both icon files.
4. In GitHub: Settings > Pages > Deploy from a branch > choose main and /(root).
5. Open the published HTTPS URL in Chrome or Edge on a supported desktop/laptop.

IMPORTANT LIMITATIONS
---------------------
- This remains a static browser-based editor. It does not gain native desktop codecs merely by packaging these files.
- Export remains WebM via MediaRecorder. MP4 export is not guaranteed in browsers.
- Full AI motion/object tracking, optical-flow interpolation, professional stabilization, polygon/freehand/Bezier masks, native LUT file import and native multi-video track compositing are not implemented in this pass. The source app does not include the necessary ML models, native codecs or a render backend, so those capabilities must not be presented as working buttons.
- Noise gating depends on browser Web Audio support and uses a lightweight threshold gate; it is not a studio-grade dialogue-isolation system.
- Projects and media remain local to the browser/device in IndexedDB.

TESTING
-------
For local testing, run a static server in this folder, for example:
  python -m http.server 8000
Then open http://localhost:8000 in Chrome or Edge.
