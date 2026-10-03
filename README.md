# vibin-dll

Public helper DLLs for VIBIN Launcher.

These files are **not** shipped inside the VIBIN Launcher installer. The launcher downloads them on first run from this repository and verifies each file against `manifest.json` (SHA256 + size).

## Layout

- `dlls/` — Windows x64 DLL files
- `manifest.json` — integrity metadata consumed by VIBIN Launcher
- `scripts/update-manifest.ps1` — regenerate `manifest.json` after DLL changes

## Update workflow

1. Replace or add files under `dlls/`.
2. Run:

```powershell
.\scripts\update-manifest.ps1
```

3. Commit, push, and tag if you cut a release.

## Why a separate repo?

- Keeps game helper DLLs out of the launcher installer (fewer antivirus false positives during setup).
- Provides a stable, auditable download source with explicit hashes.
- Allows updating patch DLLs without rebuilding the full launcher.

## License

Same distribution terms as VIBIN Launcher — for use with supported VIBIN/Fortnite private builds only.
