---
paths:
  - "**/*.dart"
  - "pubspec.yaml"
---

# Flutter and Dart

- Keep widgets small and presentational. Business logic lives in view models or repositories.
- Use `const` constructors and keys where they prevent needless rebuilds.
- Choose Row, Column, Expanded, Flexible and Spacer before fixed sizes or absolute positioning.
- Never call `setState` or navigate during `build`. Trigger side effects from callbacks.
- Use `async`/`await` with proper error handling; dispose controllers, streams and listeners.
- Check `mounted` before using a `BuildContext` after an `await`.
- Add or update widget tests for new screens, and run `flutter analyze` and `flutter test`.
- Declare new packages in `pubspec.yaml` only after the user agrees.
