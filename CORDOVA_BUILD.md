# Building iOS & Android Apps with Apache Cordova

This guide walks you through creating native iOS and Android apps from
your single-page HTML calculator.

## Prerequisites

* **Node.js & npm** – download from https://nodejs.org/
* **Xcode** (macOS, for iOS) – install from App Store or https://developer.apple.com/download/
* **Android Studio** – download from https://developer.android.com/studio
* **Java Development Kit (JDK)** – required for Android

Verify your setup:

```bash
node --version
npm --version
xcode-select --install  # macOS
```

## Step 1: Install Cordova

```bash
npm install -g cordova
cordova --version
```

## Step 2: Create a Cordova Project

From your workspace parent directory (or anywhere you like):

```bash
cordova create neck-facet-app com.example.neckfacet "Neck Facet Calculator"
cd neck-facet-app
```

This scaffolds a new Cordova project with the package name
`com.example.neckfacet` (change it to something unique if you plan to
publish).

## Step 3: Replace the Default App with Your Calculator

Your new project has a `www/` folder containing the default app. Replace
it with your calculator:

```bash
# Back up the default www
mv www www.bak

# Copy your project into www
cp -r /Users/tsurankov/workspace/neck-facet-calculator www

# Keep only index.html and assets; remove README, LICENSE, etc. if desired
cd www
rm -f README.md LICENSE CORDOVA_BUILD.md
cd ..
```

Alternatively, manually copy `index.html` into `www/index.html` and any
assets (fonts, images) into `www/`.

## Step 4: Add Platforms

### iOS

```bash
cordova platform add ios
```

### Android

```bash
cordova platform add android
```

Both commands create platform-specific folders (`platforms/ios/` and
`platforms/android/`).

## Step 5: Build

### iOS

```bash
cordova build ios
```

This generates an `.xcodeproj` in `platforms/ios/`. You can then open
it in Xcode:

```bash
open platforms/ios/neckfacetapp.xcodeproj
```

From Xcode, select a simulator or device and press **Play** to run.

### Android

```bash
cordova build android
```

This generates an APK in
`platforms/android/app/build/outputs/apk/debug/app-debug.apk`.

To test on a connected device or emulator:

```bash
cordova run android
```

(Make sure an Android emulator is running or a device is plugged in with
USB debugging enabled.)

## Step 6: Test & Iterate

As you edit `www/index.html` or other files, rebuild:

```bash
cordova build ios
cordova build android
```

Or run directly:

```bash
cordova run ios
cordova run android
```

## Notes

* **Plugins** – if you later need device features (camera, geolocation,
  etc.), install Cordova plugins (e.g., `cordova plugin add
  cordova-plugin-camera`).
* **Config** – edit `config.xml` to set the app name, description, author,
  icon, and splash screen.
* **iOS Code Signing** – you'll need an Apple Developer account and valid
  provisioning profiles to build for a real device.
* **Android Release Build** – for the Play Store, create a release APK
  with signing keys (see Android documentation).

## Troubleshooting

* `xcode-select: error: tool 'xcodebuild' not found` – run `xcode-select
  --install`.
* `Could not find gradle` – install Android Studio and set
  `ANDROID_SDK_ROOT` in your shell profile.
* App loads blank – check browser console (in iOS Simulator or Android
  emulator) for errors; verify `www/index.html` exists and is valid.

For detailed docs, see https://cordova.apache.org/docs/en/latest/
