# Auto-Resto - Downloads

Public APK builds of **Auto-Resto**, an Android app that automates university
restaurant reservations.

The application source code is kept in a **private** repository.

## Download

Latest build: `AutoResto-1.001.apk`

1. Download `AutoResto-1.001.apk` from this repository
2. Open it on your Android phone and allow installation from this source if asked
3. Sign in with your university restaurant account

If a newer build exists, the app offers the update itself from inside the app
(Settings, or automatically a few seconds after launch).

## Update feed

`version.json` is what the installed app reads to decide whether an update
exists. The app shows the update window only when `versionCode` in that file is
greater than the code of the installed build.

```
versionCode = major * 1000 + minor      v1.001 = 1001, v1.002 = 1002
```

Rules for a new release:

1. Bump `versionCode` (always higher than the previous one) and `versionName`
2. Build with the same signing key, otherwise the update cannot install over the
   previous build
3. Upload `AutoResto-<versionName>.apk`
4. Update `version.json` with the new code, name, URL, and the SHA-256 of the APK
5. Commit and push, then check the raw feed serves the new file

Keep the old APK files in place, only `version.json` moves forward. To withdraw a
release, point `version.json` back to the previous code, or delete the file.

## Notes

- Android 8.0 (API 26) or newer
- Credentials are stored encrypted on the device (Android Keystore)
- The app needs notification, exact-alarm and battery-optimisation exceptions to
  run the automatic reservation in the background

## Author

Made by : Aymen B.
