# GiftU for Android

GiftU is a small, fully offline Android birthday-greeting application. It opens to a cheerful “Happy Birthday to You” message over a colorful animated confetti background.

## Application details

| Item | Value |
| --- | --- |
| Application name | GiftU |
| Version | 1.1.0 |
| Version code | 2 |
| Package ID | `com.macleanofduartenterprises.giftu` |
| Minimum Android version | Android 6.0 (API 23) |
| Target Android version | Android 15 (API 35) |
| Internet connection required | No |

## Features

- Displays the message “Happy Birthday to You” in a centered, easy-to-read card.
- Produces colorful confetti bursts automatically while the app is visible.
- Pops additional confetti wherever the user taps the background.
- Uses multiple confetti colors, shapes, rotations, gravity, fading, and expanding burst rings.
- Limits the number of active particles to maintain smooth performance.
- Pauses animation when the app is no longer visible to reduce battery and processor use.
- Uses a balloon-and-confetti vector launcher icon.
- Operates entirely on the device without third-party libraries or online services.

## Privacy and permissions

GiftU requests no Android permissions. It does not contain Internet access, advertising, analytics, account integration, tracking, or cloud services. Android application backup is disabled, and cleartext network traffic is disabled.

## Installation

1. Download `GiftU-1.1.0-Confetti-Signed.apk` to the Android device.
2. If Android asks, allow the file-opening application to install unknown apps.
3. Open the APK and select **Install**.
4. Open **GiftU** from the launcher.
5. Tap anywhere outside the message card to create extra confetti bursts.

If Android reports that the app cannot be updated, an installed copy may use the same package ID but a different signing key. Uninstalling that copy should permit installation, but uninstalling also removes its local application data.

## Building from source

### Requirements

- Android Studio with Android SDK 35
- Java Development Kit 17
- Android Gradle Plugin 8.7.3
- A compatible Gradle installation or Android Studio’s managed Gradle environment

### Build steps

1. Extract `GiftU-Android-Source-1.1.0-Confetti.zip`.
2. Open the `HappyBirthdayApp` directory in Android Studio.
3. Allow the Gradle project to synchronize.
4. Select **Build > Build APK(s)** for a debug build.
5. For a release build, use **Build > Generate Signed App Bundle or APK** and select an authorized private signing key.

The source package does not contain the private signing key or its credentials. Keep release keys and passwords outside source control.

## Project structure

```text
HappyBirthdayApp/
├── build.gradle.kts
├── settings.gradle.kts
├── README.txt
└── app/
    ├── build.gradle.kts
    └── src/main/
        ├── AndroidManifest.xml
        ├── java/com/macleanofduartenterprises/giftu/
        │   ├── MainActivity.java
        │   └── ConfettiView.java
        └── res/
            ├── drawable/happy_birthday_icon.xml
            └── values/styles.xml
```

`MainActivity.java` creates the birthday-message interface. `ConfettiView.java` provides the dependency-free Canvas animation, automatic bursts, tap interaction, particle physics, and lifecycle-aware pausing.

## Release verification

The supplied release APK was zip-aligned and successfully verified with Android APK Signature Schemes v1, v2, and v3.

- APK: `GiftU-1.1.0-Confetti-Signed.apk`
- APK SHA-256: `8716e347f17fa3f359849773d159538836b789e926f238c58610dbce3aaf2400`
- Signing certificate SHA-256: `62ebb3c5d7d722b2e1174a4622f7593926204579084f94e11151ef606b32d136`

## Version history

### 1.1.0

- Added the animated confetti-popping background.
- Added tap-controlled confetti bursts.
- Added lifecycle-aware animation pausing and a bounded particle count.
- Updated the central birthday-message presentation and system-bar colors.

### 1.0.0

- Initial fully offline release displaying “Happy Birthday to You.”
