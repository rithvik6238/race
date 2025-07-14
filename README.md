# File content replacements (case-sensitive)
REPLACE ALL: Wllama → Race
REPLACE ALL: wllama → race
REPLACE ALL: @wllama/wllama → @race/race

# Rename filenames and folders
RENAME FILE: ./src/wllama.ts → ./src/race.ts
RENAME FILE: ./esm/wllama.js → ./esm/race.js
RENAME FILE: ./esm/wllama.wasm → ./esm/race.wasm
RENAME FILE: ./esm/wllama.worker.mjs → ./esm/race.worker.mjs
RENAME FILE: ./esm/single-thread/wllama.js → ./esm/single-thread/race.js
RENAME FILE: ./esm/single-thread/wllama.wasm → ./esm/single-thread/race.wasm
RENAME FILE: ./esm/multi-thread/wllama.js → ./esm/multi-thread/race.js
RENAME FILE: ./esm/multi-thread/wllama.wasm → ./esm/multi-thread/race.wasm
RENAME FILE: ./esm/multi-thread/wllama.worker.mjs → ./esm/multi-thread/race.worker.mjs

# Rename variables and instances in code
REPLACE ALL: const wllama → const race
REPLACE ALL: new Wllama → new Race

# Update import paths in all files
REPLACE ALL: import { Wllama } from './esm/index.js'; → import { Race } from './esm/index.js';

# Update package.json
REPLACE IN package.json: "name": "@wllama/wllama" → "name": "@race/race"

# Update README.md
REPLACE IN README.md: Wllama → Race
REPLACE IN README.md: wllama → race
REPLACE IN README.md: @wllama/wllama → @race/race
REPLACE IN README.md: ./README_banner.png → ./race_banner.png (if you rename image)

# Update config path references
REPLACE IN CODE:
  'single-thread/wllama.js' → 'single-thread/race.js'
  'single-thread/wllama.wasm' → 'single-thread/race.wasm'
  'multi-thread/wllama.js' → 'multi-thread/race.js'
  'multi-thread/wllama.wasm' → 'multi-thread/race.wasm'
  'multi-thread/wllama.worker.mjs' → 'multi-thread/race.worker.mjs'

# Optional GitHub/NPM metadata
RENAME: GitHub repo name → race
RENAME: npm package name → @race/race
