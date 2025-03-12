This is a minimal setup to demonstrate a bug in @parcel/library-bundler with `export * as name from "file"` syntax with ESModules.

## Repro
1. look at `src/index.ts` - note it exports a symbol `constants` which should contain all the constants in `src/constants.ts`
2. run `npm run build` 
3. observe `dist/index.mjs`  
Expected: file contains `constants` export
Observed: file imports constants, but does not export anything.

