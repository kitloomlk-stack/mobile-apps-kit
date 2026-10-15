---
applyTo: "app/**/*.tsx,src/**/*.tsx,app.json,app.config.*"
description: "Applies when editing React Native or Expo screens and config."
---

# React Native and Expo

- Use TypeScript in strict mode. Type navigation params and API responses.
- Lists: use FlatList or FlashList, stable `keyExtractor`, memoised row components, no inline heavy functions in render.
- Animate with Reanimated on the UI thread; avoid animating layout through React state.
- Put platform differences in `.ios.tsx` / `.android.tsx` files or `Platform.select`, not scattered conditionals.
- Prefer Expo SDK modules over third-party packages that do the same job.
- Read configuration from `app.json` or `app.config.*` and public `EXPO_PUBLIC_` variables only; never embed secrets in the JS bundle.
- Respect safe areas with the safe-area context, and test on both a small and a large device.
- Ask before adding a native module, since it can break Expo Go and require a new build.
