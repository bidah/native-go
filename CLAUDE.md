# native-go

An Expo (SDK 57) app that runs inside **Native Now**, a prebuilt iOS shell, on
the simulator beside this terminal. There is no native build: the shell already
has every native module this project may use compiled in.

## Rules

- **Dependencies are fixed.** `package.json` pins every package the shell can
  run, at the exact version the shell was built with. Import from them freely.
  Never add, remove or upgrade a package — anything not already listed cannot
  run in the shell. `native-now doctor` checks this.
- Style with NativeWind (`className`), or `StyleSheet`.
- Entry point: `index.ts` → `src/App.tsx`.

## Seeing your changes

When you finish a turn with changed files, a hook re-exports the app and pushes
it to the simulator, which reloads in place. If the new code throws, the
device's error comes back to you — fix it. On success you get a screenshot of
the simulator to check the result against what was asked.
