MCut Editor — GitHub Pages package
==================================

FILES
-----
index.html              App UI, editor and editing logic (no build step)
                         New Project dialog buttons are bound after the dialog opens (fixed)
manifest.webmanifest    Installable PWA metadata
sw.js                   Offline app-shell service worker (cache v2 refresh)
logo.png                Temporary MCut brand mark; replace with your official logo.png
icons/                  PWA launcher icons

PUBLISH ON GITHUB PAGES
-----------------------
1. Create/open your GitHub repository.
2. Upload the CONTENTS of this folder to the repository root (not the folder itself).
3. Keep index.html, manifest.webmanifest, sw.js and logo.png together in the root.
4. In GitHub: Settings > Pages > Deploy from a branch > select main and /(root) > Save.
5. Open the published HTTPS address. First load needs internet so the app shell can cache.
6. In Chrome/Edge use the browser install control or the app's Install app button. On iPhone/iPad use Safari > Share > Add to Home Screen.

IMPORTANT NOTES
---------------
- This is a static, browser-based editor designed for GitHub Pages. No server or database account is needed.
- Drafts and imported media are stored locally in IndexedDB in the browser on that device. Clearing browser site data can erase them. They do not automatically sync between devices.
- Replace the included temporary logo.png with your real logo file, keeping the exact filename and dimensions suitable for a square icon. The launcher icons in /icons are also placeholders; regenerate them from your real logo for a fully branded install icon.
- Browsers do not allow a website to silently install itself. Installation always requires a user action and may require browser confirmation.
- Export uses MediaRecorder and normally creates .webm. MP4 export is not guaranteed in all browsers. Chrome or Edge on HTTPS is recommended.
- Live automatic captions rely on the browser Speech Recognition API and microphone; support varies. For an existing video's speech, play audio near the microphone or import an SRT subtitle file. No cloud transcription API is bundled.
- “AI Trim” is a local visual-activity analysis heuristic based on frame changes; it is not a trained generative AI model.
- Record supports microphone voiceovers and camera video capture, where the browser exposes those devices and permissions.
- Features that require native codecs or permissions (microphone, screen/audio access) are limited by browser/device support.

TESTING
-------
For local testing, use a local static server (for example `python -m http.server 8000`) and visit http://localhost:8000. PWA installation and service workers require HTTPS or localhost.
