# EDIORA Editor (Android) — source review and test results

**Review date:** 14 November 2026
**Available source reviewed:** EDIORA_Android_Studio_v1.8.42.zip (Library)
**Available binary reviewed:** EDIORA-v1.8.42-debug.apk (Library)
**Environment:** Linux x86-64, Node.js 22.16.0, OpenJDK 21.0.12.1

## Automated checks
Ran 10 selected Node.js test modules from web/tests using node --test.

**Results: 29 checks, 26 passed, 3 failed/blocked; 0 skipped.**

Successful local tests included timeline trim/snap/zoom, audio signal-processing and audio state transitions, source export metadata validation, mobile editing gestures, player-selection logic and workspace layout assertions.

Three checks could not complete:
1. Android-language test module: missing Vite package in test environment (ERR_MODULE_NOT_FOUND).
2. Animation-math test module: unresolved relative module import from a data URL (ERR_UNSUPPORTED_RESOLVE_REQUEST).
3. Player-items browser-rendering subtest: missing Vite package in test environment.

Those failures do not prove that corresponding features fail on Android; they indicate unresolved local test execution. No blanket 'all tests passed' claim is made.

## APK validation
- APK ZIP integrity test found no damaged member.
- 3 DEX files and native libraries for arm64-v8a and x86_64 were present.
- Not tested: actual installation and use on a phone/emulator, camera/mic PIP, export MP4 playback, crash-free operation, memory usage, device compatibility.

## Build configuration observed
| Setting | Value |
| --- | --- |
| Application ID | com.ediora.editor |
| Version | 1.8.42 (versionCode 57) |
| Minimum SDK | 26 |
| Target / compile SDK | 35 / 35 |
| Android Gradle Plugin | 8.9.2 |
| Gradle wrapper | 8.11.1 |
| NDK | 27.0.12077973 |

## Planned Google Play submission — outstanding work
1. Upgrade and validate the Android phone app's targetSdk to **API 36 or higher**, as required for new Google Play app submissions since August 31, 2026. [Google Play target API policy](https://support.google.com/googleplay/android-developer/answer/11926878).
2. Generate and sign a **release AAB** rather than upload the reviewed debug APK.
3. Check all native .so libraries and packaging for **16 KB page-size support**. [Android guidance](https://developer.android.com/guide/practices/page-sizes).
4. Run real-device smoke tests: import video, scrub/trim/split, save/reopen, captions, sound, PIP camera/mic, export, output playback and permissions.
5. Prepare a privacy policy, accurate data-safety disclosures, screenshots, age/content declarations and required Play Console testing.
6. Resolve blocked test imports; rerun complete automated tests with installed project dependencies; run Android Gradle build in an SDK-enabled environment.

## Scope clarification
This review was of a versioned project ZIP and APK available in the owner's Library. The separately shared 903 MB Drive RAR could not be downloaded through the connected service's 256 MB limit; the two archives were **not** verified as identical. Source files are not publicly hosted here, so independent reproduction requires access to them.

[Back to EDIORA Editor](ediora-editor-android.md)