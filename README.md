# MAX STUDIO

MAX STUDIO is a modern Android music player focused on a clean listening experience, local music playback, YouTube music integration, customization, and direct release updates.

> Current platform: **Android**  
> Package name: `com.max.music`  
> Current release: **v1.4.9**

## Features

- Local music library and audio playback
- YouTube music search and playback integration
- Background playback and media controls
- Playlists, queue management, radio and recommendations
- Lyrics and music metadata support
- Multiple app icon choices, including the original Sabrina Carpenter and Sadie Sink icons
- Listen Together room support
- Google/YouTube account login
- Dark theme and customizable player experience
- Built-in release update checker
- Direct APK download and installation from the app
- What's New section with release notes and fallback notes when the release asset is unavailable

## Download

Download the latest APK from the [GitHub Releases](https://github.com/kryvexo/MAX-STUDIO-/releases) page.

For the direct update system to work, each GitHub release should include:

- The release APK
- A `changelog.json` file
- Optional `SHA256SUMS.txt` checksum file

Example release assets:

```text
MAX-STUDIO-v1.4.9.apk
changelog.json
SHA256SUMS.txt
```

## Installing the APK

1. Download the APK from GitHub Releases.
2. Open the downloaded APK on your Android device.
3. If Android asks for permission, enable **Allow from this source** for the browser or file manager.
4. Install and launch MAX STUDIO.

The app may ask for the Android install-permission setting when installing an update from inside the app. This is required by Android for APK installation outside the Play Store.

## Release changelog format

Create a `changelog.json` file for every release:

```json
{
  "description": "MAX STUDIO v1.4.9 — Android 16/Xiaomi update installer crash fixed",
  "changelog": [
    "Fixed APK installation crash on Xiaomi and Android 16",
    "Restored REQUEST_INSTALL_PACKAGES in the release manifest",
    "Added a safe permission-check fallback before installation"
  ]
}
```

The app reads this file from the matching GitHub release tag. If the file cannot be downloaded, MAX STUDIO shows built-in fallback release notes instead of leaving the What's New section empty.

## Building from source

### Requirements

- Android Studio or a compatible Gradle environment
- JDK 17 or newer
- Android SDK with the required platform and build tools
- Internet connection for Gradle dependencies

### Build commands

Clone the repository and enter the project directory:

```bash
git clone https://github.com/kryvexo/MAX-STUDIO-.git
cd MAX-STUDIO-
```

Build the universal FOSS release APK:

```bash
./gradlew assembleUniversalFossRelease
```

The APK is generated at:

```text
app/build/outputs/apk/universalFoss/release/app-universal-foss-release.apk
```

For a debug build:

```bash
./gradlew assembleUniversalFossDebug
```

## Application configuration

Important Android configuration values:

```text
Application ID: com.max.music
App name: MAX STUDIO
GitHub releases: https://github.com/kryvexo/MAX-STUDIO-/releases
```

When publishing a new release:

1. Increase `versionCode` in `app/build.gradle.kts`.
2. Update `versionName`.
3. Build the signed release APK.
4. Create a GitHub release with a matching tag such as `v1.5.0`.
5. Upload the APK and `changelog.json`.
6. Verify that the release asset URLs are publicly accessible.

The version tag and `versionName` should match. For example:

```text
versionName = "1.5.0"
GitHub tag = v1.5.0
```

## Google login

Google/YouTube login uses a WebView-based authentication flow. The app clears the login WebView session, opens Google's ServiceLogin flow, reads the authenticated YouTube cookies, and validates the account before saving it locally.

If login does not complete:

- Check the device internet connection.
- Make sure Chrome or Android System WebView is up to date.
- Try opening the login screen again.
- Do not clear the app's account data while a login attempt is running.

## iOS status

This repository currently contains the Android implementation only. It does not include a Swift, SwiftUI, Xcode, or iOS module.

An iOS version would need a separate native SwiftUI implementation and Apple signing through Xcode. Android APK updates cannot be installed on iOS; iOS updates must be distributed through TestFlight or the App Store.

## Project structure

```text
app/          Main Android application
core/         Shared music and data-layer components
playback/     Audio playback services
innertube/    YouTube/InnerTube integration
lyrics/       Lyrics-related functionality
metadata/     Music metadata handling
canvas/       Player visualizations and canvas components
```

## License and attribution

Keep the original project license and attribution files included in this repository. Third-party libraries and services remain subject to their respective licenses and terms.

Before distributing a public build, review the licenses, artwork rights, music-service terms, and platform requirements applicable to your release.

## Support

For MAX STUDIO project updates and release information, visit:

- Website: https://maxown.c0m.in
- GitHub: https://github.com/kryvexo/MAX-STUDIO-
- Telegram: `@kryvexo`
- Twitter/X: `@kryvexo`
- Instagram: `@maxgotiissues`
