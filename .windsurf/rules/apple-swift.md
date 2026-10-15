---
trigger: glob
globs: "**/*.swift"
description: "Applies when editing Swift or SwiftUI code for iOS."
---

# Swift and SwiftUI

- Prefer SwiftUI; drop to UIKit only when SwiftUI cannot do the job, and wrap it cleanly.
- Use structured concurrency (`async`/`await`, actors). Mark UI-facing types `@MainActor`.
- No force unwraps (`!`) or `try!` outside tests. Handle optionals and errors explicitly.
- Keep view bodies short; extract subviews and move logic into observable models.
- Support Dynamic Type, dark mode and VoiceOver: use semantic fonts and colors and set accessibility labels.
- Follow the Human Interface Guidelines for navigation, sheets, controls and haptics.
- Do not edit entitlements, Info.plist usage strings or signing settings without telling the user which keys changed and why.
