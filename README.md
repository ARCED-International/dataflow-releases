# DataFlow downloads

**[DataFlow](https://letdataflow.com) is a desktop app that checks field survey data while the team is still in the field.** It pulls interviews from SurveyLoopr, SurveyCTO or ODK Central (or a CSV or Excel export from any tool, KoboToolbox included), runs data-quality checks on every sync, and gives one ranked list of problems, each with a fix to approve. Keep your collection platform; DataFlow adds the quality layer on top of it.

This repository holds DataFlow's installers, checksums and update files. The app is made by [ARCED International](https://arced-international.com).

## Download

| Platform | Installer |
|---|---|
| Windows 10 and 11 (64-bit) | [DataFlow-windows-x64-setup.exe](https://github.com/ARCED-International/dataflow-releases/releases/latest/download/DataFlow-windows-x64-setup.exe) |
| macOS (Apple silicon) | [DataFlow-macos-arm64.dmg](https://github.com/ARCED-International/dataflow-releases/releases/latest/download/DataFlow-macos-arm64.dmg) |
| Linux (x86-64) | [DataFlow-linux-x86_64.AppImage](https://github.com/ARCED-International/dataflow-releases/releases/latest/download/DataFlow-linux-x86_64.AppImage) |

Intel Macs, the Linux `.deb` and the Windows `.msi` are on the [latest release](https://github.com/ARCED-International/dataflow-releases/releases/latest). The [download page](https://letdataflow.com/download) has install steps for each platform, including how to open DataFlow on a Mac the first time.

Start with the sample study: 600 interviews with real-looking problems, free and with no account. [Pricing](https://letdataflow.com/pricing) covers the rest.

## What DataFlow checks

- Duplicate IDs, interview length, outliers, allowed ranges and missing answers
- "Don't know" and refusal rates, and "other, specify" answers that belong to an existing option
- Logic rules written like XLSForm conditions, and answer pairs that can't go together
- Interview location from GPS, back-checks, and statistical signs of made-up interviews for each enumerator

DataFlow suggests the checks from your form and data. Raw submissions are never changed: every correction is logged, can be undone, and exports as a Stata do-file that rebuilds the clean data from the raw data. Survey data stays on your computer, encrypted, and the local AI works offline. See [features](https://letdataflow.com/features), [integrations](https://letdataflow.com/integrations) and [security and privacy](https://letdataflow.com/security).

## Check a download

Each release lists a SHA-256 checksum for every file: `SHA256SUMS-windows.txt` and `SHA256SUMS-linux.txt`.

- **Windows:** the installer and the app are signed by ARCED International LLC. To check a checksum: `certutil -hashfile <file> SHA256`.
- **macOS or Linux:** `shasum -a 256 <file>`.
- **Linux, with the GPG signature:** import [DataFlow's release key](https://letdataflow.com/dataflow-release-key.asc) (fingerprint `FB6B 6B8B 9469 5B40 602B 46F0 676A 32E8 689D 6C32`), then:

  ```bash
  gpg --import dataflow-release-key.asc
  gpg --verify SHA256SUMS-linux.txt.asc SHA256SUMS-linux.txt
  sha256sum --check --ignore-missing SHA256SUMS-linux.txt
  ```

## Updates

DataFlow checks this repository for a new version when it starts and every six hours, downloads it in the background, and asks before it restarts. It installs only an update whose signature matches the key built into the app (the `.sig` files and `latest.json` here). The check carries no survey data.

## Help

Write to [hello@letdataflow.com](mailto:hello@letdataflow.com). The [changelog](https://letdataflow.com/changelog) lists what changed in each version.
