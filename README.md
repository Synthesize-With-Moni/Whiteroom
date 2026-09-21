# Moonlit Monarch V6 — GitHub APK Builder

This is the native Android version of **Moonlit Monarch OS V6 — Soft Ascension**.

It is configured so GitHub Actions builds the APK in the cloud. You do **not** need Android Studio or AndroidIDE on your phone.

## Phone-only build

1. Create/open your GitHub repository.
2. Upload the **contents of this folder** to the repository root (not the ZIP file itself).
3. Make sure `.github/workflows/build-apk.yml` is uploaded too.
4. Commit the files to `main` (or `master`).
5. Open the repository → **Actions** → **Build Monarch APK**.
6. Open the successful workflow run.
7. Under **Artifacts**, download **Monarch-debug-apk**.
8. Extract the downloaded artifact and install `app-debug.apk` on your Android phone.

You can also start a build manually from **Actions → Build Monarch APK → Run workflow**.

## What gets built

- Real Android APK (native Android app shell)
- Moonlit Monarch V6 loaded from the app's bundled assets
- Offline operation after installation
- No Chrome/PWA dependency
- Debug APK is uploaded as a GitHub Actions artifact

## Project details

- Application ID: `com.moonlit.monarch.debug` for the debug APK
- Target SDK: 35
- Minimum SDK: 23
- Java: 17
- Android Gradle Plugin: 8.5.2
- Gradle used by GitHub Actions: 8.7

## Important

Upload the **files and folders inside this project** to GitHub. GitHub Actions cannot build an APK from a ZIP sitting in the repository unless you add an extraction step.

The workflow intentionally uses the installed Gradle 8.7 distribution instead of relying on a Gradle wrapper JAR, which keeps this phone-uploadable project simpler.
