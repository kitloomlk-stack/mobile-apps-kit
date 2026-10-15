---
name: "simulator-check"
description: "Build the app, run it on a simulator or emulator, and report what was actually observed on screen."
---

# simulator-check

When invoked, verify the current change on a real simulator or emulator.

1. Identify the stack and the affected screens from the changed files.
2. Pick an installed simulator or emulator (list the available ones first). State the device and OS version you chose.
3. Build and launch using the project's own commands (for example `flutter run`, `xcodebuild`, `./gradlew installDebug`, `npx expo start`). Ask before installing anything new.
4. Walk the affected flow: happy path, then empty, error and offline states, then rotate or resize if supported.
5. Check accessibility: labels present, focus order sensible, text still readable at a large font size, dark mode legible.
6. Report what you saw, step by step, including any console warnings or crashes. If you could not run the app, say exactly why and do not claim it works.
