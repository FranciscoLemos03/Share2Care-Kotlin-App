# Share2Care - Community Support Platform

## Project Description

**Share2Care** is an Android mobile application built with Kotlin and Jetpack Compose that serves as a comprehensive community support platform. It facilitates the management of social aid, user profiles, announcements, tickets, and check-in/check-out systems for social support organizations. The application leverages Firebase for authentication, real-time database management, and cloud storage, providing a seamless experience for both administrators and beneficiaries.

During the development of **Share2Care**, we collected various requirements from the [São Lázaro and São João de Souto social store](https://www.facebook.com/lojasocialsaolazaro/) so that the app would meet the requirements that the social store was looking for to optimize the collection of requirements.

---

## Project Design and Documentation

To understand how the project was planned before being developed, the `/Report&Diagrams` folder contains all the diagrams created and the project report.

---

## Main Features

- **User Authentication**: Secure Firebase-based authentication with login and registration
- **Role-Based Access Control**: Different interfaces for admin and beneficiary users
- **Beneficiary Management**: Create, view, edit, and delete beneficiary profiles
- **Announcement System**: Post and manage community announcements
- **Check-In/Check-Out Tracking**: Monitor user attendance and presence
- **Ticket Management**: Create and manage support tickets
- **Aggregate of beneficiaries Management**: Manage beneficiaries per aggregate
- **Analytics & Reports**: View statistical data through interactive charts
- **Real-Time Database**: Firestore integration for real-time data synchronization
- **Cloud Storage**: Firebase storage for image uploads and management
- **Responsive UI**: Modern Jetpack Compose-based user interface

## Installation & Setup Instructions

### Prerequisites
- Android Studio (latest version)
- JDK 11 or higher
- Android SDK API 35
- Firebase account

### Step 1: Clone the Repository
```bash
git clone https://github.com/FranciscoLemos03/Share2Care-Kotlin-App.git
cd Share2Care-Kotlin-App/Share2Care
```

### Step 2: Firebase Setup
1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or use an existing one
3. Add an Android app to your project
4. Download the `google-services.json` file
5. Place the `google-services.json` file in the `app/` directory

### Step 3: Configure Local Environment
1. Open the project in Android Studio
2. Let Gradle sync automatically (or manually sync via `File > Sync Now`)
3. Ensure the Gradle wrapper is executable:
   ```powershell
   ./gradlew --version
   ```

### Step 4: Build & Run
```bash
# Build the application
./gradlew build

# Install on connected device/emulator
./gradlew installDebug

# Or run directly
./gradlew runDebug
```

### Step 5: Emulator Setup (if not using a physical device)
1. In Android Studio, go to `AVD Manager`
2. Create a new Virtual Device with API 25 or higher
3. Start the emulator
4. Run the app via `./gradlew runDebug`

---

---

## Tech Stack / Technologies Used

### Frontend & UI
- **Language**: Kotlin 2.0.0
- **UI Framework**: Jetpack Compose (Material 3)
- **Navigation**: Androidx Navigation Compose v2.8.4
- **Material Design**: Material 3 components

### Backend & Services
- **Backend Platform**: Firebase
  - Firebase Authentication (v23.1.0)
  - Cloud Firestore (v25.1.1)
  - Firebase Storage (v21.0.1)
- **Database**: Cloud Firestore (NoSQL)

### Architecture & Libraries
- **Architecture**: MVVM (Model-View-ViewModel) with LiveData
- **Lifecycle Management**: Androidx Lifecycle components (v2.8.7)
- **ViewModels**: Androidx ViewModel & LiveData integration
- **Image Loading**: Coil v2.4.0 (image composition library)
- **Charts**: MPAndroidChart v3.1.0 (data visualization)

### Build & Testing
- **Build System**: Gradle (AGP 8.7.2)
- **Kotlin Gradle Plugin**: v2.0.0
- **Compose Plugin**: Kotlin Compose Plugin v2.0.0
- **Testing Frameworks**:
  - JUnit 4 (v4.13.2)
  - Androidx Test (JUnit v1.2.1, Espresso v3.6.1)
  - Compose UI Testing

### Target Environment
- **Minimum SDK**: API 25 (Android 7.0)
- **Target SDK**: API 35 (Android 15)
- **Compile SDK**: API 35
- **Java Version**: JDK 11
- **JVM Target**: 11

---

## Project Structure

```
Share2Care-Kotlin-App/
├── Share2Care/                          # Main project directory
│   ├── app/
│   │   ├── build.gradle.kts            # App-level build configuration
│   │   ├── google-services.json        # Firebase configuration (add this file)
│   │   ├── proguard-rules.pro          # ProGuard obfuscation rules
│   │   └── src/
│   │       └── main/
│   │           ├── AndroidManifest.xml # App manifest
│   │           └── java/com/example/share2care/
│   │               ├── MainActivity.kt              # Entry point
│   │               ├── AppNavigation.kt            # Navigation setup
│   │               ├── AuthViewModel.kt           # Authentication logic
│   │               ├── FirestoreViewModel.kt      # Firestore operations
│   │               ├── pages/                     # UI pages (Composables)
│   │               │   ├── LoginPage.kt
│   │               │   ├── RegisterPage.kt
│   │               │   ├── HomePage.kt
│   │               │   ├── BeneficiariosManagementPage.kt
│   │               │   ├── CreateBeneficiarioPage.kt
│   │               │   ├── EditBeneficiarioPage.kt
│   │               │   ├── BeneficiarioProfilePage.kt
│   │               │   ├── AnnounceManagementPage.kt
│   │               │   ├── CreateAnnouncePage.kt
│   │               │   ├── AnnounceDetailsPage.kt
│   │               │   ├── AgregadoManagementPage.kt
│   │               │   ├── CreateAgregadoPage.kt
│   │               │   ├── EditAgregadoPage.kt
│   │               │   ├── AgregadoDetailsPage.kt
│   │               │   ├── TicketsPage.kt
│   │               │   ├── CreateTicketPage.kt
│   │               │   ├── CheckInPage.kt
│   │               │   ├── CheckOutPage.kt
│   │               │   ├── Reports.kt
│   │               │   └── ...
│   │               └── ui/
│   │                   ├── components/             # Reusable UI components
│   │                   │   ├── Anuncio.kt
│   │                   │   ├── AnuncioHighlight.kt
│   │                   │   ├── AnnounceForAdmin.kt
│   │                   │   ├── BeneficiarioDataField.kt
│   │                   │   ├── CircleButton.kt
│   │                   │   └── ...
│   │                   └── theme/                  # Theme configuration
│   ├── gradle/
│   │   ├── libs.versions.toml                     # Dependency version catalog
│   │   └── wrapper/
│   │       └── gradle-wrapper.properties
│   ├── build.gradle.kts                           # Root build configuration
│   └── settings.gradle.kts                        # Project settings
├── Report&Diagrams/
│   └── Diagrams/
│       ├── Estados/                               # State diagrams
│       ├── Sequencia/                             # Sequence diagrams
│       └── ...                                    # More diagrams
└── README.md                                      # This file
```

---

## Environment Variables / Configuration

### Firebase Configuration
The app requires `google-services.json` for Firebase integration:
- **Location**: `app/google-services.json`
- **Source**: Firebase Console → Project Settings → Download

### Build Configuration
Update values in `gradle.properties` if needed:
```properties
# Android configuration
android.useAndroidX=true
android.enableJetifier=true

# Build cache
android.enableBuildCache=true
```

### Local Build Variants
Edit `app/build.gradle.kts` to configure build types:
- **Debug**: For development with full logging
- **Release**: Optimized build with ProGuard obfuscation

---

### Acknowledgements
- Firebase team for excellent backend services
- Jetpack Compose team for modern UI framework
- Material Design 3 team for design components
- Android community for valuable resources and libraries
- Contributors and testers

### Libraries & Dependencies
- Google Firebase
- Jetpack Compose
- Material Design 3
- MPAndroidChart
- Coil
- Kotlin Coroutines

---
