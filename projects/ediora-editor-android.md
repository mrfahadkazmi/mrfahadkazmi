# EDIORA Editor — Android Video Editing Application

**Featured project #1** | **Status:** In development — Google Play release planned (not yet published)

**Inspected version:** Android v1.8.42 / versionCode 57 / package com.ediora.editor

## Overview
EDIORA Editor is a touch-first Android video editing application project. The inspected source contains an Android Studio app, a React/TypeScript editor, and native processing components.

## Technology visible in source
- Android Java, C++/JNI, ONNX Runtime
- React, TypeScript, Vite and CSS
- Android camera/microphone, media picker and foreground-export services
- Gradle-based Android build and bundled editor web assets

## Source-inspected workflows
- Timeline editing, trimming, snapping, zoom and touch gestures
- Transform, Speed, Motion, Effects and Crop in the Edit workspace
- Text overlays, auto-caption tracks and caption style controls
- Export quality, output resolution, FPS and media controls
- Picture-in-picture camera/microphone workflows
- Audio processing, transcription and language functionality

These are features visible in code and project documentation; this review did not demonstrate all of them working on a physical Android device.

## Working application demo

**[Watch EDIORA Editor — Android screen recording (7 min 14 sec)](https://drive.google.com/file/d/1wh3sz0W8Z6F_Ck335He5LOVEH8g6wnVq/view?usp=drivesdk)**

Recorded on an Android phone on 14 November 2026. The uncut screen recording shows actual app operation rather than a promotional render:

- **00:00–00:45:** EDIORA Editor workspace, video previews and a timeline with imported footage.
- **00:45–02:05:** Adjustment tools, timeline playback and edit controls.
- **~02:05–02:30:** Auto Captions settings and caption track interface.
- **~02:30–07:05:** Export progress on the phone, including a visible 1080 × 1920 export dialog.
- **~07:05–07:14:** Android save dialog showing `EDIORA_export.mp4`.

**Evidence scope:** This is genuine UI and export-workflow evidence. It does not independently establish exported-file playback, correctness of every editing tool, or performance on other Android devices. Third-party sample footage may appear in the recording.

## Technical evidence
- Source reviewed: EDIORA_Android_Studio_v1.8.42.zip from the project owner's Library.
- APK reviewed: EDIORA-v1.8.42-debug.apk; archive integrity verified, 3 DEX files and 12 native libraries present. All 12 libraries passed static 16 KB ELF and APK-entry alignment checks; release AAB and device testing remain unverified.
- Selected Node.js checks: **26 passed / 29 total**. Three checks failed or could not load in the local environment.
- No clean Android Studio rebuild, phone test, final export verification or Play Console submission was performed in this review.

[Read local test results and Play Store preparation checklist](ediora-editor-test-results.md).

## Planned Google Play launch
The intended release is forthcoming, not already live. Required work includes Android API 36 target, signed release Android App Bundle and its own 16 KB alignment validation, device testing, store listing and privacy review.

## Scope and disclosure
A separate Drive project archive is a 903 MB RAR that exceeded the connected downloader limit. Its contents were not compared with the versioned Library ZIP reviewed here. Private source code and credentials are not published in this public portfolio.

[Back to all projects](README.md)