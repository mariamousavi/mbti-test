# MBTI Test

A simple Flutter app to find your MBTI personality type. Uses the [Personality FYI API](https://personality.fyi) to score your answers and determine your type.

## Features

- 32-question personality test fetched from API
- Auto-advance on answer selection
- MBTI type result with confidence bar chart
- Personality detail screen with strengths, weaknesses, careers, and famous people
- Share your result
- Persian (RTL) text support
- Dark mode support

## Project Structure

```
lib/
├── main.dart                           # App entry, theme, routes
├── utils/
│   └── constants.dart                  # Colors, API URL, MBTI types
├── models/
│   ├── test_item.dart                  # Test question model
│   └── score_response.dart             # API result model
├── services/
│   └── api_service.dart                # HTTP GET & POST requests
└── screens/
    ├── splash_screen.dart              # Animated splash
    ├── home_screen.dart                # Home with type grid
    ├── test_screen.dart                # Questions with Likert scale
    ├── result_screen.dart              # Result with chart & share
    └── personality_detail_screen.dart   # Tabbed type details
```

## How It Works

1. **Home** — User sees a grid of all 16 MBTI types and a start button
2. **Test** — Questions are loaded from API, user picks answers (1-5 scale), screen auto-advances
3. **Result** — Answers are sent to API, result shows personality type + confidence chart
4. **Detail** — User can view strengths, weaknesses, careers, and famous people for any type

## Flutter Concepts Used

| Concept | Where |
|---------|-------|
| StatelessWidget | HomeScreen, ResultScreen |
| StatefulWidget | SplashScreen, TestScreen, PersonalityDetailScreen |
| Named routes & navigation | Navigator.pushNamed, pushReplacementNamed, popUntil |
| HTTP requests | http package — GET for questions, POST for scoring |
| Async/await | API calls with loading & error states |
| Animations | flutter_animate package |
| Charts | fl_chart for confidence bar chart |
| TabBar | TabController with TabBarView |
| Share | share_plus package |

## Dependencies

- `http` — API requests
- `flutter_animate` — animations
- `share_plus` — share results
- `fl_chart` — bar charts

## Run

```bash
flutter pub get
flutter run
```

## Build APK

```bash
flutter build apk --release
```

APK will be at `build/app/outputs/flutter-apk/app-release.apk`.

## Run in Chrome

```bash
flutter run -d chrome