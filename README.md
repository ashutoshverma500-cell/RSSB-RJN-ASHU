# POINT PROGRAM - Buildable repo

This repository contains the full web app and GitHub Actions workflows to produce:

- Windows EXE (Electron packaging) via `.github/workflows/build-exe.yml` using `windows-latest` runner and `electron-packager`.
- Android APK (Cordova debug build) via `.github/workflows/build-apk.yml` using `ubuntu-latest` runner with Android SDK and Cordova.

**How to use**
1. Upload this repository to GitHub as `RSSB-RJN-ASHU` (public).
2. On first push GitHub Actions will run the workflows. Artifacts (exe / apk) will be attached as workflow artifacts for download.

**Signing / Release notes**
- EXE: the created EXE will be unsigned. For code signing you need signing certificate and to adjust the packaging command.
- APK: workflow builds a debug APK. For signed release APK you must provide a keystore and set secrets (see below).

**Secrets (optional, for signed APK & auto-release):**
- `ANDROID_KEYSTORE_BASE64` - base64 of keystore file
- `ANDROID_KEYSTORE_PASSWORD`
- `ANDROID_KEY_ALIAS`
- `ANDROID_KEY_PASSWORD`
- `GITHUB_TOKEN` (default provided by Actions) used for uploads; for creating releases, GH_TOKEN may be required.

If you want, I can also push this repo to GitHub for you (you asked earlier). To do that without exposing tokens here, you can paste the ZIP into your GitHub via web UI as explained previously.
