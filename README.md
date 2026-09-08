# Inertial Sensor Data Collection with Google Maps Integration

An Android application that collects inertial sensor data (accelerometer and gyroscope) alongside GPS location readings, visualized on a Google Maps interface. This app is designed to support research on cognitive architectures by providing sensor-logging capabilities for mobile environments.

This project was developed as part of the Cognitive Architectures research line from 
the Hub for Artificial Intelligence and Cognitive Architectures (H.IAAC) of the State University of Campinas (UNICAMP).
See more projects from the group [here](https://h-iaac.github.io/HIAAC-Index).

<!--Badges-->
[![](https://img.shields.io/badge/-H.IAAC-eb901a?style=for-the-badge&labelColor=black)](https://hiaac.unicamp.br/)

<!--Meta 1: Arquiteturas Cognitivas-->
[![](https://img.shields.io/badge/-Arq.Cog-black?style=for-the-badge&labelColor=white&logo=data:image/svg%2bxml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4gPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI1Ni4wMDQiIGhlaWdodD0iNTYiIHZpZXdCb3g9IjAgMCA1Ni4wMDQgNTYiPjxwYXRoIGlkPSJhcnFjb2ctMiIgZD0iTTk1NS43NzQsMjc0LjJhNi41Nyw2LjU3LDAsMCwxLTYuNTItNmwtLjA5MS0xLjE0NS04LjEtMi41LS42ODksMS4xMjNhNi41NCw2LjU0LDAsMCwxLTExLjEzNi4wMjEsNi41Niw2LjU2LDAsMCwxLDEuMzY4LTguNDQxbC44LS42NjUtMi4xNS05LjQ5MS0xLjIxNy0uMTJhNi42NTUsNi42NTUsMCwwLDEtMi41OS0uODIyLDYuNTI4LDYuNTI4LDAsMCwxLTIuNDQzLTguOSw2LjU1Niw2LjU1NiwwLDAsMSw1LjctMy4zLDYuNDU2LDYuNDU2LDAsMCwxLDIuNDU4LjQ4M2wxLC40MSw2Ljg2Ny02LjM2Ni0uNDg4LTEuMTA3YTYuNTMsNi41MywwLDAsMSw1Ljk3OC05LjE3Niw2LjU3NSw2LjU3NSwwLDAsMSw2LjUxOCw2LjAxNmwuMDkyLDEuMTQ1LDguMDg3LDIuNS42ODktMS4xMjJhNi41MzUsNi41MzUsMCwxLDEsOS4yODksOC43ODZsLS45NDcuNjUyLDIuMDk1LDkuMjE4LDEuMzQzLjAxM2E2LjUwNyw2LjUwNywwLDAsMSw1LjYwOSw5LjcyMSw2LjU2MSw2LjU2MSwwLDAsMS01LjcsMy4zMWgwYTYuNCw2LjQsMCwwLDEtMi45ODctLjczMmwtMS4wNjEtLjU1LTYuNjgsNi4xOTIuNjM0LDEuMTU5YTYuNTM1LDYuNTM1LDAsMCwxLTUuNzI1LDkuNjkxWm0wLTExLjQ2MWE0Ljk1LDQuOTUsMCwxLDAsNC45NTIsNC45NUE0Ljk1Nyw0Ljk1NywwLDAsMCw5NTUuNzc0LDI2Mi43MzlaTTkzNC44LDI1Ny4zMjVhNC45NTIsNC45NTIsMCwxLDAsNC4yMjEsMi4zNDVBNC45Myw0LjkzLDAsMCwwLDkzNC44LDI1Ny4zMjVabS0uMDIyLTEuNThhNi41MTQsNi41MTQsMCwwLDEsNi41NDksNi4xTDk0MS40LDI2M2w4LjA2MSwyLjUuNjg0LTEuMTQ1YTYuNTkxLDYuNTkxLDAsMCwxLDUuNjI0LTMuMjA2LDYuNDQ4LDYuNDQ4LDAsMCwxLDIuODQ0LjY1bDEuMDQ5LjUxOSw2LjczNC02LjI1MS0uNTkzLTEuMTQ1YTYuNTI1LDYuNTI1LDAsMCwxLC4xMTUtNi4yMjksNi42MTgsNi42MTgsMCwwLDEsMS45NjYtMi4xMzRsLjk0NC0uNjUyLTIuMDkzLTkuMjIyLTEuMzM2LS4wMThhNi41MjEsNi41MjEsMCwwLDEtNi40MjktNi4xbC0uMDc3LTEuMTY1LTguMDc0LTIuNS0uNjg0LDEuMTQ4YTYuNTM0LDYuNTM0LDAsMCwxLTguOTY2LDIuMjY0bC0xLjA5MS0uNjUyLTYuNjE3LDYuMTMxLjc1MSwxLjE5MmE2LjUxOCw2LjUxOCwwLDAsMS0yLjMsOS4xNjRsLTEuMS42MTksMi4wNiw5LjA4NywxLjQ1MS0uMUM5MzQuNDc1LDI1NS43NSw5MzQuNjI2LDI1NS43NDQsOTM0Ljc3OSwyNTUuNzQ0Wm0zNi44NDQtOC43NjJhNC45NzcsNC45NzcsMCwwLDAtNC4zMTYsMi41LDQuODg5LDQuODg5LDAsMCwwLS40NjQsMy43NjIsNC45NDgsNC45NDgsMCwxLDAsNC43NzktNi4yNjZaTTkyOC43LDIzNS41MzNhNC45NzksNC45NzksMCwwLDAtNC4zMTcsMi41LDQuOTQ4LDQuOTQ4LDAsMCwwLDQuMjkxLDcuMzkxLDQuOTc1LDQuOTc1LDAsMCwwLDQuMzE2LTIuNSw0Ljg4Miw0Ljg4MiwwLDAsMCwuNDY0LTMuNzYxLDQuOTQsNC45NCwwLDAsMC00Ljc1NC0zLjYzWm0zNi43NzYtMTAuMzQ2YTQuOTUsNC45NSwwLDEsMCw0LjIyMiwyLjM0NUE0LjkyMyw0LjkyMywwLDAsMCw5NjUuNDc5LDIyNS4xODdabS0yMC45NTItNS40MTVhNC45NTEsNC45NTEsMCwxLDAsNC45NTEsNC45NTFBNC45NTcsNC45NTcsMCwwLDAsOTQ0LjUyNywyMTkuNzcyWiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoLTkyMi4xNDMgLTIxOC4yKSIgZmlsbD0iIzgzMDNmZiI+PC9wYXRoPjwvc3ZnPiA=)](https://h-iaac.github.io/HIAAC-Index)

## Repository Structure

- **app/**: Main Android application module containing source code, resources, and build configuration
  - **src/main/java/com/henriquehpds/ic/gmapsagoravai/**: Java source files
    - `MapsActivity.java` — Main activity: Google Maps display with concurrent GPS location tracking and inertial sensor logging (accelerometer + gyroscope). Exports data to CSV on pause/destroy.
    - `SensorActivity.java` — Alternative activity: standalone inertial sensor reader that logs accelerometer and gyroscope data to a CSV file.
  - **src/main/res/**: Android resources (layouts, drawables, themes, strings)
  - **build.gradle.kts**: Module-level build configuration with dependencies
- **build.gradle.kts**: Project-level Gradle build file
- **settings.gradle.kts**: Gradle settings
- **gradle.properties**: Gradle configuration properties
- **secrets.properties**: Local file for Google Maps API key (not committed to version control)
- **local.defaults.properties**: Default values for the secrets plugin
- **LICENSE**: Project license file

## Dependencies / Requirements

- **Android Studio** (Hedgehog or newer recommended) for building and running the project
- **Android SDK** version 36 (compile SDK) with minimum support for API 24 (Android 7.0)
- **Google Maps API Key** — obtain one from the [Google Cloud Console](https://console.cloud.google.com/)
- **Gradle** 8.x (wrapped via `gradlew`)

Key libraries used (automatically resolved by Gradle):
- `com.google.android.gms:play-services-maps:19.2.0` — Google Maps SDK
- `com.google.android.gms:play-services-location:21.3.0` — Fused Location Provider
- `androidx.appcompat:appcompat:1.7.1` — AndroidX support
- Google Maps Secrets Gradle Plugin — for API key management

## Installation / Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/H-IAAC/gmaps-android-sensors.git
   ```

2. Open the project in **Android Studio**.

3. Configure your **Google Maps API key**:
   - Create a `secrets.properties` file in the project root (or edit the existing one):
     ```properties
     MAPS_API_KEY=YOUR_API_KEY_HERE
     ```
   - The key is injected into `AndroidManifest.xml` via the `google.maps.platform.secrets` Gradle plugin.

4. Build and run on a physical Android device (7.0+ / API 24+) or emulator with Google Play services:
   ```bash
   ./gradlew assembleDebug
   ```
   Or click **Run** in Android Studio.

### Behavior

- **MapsActivity** (launcher): Displays a Google Map. While active, it reads:
  - **Accelerometer** and **gyroscope** data at `SENSOR_DELAY_NORMAL` rate
  - **GPS location** via the Fused Location Provider every 2 seconds
  - On pause or destroy, exports:
    - `sensor_data.csv` — columns: `timestamp,type (ACCEL|GYRO),x,y,z`
    - `location_data.csv` — columns: `timestamp,latitude,longitude`
- **SensorActivity** (standalone sensor reader): Logs accelerometer and gyroscope at `SENSOR_DELAY_GAME` rate and exports `inertial.csv` on pause.

Output files are saved to the app's **external files directory** (accessible via device file explorer or ADB).

## Authors

- (2026-) [Henrique Parede de Souza](https://github.com/Henrique-hpds): Computer Engineering student, FEEC-UNICAMP

## Acknowledgements

This study was financed by the São Paulo Research Foundation (FAPESP), Brasil. Process Number 2024/23473-6.

Project supported by the brazilian Ministry of Science, Technology and Innovations, with resources from Law No. 8,248, of October 23, 1991