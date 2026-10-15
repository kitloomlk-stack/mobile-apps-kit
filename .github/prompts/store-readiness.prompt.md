---
name: "store-readiness"
description: "Audit the project against an app-store submission checklist and list blockers."
---

# store-readiness

When invoked, audit the project against an App Store and Google Play submission checklist. Do not change files; produce a report.

Check and report on each item, citing the file you found it in:

- App identity: name, bundle identifier or application ID, version and build number, icons for all required sizes, splash or launch screen.
- Permissions: every declared permission or usage-description string, and whether code actually uses it. Flag unused or vague entries.
- Privacy: data collected, third-party SDKs that collect data, and whether a privacy policy URL is configured.
- Sign-in: if third-party login exists, note whether the store's account rules are met; account deletion available in-app if accounts can be created.
- Stability: debug flags, test endpoints, logging of personal data, placeholder text, TODOs on user-facing screens.
- Listing: title, subtitle, description, keywords, screenshot set for required device sizes, support URL.
- Build: release configuration, minimum OS version, supported architectures.

End with a short list of blockers, then warnings, then items you could not verify from the repository. You may delegate to the `store-readiness-auditor` sub-agent.
