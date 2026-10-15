# Mobile Apps Kit

This setup is for building and shipping mobile apps with Flutter, iOS (Swift and SwiftUI),
Android (Kotlin) and React Native or Expo. It favours platform conventions over custom
widgets, verifying changes on a simulator or emulator rather than assuming they work, and
treating app-store requirements as part of the definition of done.

## Working agreement

- Identify the stack first: look for `pubspec.yaml` (Flutter), `*.xcodeproj` or `Package.swift`
  (iOS), `build.gradle(.kts)` (Android), `package.json` with `expo` or `react-native`
  (React Native). Follow the conventions already in the repo before introducing new ones.
- Ask before adding a dependency, changing the minimum OS version, or editing signing,
  entitlements, permissions or bundle identifiers.
- Never commit signing keys, provisioning profiles, keystores, `google-services.json` with real
  project data, or `.env` files. Do not read credential files. If one is needed, ask the user.
- Ask before pushing, tagging, uploading a build, or submitting to a store.
- Make small, verifiable changes. After each one, build and run it where possible.

## Platform conventions

- Follow the platform's own navigation, back behaviour and gestures. Do not port an iOS tab
  bar or Android back-stack idiom to the other platform without a reason.
- Respect safe areas, notches, dynamic type or font scale, dark mode, and landscape if the app
  supports it. Never hard-code pixel sizes for text containers.
- Touch targets are at least 44x44 pt (iOS) and 48x48 dp (Android).
- Every interactive element needs an accessibility label; check VoiceOver and TalkBack
  semantics for custom controls.
- Ask for a permission at the moment it is needed, with a one-line reason, and handle denial
  without breaking the screen.
- Treat network as unreliable: every screen that loads data has loading, empty, error and
  offline states, and a retry path.
- Keep work off the main thread. Use async APIs (Dart isolates, Swift concurrency, Kotlin
  coroutines, JS async) and cancel work when a screen goes away.

## Stack notes

- **Flutter:** layered architecture (view, view model, repository, service), one source of
  truth per piece of state, `const` constructors where possible, no business logic in widgets.
  Prefer Row, Column, Expanded and Flexible over fixed sizes. Run `flutter analyze` and
  `flutter test` before finishing.
- **iOS:** SwiftUI first, UIKit only where needed. Use structured concurrency, avoid force
  unwraps, keep views small, and check against the Human Interface Guidelines.
- **Android:** Jetpack Compose with unidirectional state, ViewModel plus StateFlow, no work in
  composables, resources in `res/` rather than literals.
- **React Native / Expo:** virtualized lists with stable keys, Reanimated for animation,
  platform files or `Platform.select` for divergence, TypeScript strict. Prefer Expo SDK
  modules over community packages when both exist.

## Testing

- Pyramid: many unit tests for logic, widget or component tests for screens, a few
  end-to-end flows for the critical path (sign-in, purchase, onboarding).
- A bug fix starts with a failing test when the code is testable.
- UI claims need evidence: run the app in a simulator or emulator, state which device and OS
  version, and describe what you saw. If you could not run it, say so plainly.
- Do not weaken or delete a test to make it pass. Report why it fails instead.

## Before you finish

1. The project builds for every platform you touched.
2. Analyzer, linter and tests pass; report the exact commands and results.
3. New screens have loading, empty, error and offline states and accessible labels.
4. New permissions, entitlements or privacy-relevant data collection are listed for the user.
5. Anything you did not verify is stated explicitly.

## Skills in this kit

- ios-simulator-skill — drive the iOS Simulator: build, launch, navigate, accessibility checks.
- react-native — React Native and Expo performance, navigation and platform code.
- flutter-best-practices — everyday Flutter and Dart structure, state and widgets.
- flutter-app-architecture — layering, view models, repositories, dependency injection.
- testing — Flutter unit, widget and golden tests, flaky test fixes.
- flutter-errors — layout and build-time Flutter error diagnosis.
- appllama-app-design-skill — native-feeling mobile UI patterns for Expo and React Native.
- apple-ecosystem-expert — Apple platform behaviour and Human Interface Guidelines.
- app-store-optimization — store listing metadata, keywords and screenshots.

There is no dedicated Android skill in this kit; rely on the Android notes above and the
official Android documentation, and say when you are unsure.

## Commands

- `simulator-check` — build, run on a simulator or emulator, report what was observed.
- `store-readiness` — audit the project against a submission checklist.
- `platform-parity` — compare iOS and Android behaviour of a feature.

## Sub-agents

- `ui-states-reviewer` — read-only review of screens for missing states and accessibility.
- `store-readiness-auditor` — read-only audit of metadata, permissions and assets.

## Scoped rules

Agents that support scoped rules load these automatically. If yours does not, read the matching file before editing files it covers:

- `.agents/rules/flutter-dart.md` — for `**/*.dart`, `pubspec.yaml`: Applies when editing Dart code in a Flutter app.
- `.agents/rules/apple-swift.md` — for `**/*.swift`: Applies when editing Swift or SwiftUI code for iOS.
- `.agents/rules/react-native-expo.md` — for `app/**/*.tsx`, `src/**/*.tsx`, `app.json`, `app.config.*`: Applies when editing React Native or Expo screens and config.
