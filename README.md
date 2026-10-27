# Permission Helper | Windows downloads

Created by **CheapskateChangar**.

**STABLE release:** 4.0.0 | October 27, 2026

[Download stable 4.0.0 ZIP](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0.zip) · [SHA-256 checksum](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0.zip.sha256) · [Release notes](RELEASE-4.0.0.md) · [Website](https://scout-prompt-approver.vercel.app/)

## What's new

The Scout hidden-permission fix brings an exact selected approval button into view when the conversation is above it, then rescans before approval. The maintainer confirmed the fix works before authorizing stable release. Detect only remains read-only. If the accessibility provider cannot reveal the button, use Scout's down arrow manually.

4.0.0 also includes the previous Beta 7 target profiles, exact session actions and Cowork card matching. The live confirmation covers the Scout fix; it does not establish new live acceptance for every supported target or operation. Always allow and menu controls remain excluded. AI follow-ups are still manual.

## Upgrade and start

1. Stop and close the older helper.
2. Download and extract both files into a new folder.
3. Keep Start-PermissionHelper.bat and PermissionHelper.Portable.ps1 together. These names differ from 3.1.x; do not mix old and new files.
4. Open the intended app, launch Start-PermissionHelper.bat, and select the target and permission labels.
5. Start in Detect only. Stop, clear Detect only and start again when ready for selected approvals.

Check for updates in existing stable and beta installations now offers 4.0.0. Updating requires extracting the new package and restarting; Refresh does not reload code. stable.json, latest.json and beta.json intentionally offer the same stable package. New installations use stable.json for future updates.

Windows 10/11, Windows PowerShell 5.1 and an unlocked desktop are required. No installer, administrator access or GitHub sign-in is needed to download. Pause/Resume/Stop, emergency pause, limits and duplicate protection remain.

## Scope and logs

Use the helper only for work whose scope you have reviewed. Button labels do not establish the underlying operation, and invocation does not establish backend success. Cowork's selected Create/Approve confirmations are handled regardless of the displayed risk label, with matching-card and selected-window checks.

Local logs remain under %LOCALAPPDATA%/ScoutPermissionHelper/Portable/Runs until removed. Diagnostics can include control labels, local paths and process identities.

## Previous packages

[Beta 6](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0-beta.6.zip) · [Scout-only 3.1.4](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/ScoutPermissionHelper-Portable-3.1.4.zip) · [Release history](RELEASE-NOTES.md)

Independent project. Not affiliated with or endorsed by Microsoft.
