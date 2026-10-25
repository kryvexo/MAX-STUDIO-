<div align="center">
  <img src="assets/banner.png" alt="MAX STUDIO" width="760" />

  <h1>MAX STUDIO</h1>
  <p><strong>A customizable Android music experience with modern playback, synchronized lyrics, and a choice of visual styles.</strong></p>

  <p>
    <a href="https://github.com/kryvexo/MAX-STUDIO-/releases"><img src="https://img.shields.io/badge/version-1.5.16-6750A4?style=for-the-badge" alt="Version 1.5.16" /></a>
    <img src="https://img.shields.io/badge/platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android" />
    <a href="LICENSE"><img src="https://img.shields.io/badge/license-GPL--3.0-2F6F9F?style=for-the-badge" alt="GPL-3.0 license" /></a>
  </p>

  <p>
    <a href="https://github.com/kryvexo/MAX-STUDIO-/releases">Releases</a> ·
    <a href="https://github.com/kryvexo/MAX-STUDIO-/issues">Issues & feature requests</a> ·
    <a href="PRIVACY_POLICY.md">Privacy policy</a>
  </p>
</div>

---

## About

MAX STUDIO is an open-source Android music app focused on flexible playback and a personal listening experience. It brings together online music discovery, local playback, lyrics, and extensive interface customization in one app.

The app's application ID is `com.max.music`. The current source version is **1.5.16** and supports **Android 8.0 (API 26) and newer**.

> MAX STUDIO is an independent project. It is not affiliated with YouTube, Google, Spotify, Apple, or other third-party services. It does not host music or video files; all third-party content and trademarks remain the property of their respective owners.

## Screenshots

| Home | Material 3 player | Liquid Glass player |
|:---:|:---:|:---:|
| <img src="Screenshots/Home.png" alt="MAX STUDIO home screen" width="220" /> | <img src="Screenshots/Material%20you%20music%20page.png" alt="Material 3 music player" width="220" /> | <img src="Screenshots/Liquid%20Glass%20Apple%20Inspired.png" alt="Liquid Glass player" width="220" /> |

| Synchronized lyrics | Search & explore | Liquid Glass while scrolling |
|:---:|:---:|:---:|
| <img src="Screenshots/lyrics.png" alt="Synchronized lyrics" width="220" /> | <img src="Screenshots/search%20page.png" alt="Search and explore" width="220" /> | <img src="Screenshots/Liquid%20Glass%20Apple%20Inspired%20%28While%20Scrolling%29.png" alt="Compact Liquid Glass navigation while scrolling" width="220" /> |

## Highlights

- **Flexible playback:** background playback, queue controls, crossfade, and support for local music.
- **Offline listening:** manage supported downloads from the app's download interface.
- **Lyrics:** synchronized lyrics, multiple display styles, and optional translation-provider integrations.
- **Discovery:** browse music and use Echo Find for music recognition.
- **Music Flow:** move between navigation tabs with horizontal swipes, including the compact iOS-style floating tab bar while scrolling.
- **Personalization:** Material 3 styling, Liquid Glass effects, player layouts, themes, and custom launcher icons.
- **Connected features:** optional Spotify and other third-party integrations; availability depends on service configuration and region.
- **About download stats:** view the cumulative download count for public APK assets on the MAX STUDIO GitHub Releases page. This is a download metric, **not** a count of unique or currently active users.

Some integrations require an account, API key, or network access. Availability and behavior can change when third-party services change.

## Download and install

1. Open the [GitHub Releases page](https://github.com/kryvexo/MAX-STUDIO-/releases).
2. Download the latest published Android APK.
3. Open the APK on your device and follow Android's installation prompts. Android may ask you to allow your browser or file manager to install apps.

To update an existing installation, Android requires the same package ID and signing certificate. If the APK is signed with a different key, Android may refuse the update. Back up important app data before uninstalling an existing build.

## Build from source

### Requirements

- Android Studio or Android SDK command-line tools
- **JDK 21**
- Android SDK platform **API 37** and the project-required build tools
- Git

### Get the source

```bash
git clone https://github.com/kryvexo/MAX-STUDIO-.git
cd MAX-STUDIO-
cp local.properties.template local.properties
```

Edit `local.properties` and set your local Android SDK path:

```properties
sdk.dir=/path/to/your/Android/Sdk
```

On Windows, use `gradlew.bat` in place of `./gradlew`.

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

Release builds require your own signing key. Configure it through environment variables and never commit the keystore or passwords:

```bash
export KEYSTORE_PATH=/path/to/release-key.jks
export STORE_PASSWORD=your_store_password
export KEY_ALIAS=your_key_alias
export KEY_PASSWORD=your_key_password
./gradlew assembleUniversalFossRelease
```

Build outputs are written under `app/build/outputs/apk/`.

## Privacy

Review [PRIVACY_POLICY.md](PRIVACY_POLICY.md) for the project's stated data practices and third-party services. Features may connect to the services you choose to use. The About-page download counter requests aggregate public release metadata from GitHub; it does not identify active users, though GitHub receives ordinary network request metadata such as the device's IP address.

## Contributing and support

Bug reports and feature requests are welcome through [GitHub Issues](https://github.com/kryvexo/MAX-STUDIO-/issues). Before opening an issue, check whether it has already been reported. For code contributions, see [CONTRIBUTING.md](CONTRIBUTING.md) and follow the project conventions.

See the [contributors page](https://github.com/kryvexo/MAX-STUDIO-/graphs/contributors) and the source notices for project contributors and dependency attributions. MAX STUDIO also acknowledges the open-source work of [Metrolist](https://github.com/MetrolistGroup/Metrolist), [Vivi Music](https://github.com/vivizzz007/vivi-music), [ArchiveTune](https://github.com/koiverse/ArchiveTune), [Better Lyrics](https://better-lyrics.boidu.dev/), [SimpMusic](https://github.com/maxrave-dev/SimpMusic), [Music Recognizer](https://github.com/aleksey-saenko/MusicRecognizer), and [BravePipe](https://github.com/bravepipeproject/BravePipe). Each project remains subject to its own license and notices.

## License

MAX STUDIO is distributed under the **GNU General Public License v3.0**. See the [LICENSE](LICENSE) file for the complete terms. Third-party components and assets may carry their own licenses.
