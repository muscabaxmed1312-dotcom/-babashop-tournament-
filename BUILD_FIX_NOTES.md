# Render build error fix

If Render shows:

`Error [ERR_MODULE_NOT_FOUND]: Cannot find module '/opt/render/project/src/script/build.ts'`

the repository is missing `script/build.ts` while your Render/NPM build command expects it.

## What was added

- `script/build.ts` as a safe placeholder build entrypoint.

## Next steps

1. Check your Render **Build Command** (for example `npm run build`).
2. Check `package.json` and confirm what `build` runs.
3. Replace the placeholder logic in `script/build.ts` with your real build steps.
4. Ensure dependencies for TypeScript runtime (for example `tsx` or `ts-node`) are installed if your build command executes `.ts` directly.
