# CLAUDE.md

This public repository holds DataFlow's release assets and nothing else: for each version, a GitHub Release with the installers, their updater signatures (`.sig`), SHA-256 checksums and `latest.json`. There is no code to build here.

- The DataFlow app's updater reads `releases/latest/download/latest.json`. Every update it installs must match the signature in that file.
- The website (letdataflow.com) links to stable names under `releases/latest/download/`: `DataFlow-windows-x64-setup.exe`, `DataFlow-macos-arm64.dmg`, `DataFlow-linux-x86_64.AppImage`. Every release must carry them.
- Releases are made by the DataFlow repository's release tooling: each platform adds its files and a `latest-<platform>.json` to a draft, then `scripts/release/merge-latest.mjs` joins those into `latest.json` and publishes. Don't create, edit or delete releases by hand, and never reuse a version tag: to take a release back, publish the next patch.

## Sibling repositories

DataFlow is three repositories under ARCED-International, usually cloned side by side (`../DataFlow`, `../dataflow-web`):

- **DataFlow** (private): the desktop app and its release tooling (`.github/workflows/release.yml`, `scripts/release/`, `scripts/set-version.sh`); its docs/RELEASING.md describes a release step by step.
- **dataflow-web** (private): the website at letdataflow.com, whose download page links here.
