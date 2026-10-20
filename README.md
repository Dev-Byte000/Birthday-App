# Greeting Card App

A modern Android application built with **Jetpack Compose** that displays a personalized birthday greeting card featuring a full-screen background image and styled text overlay.

---

## 📱 Features

- **Jetpack Compose UI**: Declarative UI built entirely with modern Android Compose components.
- **Material 3 Theme**: Integrated with Material Design 3 color schemes and typography.
- **Layered Layout**: Uses `Box` layout to overlay `GreetingText` on top of a full-screen `Image` rendered with `ContentScale.Crop`.
- **Interactive Previews**: `@Preview` composables configured for rapid visual feedback in Android Studio.
- **Edge-to-Edge Layout**: Utilizes `enableEdgeToEdge()` for an immersive full-screen presentation.

---

## 🛠️ Tech Stack & Prerequisites

- **Language**: [Kotlin](https://kotlinlang.org/)
- **UI Framework**: [Jetpack Compose](https://developer.android.com/jetpack/compose) (Material 3)
- **Min SDK**: 24 (Android 7.0 Nougat)
- **Target SDK**: 37
- **Compile SDK**: 37
- **Build System**: Gradle with Kotlin DSL (`build.gradle.kts`) & Version Catalog (`gradle/libs.versions.toml`)
- **JDK Requirement**: JDK 11 or higher

---

## 📂 Project Structure

```text
GreetingCard/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/greetingcard/
│   │   │   │   ├── MainActivity.kt               # Main Activity & Composable Functions
│   │   │   │   └── ui/theme/                     # Material 3 Theme (Color, Theme, Type)
│   │   │   ├── res/
│   │   │   │   └── drawable-nodpi/
│   │   │   │       └── androidparty.png          # Greeting card background image asset
│   │   │   └── AndroidManifest.xml
│   │   └── test/                                 # Unit Tests
│   └── build.gradle.kts
├── gradle/
│   └── libs.versions.toml                        # Dependency version catalog
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure you have the following installed:
- [Android Studio](https://developer.android.com/studio) (Koala / Ladybug or newer recommended)
- Android SDK Platform 37 installed via SDK Manager

### 2. Building the Project

Open a terminal in the project root directory and run:

- **Build Debug APK:**
  ```bash
  ./gradlew assembleDebug
  ```

- **Compile Kotlin Code:**
  ```bash
  ./gradlew :app:compileDebugKotlin
  ```

- **Run Unit Tests:**
  ```bash
  ./gradlew test
  ```

### 3. Running on Device or Emulator

1. Connect an Android device with USB debugging enabled or launch an Android Virtual Device (AVD).
2. Open the project in Android Studio.
3. Click the **Run** button (or press `Shift + F10`) to deploy the `:app` module.

---

## 🖼️ Code Snippet Overview

```kotlin
@Composable
fun GreetingImage(message: String, from: String, modifier: Modifier = Modifier) {
    val image = painterResource(R.drawable.androidparty)
    Box(modifier) {
        Image(
            painter = image,
            contentDescription = null,
            contentScale = ContentScale.Crop,
            alpha = 1.0f
        )
        GreetingText(
            message = message,
            from = from,
            modifier = Modifier
                .fillMaxSize()
                .padding(8.dp)
        )
    }
}
```

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
