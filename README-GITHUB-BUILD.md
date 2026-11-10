# PremiumC8BP - GitHub Actions build

This repository is configured as a standard Android Gradle project using the existing native `jni/Android.mk` build.

## Build locally

```bash
gradle assembleDebug
```

## Build on GitHub

Push the project to GitHub. The workflow at `.github/workflows/build.yml` runs automatically on pushes and pull requests, or manually from **Actions → Android Build → Run workflow**.

The generated APK is uploaded as the `PremiumC8BP-debug-apk` workflow artifact.

## Native build

The original project uses Android NDK `21.3.6528147` and `ndk-build`. The workflow installs that NDK and the required Android 30 SDK/build-tools packages.

Only `armeabi-v7a` and `arm64-v8a` are enabled because those are the ABI-specific prebuilt curl/OpenSSL libraries included in the source tree.
