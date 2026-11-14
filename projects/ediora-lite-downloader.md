# EDIORA Lite Downloader

**Area:** Windows desktop downloader and offline dependency packaging  
**Artifacts reviewed:** EDIORA Lite Windows executable; a separate single-file offline tool-bundle build.  
**Evidence level:** Windows binary inspection and packaging artifact inspection; no native Windows downloading test.

## Project overview

This project focuses on desktop media-download workflows, output-format handling and packaging supporting command-line tools with the application.

Relevant tools in the associated packaging work include `yt-dlp`, `Deno`, `FFmpeg` and `FFprobe`. The available offline bundle was designed to extract bundled tools locally so users do not have to install each dependency manually.

## Engineering challenges

- Keeping downloaded dependencies available across application launches.
- Preserving the application's existing format-selection behavior.
- Handling failure or missing local tools clearly.
- Verifying extracted tool files rather than assuming success.
- Explaining browser/cookie dependencies without including private browser data.

## Portfolio demonstration plan

1. Start the application on a clean Windows test account.
2. Verify the dependency bundle extracts offline.
3. Download a permitted test video using an available format.
4. Check that audio and video are playable and match the selected format.
5. Relaunch, check cached tools, and record any extra network downloads.
6. Capture real progress output and error cases.

## Verification limits

The submitted Windows executable has been inspected as an executable artifact, but a live Windows download and first-run offline test were **not performed in this review**. Chrome/browser profile dependency and the application's own updater may still require external resources. This page does not claim that the app works completely offline in all circumstances.

[Back to all projects](README.md)
