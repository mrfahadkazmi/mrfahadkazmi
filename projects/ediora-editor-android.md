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

## Technical evidence
- Source reviewed: EDIORA_Android_Studio_v1.8.42.zip from the project owner's Library.
- APK reviewed: EDIORA-v1.8.42-debug.apk; archive integrity verified, 3 DEX files and native libraries present.
- Selected Node.js checks: **26 passed / 29 total**. Three checks failed or could not load in the local environment.
- No clean Android Studio rebuild, phone test, final export verification or Play Console submission was performed in this review.

[Read local test results and Play Store preparation checklist](ediora-editor-test-results.md).

## Planned Google Play launch
The intended release is forthcoming, not already live. Required work includes Android API 36 target, signed release Android App Bundle, 16 KB native library alignment checks, device testing, store listing and privacy review.

## Scope and disclosure
A separate Drive project archive is a 903 MB RAR that exceeded the connected downloader limit. Its contents were not compared with the versioned Library ZIP reviewed here. Private source code and credentials are not published in this public portfolio.

[Back to all projects](README.md)