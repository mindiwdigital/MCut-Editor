# MCut Editor — CapCut-style Desktop Upgrade

This is an upgrade of the existing MCut Editor source, preserving its original project format and current editing tools while adding a separate video-overlay track and a contextual properties inspector.

## Added in this build

- Independent **video overlay** clips above the main footage, stored with the project in IndexedDB.
- Add overlay videos from the device, select them on the timeline, drag them on the preview, trim their in/out points, adjust size, position, opacity, speed, fit and rounded corners.
- Dedicated blue video-overlay timeline blocks and a layer management panel.
- Contextual desktop inspector for video/photo clips, overlay videos, audio, text and captions.
- Improved laptop/desktop column sizing; inspector is hidden on narrower tablet/mobile layouts to keep the editing stage usable.
- Existing logo, project storage, transitions, keyframes, color grade, masks/blur/mosaic, chroma key, captions, audio controls, effects and export flow retained.

## Publish on GitHub Pages

1. Extract this ZIP.
2. Upload **all files and folders inside** this folder to the repository root.
3. Ensure `index.html`, `logo.png`, `manifest.webmanifest`, and `sw.js` are in the root.
4. In GitHub, open **Settings → Pages → Deploy from a branch**, choose `main` and `/(root)`, then save.
5. Open the HTTPS Pages URL using a supported desktop/laptop browser (Chrome or Edge recommended).

## Important limitations

- This remains a browser-based, local-first video editor. Projects and imported media are stored in that browser on that device; they do not automatically sync between computers.
- Overlay video audio is muted in this build. Import its sound separately through the Music/Audio track.
- Export remains browser `MediaRecorder` WebM where supported. Native MP4 export and the full native codec pipeline are not added by this upgrade.
- A browser editor cannot claim the same performance, codecs, AI features, stabilization, or full multi-track render engine as CapCut desktop. Those require separate render/media-engine work.
- Large video files and multiple simultaneous layers depend on available RAM, GPU and browser decoding support.

## Local test

Run `python -m http.server 8000` in this folder and open `http://localhost:8000` in Chrome or Edge.
