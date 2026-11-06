# Team Everest — Secure Login App

**Built in 24 hours | Hackathon project (2025) | Android / Flutter prototype**

Team Everest is a hackathon prototype exploring a simple idea: **a password alone should not be enough to approve a sensitive action**. The project presents a mobile-based approval experience that uses the Android device's fingerprint authentication as an additional security check for login and device-access requests.

> **Hackathon prototype, not a production security product.** This repository preserves the Android release build and the team's presentation. It does **not** currently include the original Flutter/Dart source code or a verified backend implementation.

## 🎬 Demo and project materials

- **[Watch the demo on YouTube](https://www.youtube.com/shorts/J3sy4jwVp-c)**
- **[Download the Android APK](apk/release/app-release.apk)**
- **[View the hackathon presentation](hackathon2025.pptx)**

## 💡 The problem

Passwords can be guessed, stolen, or shared. For sensitive actions—such as signing in to an account or allowing device access—we wanted to explore a second check that requires the device owner's approval.

During a **24-hour hackathon**, our team designed and packaged an Android proof of concept around that challenge. The focus was on communicating an approachable biometric-approval flow and demonstrating a working mobile prototype within a tight deadline.

## 🔐 Project concept

The team's presentation describes this high-level flow:

1. A user attempts a login or requests access to a protected device or activity.
2. The mobile app presents an approval/verification step.
3. The owner authenticates using the phone's fingerprint sensor through Android's biometric mechanism.
4. Access is approved only after successful verification.

**Scope note:** This is the **intended workflow presented at the hackathon**, not a claim that a complete, independently verified cross-device authentication service or live transaction-processing backend is present in this repository.

### Use cases discussed at the hackathon

| Use case | Idea |
| --- | --- |
| **Secure login** | Add device-owner biometric verification beyond a password. |
| **Device / parental approval** | Explore requiring a parent's approval before protected device use. |
| **Approval notifications** | Show how immediate requests and alerts could keep the owner informed. |
| **Transaction confirmation** | Illustrate how an extra mobile approval step *could* help with card-transaction security; **not an integrated payment feature**. |

## 🛠️ Technology and build details

| Item | Details |
| --- | --- |
| Mobile framework | **Flutter** (indicated by the generated build files and plugin metadata) |
| Target platform | Android |
| Biometric support | Android `local_auth_android` plugin appears in the release manifest-merger log |
| Available build | Release APK (`app-release.apk`) |
| Build version | `1.0.0` (`versionCode: 1`) |
| Android application ID | `com.example.nwe` |

The application ID, version, and APK type come from [`apk/release/output-metadata.json`](apk/release/output-metadata.json). The listed Flutter plugin is visible in [`logs/manifest-merger-release-report.txt`](logs/manifest-merger-release-report.txt). Exact runtime behavior has not been independently tested from the artifacts.

## 📱 Try the APK

1. Download [`apk/release/app-release.apk`](apk/release/app-release.apk) from the repository.
2. Transfer the file to an Android device.
3. Open the file and follow the device's installation instructions. Android may ask you to allow installation from that source.
4. Explore the **hackathon demo build** using a test device and non-sensitive test information.

**Important:** The APK is an old hackathon artifact. It has not been audited or verified against current Android versions. Do not use it to protect real accounts, store sensitive identity information, or authorize financial transactions.

## 📂 Repository contents

```text
Team-Everest/
├── README.md                          # Project documentation
├── hackathon2025.pptx                # Original team presentation
├── apk/release/
│   ├── app-release.apk               # Android release build
│   └── output-metadata.json          # APK version and application ID
├── flutter-apk/
│   ├── app-release.apk               # Same APK published in a second location
│   └── app-release.apk.sha1
├── logs/                              # Android build logs
├── mapping/release/                  # Release build mapping/analysis artifacts
└── sdk-dependencies/release/         # Generated Android SDK dependency report
```

### Where is the source code?

The current `master` and `main` branches **do not contain the Flutter application source**, such as `lib/`, `pubspec.yaml`, or the Android project configuration needed to rebuild the app. They primarily preserve the compiled release and supporting materials. Therefore, commands such as `flutter pub get` and `flutter run` **cannot rebuild this project from the current repository**.

If the original Flutter project becomes available, it can be added separately with dependency information and reproducible development/build instructions. A compiled APK cannot simply be converted back into the original maintainable Dart codebase.

## 🚀 Future enhancements

The hackathon presentation proposed the following directions for a more complete product:

- Additional verification options such as **PIN** or voice-based authentication.
- **Daily and weekly device-usage reports**.
- **Custom time limits** and scheduled access windows.
- Improved **UI/UX**, accessibility, and user feedback.
- Clearer approval notifications and secure integration with a real identity or device-management service.

These are **ideas from the presentation**, not features claimed to be implemented in the published APK.

## 🛡️ Security and privacy

- Use the operating system's secure biometric APIs; an app should **not** collect or store raw fingerprint data.
- **Never use a Social Security number (SSN) as a password or authentication factor.** Although identity-number use was discussed in the original pitch, an SSN is sensitive personal information, not a secure login secret.
- A production version would require secure enrollment, authenticated requests, server-side verification, replay protection, careful data handling, and independent security testing.
- The credit-card approval example in the slides is **illustrative**, not evidence of real banking or payment-network connectivity.

## 👥 Team Everest

Built as a team project during a 24-hour hackathon:

- **Deepika Jirel**
- **Utsav Acharya**
- **Saroj Bhattarai**
- **Gaurav Raj Sah**
- **Anant Budhathoki**

*Team names and the project description are taken from the original [`hackathon2025.pptx`](hackathon2025.pptx) presentation.*

## 📌 Project status

This repository is a **snapshot of the hackathon prototype**, shared to document the idea, team effort, demo, and the Android build. It is not presented as a maintained or production-ready authentication solution.

Questions or feedback? Please use the repository's [Issues](https://github.com/sarojbhattaraiii/Team-Everest/issues) page.
