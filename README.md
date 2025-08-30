# Library_manager_flutter

A cross-platform library management app built with Flutter (Android/iOS/web) and a Flask + SQLite backend.

## Project overview

Library_manager_flutter is a full-stack example application that implements a library borrowing system. The Flutter frontend provides user authentication, book browsing/search, book details, and borrow/return workflows. The bundled Flask backend exposes REST endpoints and uses SQLite as the data store. A custom in-tree Flutter plugin (`plugins/login`) supplies an enhanced login UI.

## Features

- User signup & login
- Browse books (list & detail views)
- Search books by title/author/category
- Borrow and return books; view borrow history
- Custom login plugin included (in-tree)
- Cross-platform support: Android, iOS, and web (Flutter)

## Repo structure (high-level)

```
Library_manager_flutter/
├─ android/        # Android module (Gradle)
├─ ios/            # iOS module (Xcode)
├─ lib/            # Flutter app source (Dart)
├─ plugins/login/  # Custom login plugin
├─ backend/        # Flask backend + database.db (SQLite)
├─ assets/         # Images & fonts
├─ pubspec.yaml
└─ README.md
```

## Configuration & customizable places

Customizable elements and their locations in the repository:

- **Backend base URL (frontend):** occurrences of the base URL string appear across `lib/**/*.dart`.
- **Backend host and port:** defined in `backend/backend.py`.
- **Database file:** path is `backend/database.db` (SQLite).
- **Android package & app name:** locations include `android/app/src/main/AndroidManifest.xml`, `android/app/build.gradle`, and `pubspec.yaml`.
- **Plugin usage:** plugin source is at `plugins/login`.
- **Assets & fonts:** assets are under `assets/images/` and font entries appear in `pubspec.yaml`.
- **Gradle & Kotlin:** configuration files in `android/` and `android/gradle/wrapper/` control Gradle and Kotlin versions.
- **CORS and backend behavior:** relevant code sections are in `backend/backend.py`.

## Notable repository artifacts and observations

- The repository contains a committed Python virtual environment under `backend/venv/`.
- A SQLite database file `backend/database.db` is present in the archive.
- The Flutter frontend contains hardcoded backend host strings in multiple Dart files (example pattern: `http://192.168.0.100:5000/`).
- The Flask backend file in the archive has a default listening port setting that differs from some frontend references.
- Android Gradle Plugin and Kotlin versions in the Android module reflect an older toolchain in some files.
- The in-tree plugin `plugins/login` includes widget implementations and UI logic.

## Testing & current test coverage

- The repository contains the standard Flutter widget test placeholder (`test/widget_test.dart`).
- No comprehensive unit or integration test suites are present in the archive.

## Example .gitignore (informational)

```
# Flutter / Dart
.dart_tool/
.build/
.packages
.pub/
android/.gradle
**/build/

# VSCode / IntelliJ
.vscode/
.idea/
*.iml

# Backend virtualenv and DB
backend/.venv/
backend/database.db

# OS files
.DS_Store
Thumbs.db
```

## Contribution notes (informational)

Typical contribution flow for projects of this type: fork the repository, create a feature branch, apply changes, and open a pull request with a description
