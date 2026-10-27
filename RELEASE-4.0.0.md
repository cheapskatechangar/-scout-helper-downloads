# Permission Helper 4.0.0 stable

Released October 27, 2026 with the maintainer's confirmation that the Scout hidden-permission fix works and explicit authorization to promote and publish it.

When Scout leaves a permission prompt below the current conversation viewport, the helper requests that the selected permission button be brought into view, then rescans before approval. Detect only never scrolls. Navigation is bounded to one attempt per control per run. Pause, Stop, target identity, visibility checks and duplicate protection remain. Providers without ScrollItem support require manual down-arrow navigation.

This stable release also includes the previous Beta 7 target profiles and exact-action matching. The maintainer's live confirmation covers the Scout fix. Autopilot and other host/action combinations retain their separately documented acceptance limitations; no new universal compatibility claim is made.

## Upgrade

1. Stop and close the older helper.
2. Download PermissionHelper-Portable-4.0.0.zip from the public downloads repository and extract both files to a new folder.
3. Keep Start-PermissionHelper.bat beside PermissionHelper.Portable.ps1. Older 3.1.x launcher/script names differ; do not mix versions.
4. Launch Start-PermissionHelper.bat, select the intended target and permission scope, and begin with Detect only.
5. Stop and clear Detect only when ready for the helper to handle selected approvals.

Updates are download-and-extract, not an automatic replacement of a running script. Stable.json and the legacy latest.json offer 4.0.0. Beta.json also points to 4.0.0 so existing beta installations see the stable upgrade. The released application checks stable.json for future updates. Refresh does not reload code; restart after upgrading.

## Validation

The full Windows PowerShell 5.1 gate passed all 437 checks with a separate test TEMP directory. The new hidden-permission suite has 49 passing checks, including the real worker/scanner/reveal/approval pipeline with simulated controls. The maintainer separately confirmed the live Scout fix works. Build tooling verifies the two-file archive, packaged source bytes, embedded logo and SHA-256. Historical file-replacement failures and full-gate rerun results are recorded in HIDDEN-PERMISSIONS.md; fixture results alone do not establish live compatibility.

Public distribution: https://github.com/cheapskatechangar/-scout-helper-downloads
