# Mobile Apps Kit

A setup for building Flutter, iOS, Android and React Native apps: platform conventions, simulator testing, and an app-store readiness checklist before you ship.

A setup for AI coding agents, made by [Kitloom](https://kitloom.site). One source, generated for every major agent: Claude Code, OpenAI Codex, Cursor, Google Antigravity, Gemini CLI, GitHub Copilot, Windsurf (Devin), opencode and Aider.

## Install

1. Download this repository as a ZIP, or use the **Check and download** button on its Kitloom page, which checks it first.
2. Read the files. Nothing here runs on its own: the kit has no hooks and no install scripts.
3. Copy the folders and files you want into the root of your project. `AGENTS.md` is the shared instructions file; edit it to fit your project.

## What is inside

### Skills

- `ios-simulator-skill` — Build, launch and drive the iOS Simulator, navigate the UI and run accessibility checks when verifying an iOS change.
- `react-native` — Writing or reviewing React Native and Expo code: lists, Reanimated, navigation and platform-specific code.
- `flutter-best-practices` — Writing, reviewing or refactoring Flutter and Dart code, project structure and widgets.
- `flutter-app-architecture` — Scaffolding a Flutter project or splitting it into view models, repositories and dependency injection.
- `testing` — Writing or fixing Flutter unit, widget and golden tests, or chasing flaky tests.
- `flutter-errors` — Diagnosing RenderFlex overflow, unbounded constraints and setState-during-build errors.
- `appllama-app-design-skill` — Designing or implementing native-feeling mobile screens, onboarding, sheets, tab bars and empty states in Expo or React Native.
- `apple-ecosystem-expert` — Checking an iOS feature against Apple Human Interface Guidelines and platform behaviour.
- `app-store-optimization` — Preparing or auditing an App Store or Google Play listing: metadata, keywords and screenshots.

### Commands

Invoke by name (for example `/simulator-check`).

- `simulator-check` — Build the app, run it on a simulator or emulator, and report what was actually observed on screen.
- `store-readiness` — Audit the project against an app-store submission checklist and list blockers.
- `platform-parity` — Compare iOS and Android behaviour of a feature and list platform-specific gaps.

### Sub-agents

- `ui-states-reviewer` — Delegate to review a screen or flow for missing loading, empty, error and offline states and accessibility gaps.
- `store-readiness-auditor` — Delegate to audit app metadata, permissions, privacy declarations and assets before a store submission.

### Scoped rules

- `flutter-dart` — Applies when editing Dart code in a Flutter app.
- `apple-swift` — Applies when editing Swift or SwiftUI code for iOS.
- `react-native-expo` — Applies when editing React Native or Expo screens and config.

## Where each agent finds it

| Agent | Instructions | Skills and commands | Rules | Sub-agents |
|---|---|---|---|---|
| Claude Code | `CLAUDE.md` (imports `AGENTS.md`) | `.claude/skills/` | `.claude/rules/` | `.claude/agents/` |
| OpenAI Codex | `AGENTS.md` | `.agents/skills/` | listed in `AGENTS.md` | `.codex/agents/` |
| Cursor | `AGENTS.md` | `.agents/skills/`, `.claude/skills/` | `.cursor/rules/` | `.claude/agents/` |
| Google Antigravity | `AGENTS.md` | `.agents/skills/` | `.agents/rules/` | `.agents/agents/` |
| Gemini CLI | `AGENTS.md` via `.gemini/settings.json` | `.agents/skills/`, `.gemini/commands/` | listed in `AGENTS.md` | `.gemini/agents/` |
| GitHub Copilot | `AGENTS.md` | `.agents/skills/`, `.github/prompts/` | `.github/instructions/` | `.claude/agents/` |
| Windsurf (Devin) | `AGENTS.md` | `.agents/skills/`, `.windsurf/workflows/` | `.windsurf/rules/` | — |
| opencode | `AGENTS.md` | `.agents/skills/`, `.opencode/commands/` | listed in `AGENTS.md` | `.opencode/agents/` |
| Aider | `AGENTS.md` via `.aider.conf.yml` | — | — | — |

Skills are stored twice (`.agents/skills/` and `.claude/skills/`) because Claude Code reads only its own folder. Agents that read both may list a skill twice; delete the copy you do not need.

## Credits

The skills come from these open-source repositories, each under its own licence. Their licence and a notice are kept beside every copied skill.

| Skill | Source | Licence |
|---|---|---|
| `ios-simulator-skill` | [conorluddy/ios-simulator-skill](https://github.com/conorluddy/ios-simulator-skill) at `c535422` | MIT |
| `react-native` | [jezweb/claude-skills](https://github.com/jezweb/claude-skills) at `1260fa7` | MIT |
| `flutter-best-practices` | [evanca/flutter-ai-rules](https://github.com/evanca/flutter-ai-rules) at `30f908d` | MIT |
| `flutter-app-architecture` | [evanca/flutter-ai-rules](https://github.com/evanca/flutter-ai-rules) at `30f908d` | MIT |
| `testing` | [evanca/flutter-ai-rules](https://github.com/evanca/flutter-ai-rules) at `30f908d` | MIT |
| `flutter-errors` | [evanca/flutter-ai-rules](https://github.com/evanca/flutter-ai-rules) at `30f908d` | MIT |
| `appllama-app-design-skill` | [Appllama/appllama-skills](https://github.com/Appllama/appllama-skills) at `dd5caae` | MIT |
| `apple-ecosystem-expert` | [roedyrustam/vibes-plug](https://github.com/roedyrustam/vibes-plug) at `3489fab` | MIT |
| `app-store-optimization` | [cbrock84/headcount](https://github.com/cbrock84/headcount) at `98d1c17` | MIT |

Everything else in this repository (instructions, rules, commands, sub-agents) is by Kitloom under the MIT licence.

## Use at your own risk

Read every file before you use it. Agent instructions can make an agent run commands on your machine. This kit was checked with Kitloom's pre-download check, which looks for warning signs but cannot prove anything is safe.
