<div align="center">
  <h1>MAX STUDIO</h1>
  <p><strong>Your music. Your flow. Your interface.</strong></p>
  <p>A customizable Android music experience with modern playback, synchronized lyrics, and a choice of visual styles.</p>

  <p>
    <a href="https://github.com/kryvexo/MAX-STUDIO-/releases/latest"><img src="https://img.shields.io/github/v/release/kryvexo/MAX-STUDIO-?style=for-the-badge&label=Latest%20release" alt="Latest GitHub release" /></a>
    <a href="https://github.com/kryvexo/MAX-STUDIO-/stargazers"><img src="https://img.shields.io/github/stars/kryvexo/MAX-STUDIO-?style=for-the-badge&logo=github&label=Stars" alt="GitHub stars" /></a>
    <a href="LICENSE"><img src="https://img.shields.io/github/license/kryvexo/MAX-STUDIO-?style=for-the-badge" alt="GPL-3.0 license" /></a>
    <img src="https://img.shields.io/badge/Android-API%2026%2B-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android 8.0 and newer" />
  </p>

  <p>
    <a href="https://github.com/kryvexo/MAX-STUDIO-/releases/latest"><strong>Download APK</strong></a> ·
    <a href="https://github.com/kryvexo/MAX-STUDIO-">Browse source</a> ·
    <a href="https://github.com/kryvexo/MAX-STUDIO-/issues">Report an issue</a>
  </p>
</div>

---

## Overview

MAX STUDIO is an open-source Android music app built around flexible listening and deep personalization. Explore music, play local tracks, follow synchronized lyrics, and shape the interface to suit your style.

| Project detail | Value |
|:--|:--|
| Current source version | `1.5.16` |
| Android package | `com.max.music` |
| Minimum Android version | Android 8.0 · API 26 |
| Main technologies | Kotlin · Jetpack Compose · Gradle |
| License | GNU GPL v3.0 |

## Screenshots

The gallery below loads directly from the repository's **`main/SCREENSHOTS`** folder. Replacing an image in that folder updates the image shown here.

<p align="center">
  <a href="https://github.com/kryvexo/MAX-STUDIO-/blob/main/SCREENSHOTS/Screenshot_2026-10-25-08-50-42-859_com.max.music.jpg"><img src="https://raw.githubusercontent.com/kryvexo/MAX-STUDIO-/main/SCREENSHOTS/Screenshot_2026-10-25-08-50-42-859_com.max.music.jpg" alt="MAX STUDIO home screen with Music Flow and floating navigation" width="220" /></a>
  &nbsp;&nbsp;
  <a href="https://github.com/kryvexo/MAX-STUDIO-/blob/main/SCREENSHOTS/Screenshot_2026-10-25-08-51-13-101_com.max.music.jpg"><img src="https://raw.githubusercontent.com/kryvexo/MAX-STUDIO-/main/SCREENSHOTS/Screenshot_2026-10-25-08-51-13-101_com.max.music.jpg" alt="About screen featuring Developed by MAX" width="220" /></a>
  &nbsp;&nbsp;
  <a href="https://github.com/kryvexo/MAX-STUDIO-/blob/main/SCREENSHOTS/Screenshot_2026-10-25-08-51-18-838_com.max.music.jpg"><img src="https://raw.githubusercontent.com/kryvexo/MAX-STUDIO-/main/SCREENSHOTS/Screenshot_2026-10-25-08-51-18-838_com.max.music.jpg" alt="App update settings and release notes" width="220" /></a>
</p>
<p align="center"><sub>Home & Music Flow · About · Update settings</sub></p>

<p align="center">
  <a href="https://github.com/kryvexo/MAX-STUDIO-/blob/main/SCREENSHOTS/Screenshot_2026-10-25-08-50-59-825_com.max.music.jpg"><img src="https://raw.githubusercontent.com/kryvexo/MAX-STUDIO-/main/SCREENSHOTS/Screenshot_2026-10-25-08-50-59-825_com.max.music.jpg" alt="Landscape player with synchronized Hindi lyrics" width="760" /></a>
</p>
<p align="center"><sub>Landscape playback with synchronized lyrics</sub></p>

> **Screenshot note:** The About and Update Settings captures display version 1.5.3. They are representative UI images and may not show the current source version.

