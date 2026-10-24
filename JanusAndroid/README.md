# Janus Android starter project (v0.1.0)

This Android Studio project wraps the Janus browser prototype in an Android WebView so it can be built as an APK.

## What works in this starter
- Capture and categorize reminders, tasks, thoughts, ideas, notes, and questions
- Search and filter saved entries
- Mark tasks/reminders complete, change category, read entries aloud where Android WebView supports speech synthesis
- Export/import a JSON backup and export scheduled items as an `.ics` calendar file
- Entries are stored locally on this app installation

## Not implemented yet
- Cloud sync or AI assistant backend
- Reliable scheduled Android notifications when the app is closed
- Always-on wake word / background listening
- Direct Google Calendar integration
- Zoom/meeting audio capture and summaries

Voice dictation relies on browser speech-recognition support and may not work inside the local-file WebView on every Android device. Typing and local saving are the baseline features.

## Build the APK in the cloud (no Android Studio needed)
This project includes `.github/workflows/build-apk.yml` for a GitHub Actions build.

1. Create a GitHub account if you don't have one, then create a **new repository**.
2. Upload the contents of this folder to the repository (including the hidden `.github` folder), and commit to the `main` branch.
3. Open the repository's **Actions** tab and select **Build Janus APK**. If prompted, enable workflows, then click **Run workflow**. A push to `main` or `master` also starts a build.
4. Wait for the workflow to finish successfully, open its run, and download the `janus-debug-apk` artifact.
5. Extract the downloaded artifact ZIP on your phone or computer. Install `app-debug.apk` on your Android phone. Android may ask you to allow installation from that browser/file manager.

GitHub Actions availability and limits depend on your GitHub account and repository settings. Do not upload secrets to the repository. The debug APK is for testing, not a Play Store release.

## Build locally with Android Studio
1. Install Android Studio: https://developer.android.com/studio
2. Open this folder (the folder containing `settings.gradle`).
3. Allow Gradle sync and install Android SDK platform 35 if prompted.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. The debug APK is normally at `app/build/outputs/apk/debug/app-debug.apk`.

## Privacy and limitations
- The app has no network permission and does not send entries to a server.
- App data is local to this installation. Export a backup before uninstalling or changing devices.
