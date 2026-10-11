# Tủ Đồ Ảo — Android build

This repository wraps the supplied Tủ Đồ Ảo PWA v8 in a native Android WebView. The PWA is bundled locally at `android/app/src/main/assets/www/`, so the core UI opens without hosting. Internet access remains available for remote resources such as Google Fonts.

## Build APK on GitHub
1. Upload the contents of this ZIP to the root of a GitHub repository (keep `.github/` and `android/` at repository root).
2. Open **Actions → Build debug APK → Run workflow** (or push to `main`/`master`).
3. Open the successful run and download the `tudoao-debug-apk` artifact. It contains `app-debug.apk`.

## Build locally
Install JDK 17 and Android SDK Platform 35, then from the repository root run:

```sh
gradle -p android assembleDebug
```

APK output: `android/app/build/outputs/apk/debug/app-debug.apk`.

## Data and limitations
The app uses WebView DOM storage/localStorage, so wardrobe data stays on the device and is not automatically synchronized across devices. This is a debug APK workflow, not a Play Store release/signing setup. Test photo/file upload and any device-specific behavior on a real phone before release.

## File and camera access (v9 permission fix)
The Android wrapper implements WebView's `onShowFileChooser`, so the wardrobe's hidden image inputs open the Android system photo picker/document picker. Inputs marked `capture="environment"` also offer the camera app and pass a FileProvider URI for full-size output. This uses Android's Storage Access Framework for user-selected images; it deliberately does not request broad storage permissions. Launching the external camera app does not require the app to request the `CAMERA` runtime permission.

After updating this source, rebuild the APK and test both **Chụp ảnh mới** and **Chọn từ thư viện** on the target phone.
