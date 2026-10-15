# platform-parity

Compare iOS and Android behaviour of a feature and list platform-specific gaps.

# platform-parity

When invoked with a feature name or screen, compare how it behaves on iOS and Android (and web, if the project targets it).

1. Locate the shared code and every platform-specific branch (platform files, `Platform.select`, `Platform.isIOS`, `#if os`, source sets).
2. For each platform, list: navigation and back behaviour, permission flow, keyboard handling, safe areas, haptics or feedback, text input quirks, and any API that exists on only one platform.
3. Mark each difference as intentional (follows platform convention) or accidental (a gap or bug).
4. Propose the smallest fix for each accidental gap. Do not implement them until the user agrees.
5. Report as a table: area, iOS behaviour, Android behaviour, verdict.