## Features

- **Flexible playback:** background listening, queue controls, crossfade, and local music support.
- **Offline listening:** manage supported downloads through the app's download interface.
- **Synchronized lyrics:** follow lyrics while listening, with multiple display styles and optional translation-provider integrations.
- **Music discovery:** browse music and use Echo Find for music recognition.
- **Music Flow navigation:** swipe between tabs, including the compact iOS-style floating bar while it shrinks during scrolling.
- **Personalization:** Material 3 styling, Liquid Glass effects, player layouts, themes, and custom launcher icons.
- **Connected services:** optional Spotify and other integrations; availability depends on service configuration and region.
- **About download stats:** see cumulative downloads for public APK assets on GitHub Releases. This is a download total, **not** a count of unique or currently active users.

Some features need a network connection, account, or API key. Third-party service behavior and availability can change independently of MAX STUDIO.

## Download and install

1. Visit [GitHub Releases](https://github.com/kryvexo/MAX-STUDIO-/releases/latest).
2. Download the latest published Android APK.
3. Open the APK on your device and follow Android's installation prompts. You may need to allow your browser or file manager to install apps.

Android updates require the same package ID and signing certificate as the installed build. If Android refuses an update because the signing key differs, back up important app data before removing the existing version.

## Build from source

### Requirements

- Android Studio or Android SDK command-line tools
- JDK 21
- Android SDK Platform API 37 and the build tools required by the project
- Git

### Clone and configure

```bash
git clone https://github.com/kryvexo/MAX-STUDIO-.git
cd MAX-STUDIO-
cp local.properties.template local.properties
```

Edit `local.properties` and set the path to your Android SDK:

```properties
sdk.dir=/path/to/your/Android/Sdk
```

On Windows, use `gradlew.bat` instead of `./gradlew`.

### Build variants

The project provides FOSS and GMS variants. FOSS builds omit Google Play Services-dependent functionality such as Cast; GMS builds include Google-dependent integrations.

```bash
# Universal FOSS debug APK
./gradlew assembleUniversalFossDebug

# Universal GMS debug APK
./gradlew assembleUniversalGmsDebug

# FOSS unit tests
./gradlew :app:testUniversalFossDebugUnitTest
```

A release APK needs your own signing key. Keep the keystore and credentials private; never commit them to GitHub.

```bash
export KEYSTORE_PATH=/path/to/release-key.jks
export STORE_PASSWORD=your_store_password
export KEY_ALIAS=your_key_alias
export KEY_PASSWORD=your_key_password
./gradlew assembleUniversalFossRelease
```

APK outputs are written under `app/build/outputs/apk/`.

## Privacy and third-party services

Read [PRIVACY_POLICY.md](PRIVACY_POLICY.md) for the project's stated data practices. MAX STUDIO may connect to the third-party services you choose to use. The About-page counter requests public release metadata from GitHub; it does not identify active users, although GitHub receives ordinary network request metadata such as the device's IP address.

## Contributing

Bug reports and feature requests are welcome through [GitHub Issues](https://github.com/kryvexo/MAX-STUDIO-/issues). Please search existing issues before opening a new one. See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines and the [contributors page](https://github.com/kryvexo/MAX-STUDIO-/graphs/contributors) to acknowledge project contributors.

MAX STUDIO also acknowledges the open-source work of [Metrolist](https://github.com/MetrolistGroup/Metrolist), [Vivi Music](https://github.com/vivizzz007/vivi-music), [ArchiveTune](https://github.com/koiverse/ArchiveTune), [Better Lyrics](https://better-lyrics.boidu.dev/), [SimpMusic](https://github.com/maxrave-dev/SimpMusic), [Music Recognizer](https://github.com/aleksey-saenko/MusicRecognizer), and [BravePipe](https://github.com/bravepipeproject/BravePipe). Each project remains subject to its own license and notices.

## License and disclaimer

MAX STUDIO is distributed under the [GNU General Public License v3.0](LICENSE). Third-party components and assets may have separate licenses.

MAX STUDIO is an independent project and is not affiliated with YouTube, Google, Spotify, Apple, or other third-party services. It does not host music or video files. Users are responsible for complying with applicable laws and third-party service terms.
