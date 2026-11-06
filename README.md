# Physics 3D AI — Offline Android starter app

## What this project does
- Runs locally on Android; no login, cloud AI, or internet call is used by the app.
- English/Hindi interface toggle.
- Typed question input.
- On-device photo OCR using the bundled ML Kit text-recognition dependency.
- Offline numerical solvers for:
  - Class 11 projectile motion (ideal same-height launch/landing, no air resistance).
  - Class 11 Circular Motion (centripetal acceleration, angular speed, and force when mass is supplied).
- Offline 2D schematic visualisations and structured simulation data.
- Class 11 and Class 12 topic catalogue.

## Important limitations
- This is a first installable Android project, not a finished all-chapters AI tutor.
- There is no general-purpose LLM in this build. Topic parsing is rule-based and deliberately supports only the two numerical models above.
- OCR accuracy depends on photo quality, handwriting, and language. The included ML Kit Latin recognizer is best suited to printed Latin-script text; Hindi handwritten OCR is not guaranteed.
- The visualisation is 2D, not a full interactive 3D engine.
- Other Class 11/12 chapters are listed but do not yet have verified numerical solvers.
- OCR dependency is bundled in the app, but first build requires internet to download Gradle/Android dependencies. Once built and installed, the app's features are designed to work offline.

## Build an APK
1. Install Android Studio on a computer.
2. Open this folder as an existing project.
3. Let Gradle sync download the Android and ML Kit dependencies (internet required for this one-time build).
4. Connect your Android phone with USB debugging enabled, or choose Build > Build Bundle(s) / APK(s) > Build APK(s).
5. Install the generated APK on your phone.
6. After installation, turn on airplane mode and test typed questions and photo OCR.

Minimum Android version: Android 6.0 (API 23).

## Example questions to test
Projectile:
"A ball is projected with speed 20 m/s at an angle of 30 degrees. Find maximum height and range."

Circular motion:
"A car moves in a circular path with speed 12 m/s and radius 20 m. Find centripetal acceleration."

To calculate centripetal force:
"A mass 2 kg moves in circular motion with speed 12 m/s and radius 20 m. Find centripetal force."

## Next development milestone
Add verified offline solvers chapter-by-chapter, improve unit-aware parsing and error checking, add Devanagari OCR, then replace the schematic canvas with a true offline 3D renderer and interactive controls.


## Build an APK using only your Android phone (cloud build)
This repository includes `.github/workflows/android.yml`. GitHub's cloud runner builds the APK; you do not need Android Studio or a computer.

1. Sign in to GitHub in your phone browser and create a new repository.
2. Extract this ZIP on your phone. In the repository, use **Add file → Upload files** and upload the extracted project contents, including the hidden `.github/workflows/android.yml` folder. If your phone's file picker hides dot-folders, use GitHub's web editor to create `.github/workflows/android.yml` and paste the workflow from this project.
3. Open the repository's **Actions** tab, select **Build Physics 3D AI APK**, and tap **Run workflow** (or wait for the first push build).
4. When the run finishes successfully, open that run and download the `Physics3D-AI-debug-apk` artifact. GitHub may download it as a ZIP; extract it to get `app-debug.apk`.
5. Tap the APK to install. Android may ask you to allow installation from your browser or file manager; only allow it for the app you used to download the APK, then turn the permission back off afterward.

Notes: A GitHub account and internet connection are needed for the one-time cloud build and download. The installed app's supported features are designed to run offline. This is a debug APK for personal testing, not a Play Store release.
