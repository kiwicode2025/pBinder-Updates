# pBinder Update Channel

Public update/asset channel for **pBinder**.  
This repository does **not** contain pBinder application source code.

## What this repository hosts

- `latest.json` — update manifest (version, download URL, SHA-256, size, notes URL)
- `latest.json.sig` — detached RSA signature for `latest.json`
- GitHub Release assets per version tag (`vX.Y.Z`), including:
  - `pBinder.exe`
  - `certifi-<version>-corresponding-source.zip` (MPL corresponding-source artifact)  
    Current release example: `certifi-2024.7.4-corresponding-source.zip`

## Security model

- The app verifies `latest.json.sig` before trusting update metadata.
- The app verifies downloaded EXE hash against `latest.json` (`download.sha256`).
- Any manifest change requires a new signature.

## Notes

- pBinder is a commercial product sold via Gumroad.
- This repository is used only for update delivery and required open-source notice artifacts.
- License keys are not stored here.
- Application source code is not published here.

## Release checklist (short)

1. Build final `pBinder.exe`.
2. Create release tag (example: `v1.0.0`).
3. Upload release assets (`pBinder.exe` + certifi corresponding-source zip).
4. Regenerate `latest.json` for that EXE/version.
5. Sign it to produce `latest.json.sig`.
6. Commit/push `latest.json` and `latest.json.sig` to `main`.

