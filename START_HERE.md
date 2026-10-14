# EffectCraft v0.9.2 — original UI automatic website build

This bundle is the original upstream v0.9.2 source plus a GitHub Actions workflow. It is **not** a precompiled website. The build must run on GitHub because Rust/WASM tools are unavailable in the packaging environment.

## How to get the Netlify-ready ZIP without installing anything

1. Create a new GitHub repository (public or private).
2. Upload the **contents of this folder** (including `.github/workflows/build-web.yml`) to the repository's `main` branch. The GitHub web uploader can upload folders, but verify the hidden `.github` folder is included. For large numbers of files, GitHub Desktop or git may be easier.
3. Go to **Actions** → **Build original EffectCraft web site** → **Run workflow**. The workflow also triggers on push to main.
4. Wait for the build to finish. Under the run's **Artifacts**, download `EffectCraft-Netlify-Deploy`.
5. Extract that artifact ZIP. Drag the **extracted contents** (or its folder) into Netlify's manual deploy page. The website must contain `index.html`, `effectcraft_web.js`, and `effectcraft_web_bg.wasm` at the root.

The original Rust egui UI and engine are compiled to WebAssembly. The browser version may differ in OS-specific title bars and native-only features. Do not expect the site to work by uploading this *source* ZIP directly to Netlify.

If build fails, inspect the GitHub Actions logs; this build has not been executed in the current environment. GitHub Actions limits/quotas may apply.

Source: https://github.com/storytold/effectcraft/tree/v0.9.2
Upstream documentation: docs/web.md
Respect upstream MIT/Apache-2.0 licensing and notices.
