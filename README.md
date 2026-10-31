# Frieren — Japanese card runtime dependencies

This repository hosts the Japanese MVU runtime required by a privately maintained `Frieren.png` character card. It does not contain that card, its worldbook, any preset, account data or chat history. This is not an official Frieren project.

The runtime is based on MagVarUpdate commit `d03b7dc8a6ebf9bd611c7e2dc91f3b35462deebc`, the exact upstream artifact served to the source card during localization. The Japanese edition translates the runtime's interface, help and settings protocol without changing its variable parsing and update mechanisms. Legacy Chinese settings are accepted as input aliases; Japanese settings are persisted under `mvu_jp_settings`.

`runtime/bundle.js` and its 82 imported modules are pinned by the immutable `v2026.10.31-ja.1` release. `DEPENDENCIES.json` records upstream URLs, original hashes, rewritten hashes and sizes. Imports between these files are relative to this release. Host-provided Vue, Zod, YAML and Tavern Helper remain host dependencies.

Build source is under `source/MagVarUpdate`. Install its dependencies with the package manager declared in `package.json`, then build with `CI=true` and `npm run build`. `tools/vendor-runtime.cjs` copies the compiled entry, mirrors its browser imports recursively and emits the release manifest. The checked-in manifest describes the actual release bytes. Build-time timestamps may differ in later rebuilds.

Upstream licenses and notices are preserved in the source, `runtime/bundle.js.LICENSE.txt`, `licenses/` and `LICENSES.json`. The two packages whose npm archives omit a license file include a pinned upstream license source. Natural-sort and seedrandom retain the notices embedded in their source distributions.

Validation: Japanese settings aliases and canonical precedence, explicit false/zero preservation, six canonical buttons plus the upstream incremental-repair action, complete import closure, and isolated SillyTavern UI/variable checks. No real model credentials or live model requests are used for these checks.
