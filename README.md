# Documentary Android APK project

This Android project packages the latest Documentary web app HTML inside a native Android WebView. The page is served from AndroidX WebViewAssetLoader over a secure app-assets origin, allowing normal HTTPS requests to Supabase and other services.

## Build the APK using GitHub Actions

1. Create a new GitHub repository (or a separate `android-app` repository) for this Android project.
2. Upload **all files and folders in this project** to the repository root. Keep `.github/workflows/build-apk.yml` in place.
3. Open the repository's **Actions** tab and select **Build Documentary APK**.
4. If prompted, enable Actions, then press **Run workflow**.
5. Wait for the run to finish successfully. Open the completed run and download the `Documentary-debug-apk` artifact.
6. Extract the downloaded ZIP. It contains `app-debug.apk`. Transfer that APK to your Android phone and install it. Android may ask you to allow installation from the browser or file manager you used.

A push to `main` or `master` also triggers a build automatically.

## App details

- App name: Documentary
- Application ID: `com.documentary.app`
- Version: `1.0.0`
- Minimum Android: Android 6.0 (API 23)
- Build output: `app/build/outputs/apk/debug/app-debug.apk`

## Important notes

- This is a **debug APK** for testing and direct installation. Publishing on Google Play requires a signed release App Bundle/APK and Play Console setup.
- Supabase, payments, external images, and other hosted services still require an internet connection. The offline page can display while the phone is offline, but server-backed feed content cannot load without connectivity.
- Do not put Supabase service-role keys or payment secret keys in the HTML or Android app. Keep privileged keys on secure server-side functions.
- The app requests internet access. Photo/document selection is supported through Android's file picker.
