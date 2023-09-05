# Tamagui + Solito + Next + Expo Monorepo

## 🔦 About

This monorepo is a starter for an Expo + Next.js + Tamagui + Solito app, but focused on enterprise usage (older, more stable techs)

Many thanks to [@FernandoTheRojo](https://twitter.com/fernandotherojo) for the Solito starter monorepo which this was forked from. Check out his [talk about using expo + next together at Next.js Conf 2021](https://www.youtube.com/watch?v=0lnbdRweJtA).

## 📦 Included packages / Tech Stacks

- [Tamagui](https://tamagui.dev) 🪄
- [solito](https://solito.dev) for cross-platform navigation
- Expo SDK
- Next.js
- Expo Router
- pnpm

## 🗂 Folder layout

The main apps are:

- `expo` (native)
- `next` (web)

- `packages` shared packages across apps
  - `ui` includes your custom UI kit that will be optimized by Tamagui
  - `app` you'll be importing most files from `app/`
    - `features` (don't use a `screens` folder. organize by feature.)
    - `provider` (all the providers that wrap the app, and some no-ops for Web.)

You can add other folders inside of `packages/` if you know what you're doing and have a good reason to.

## 🏁 Start the app

- Install dependencies: `pnpm i` / `pnpm install`

- Next.js local dev: `pnpm web`

To see debug output to verify the compiler, add `// debug` as a comment to the top of any file.

- Expo local dev: `pnpm native`
- Expo run:android: `pnpm build:android`
- Expo run:ios: `pnpm build:ios`

## UI Kit

Note we're following the [design systems guide](https://tamagui.dev/docs/guides/design-systems) and creating our own package for components.

See `packages/ui` named `@my/ui` for how this works.

## 🆕 Add new dependencies

### Pure JS dependencies

If you're installing a JavaScript-only dependency that will be used across platforms, install it in `packages/app`:

```sh
cd packages/app
pnpm i date-fns
cd ../..
pnpm
```

### Native dependencies

If you're installing a library with any native code, you must install it in `expo`:

```sh
cd apps/expo
pnpm i react-native-reanimated
cd ..
pnpm
```
