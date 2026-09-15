# Permission Helper | Windows downloads

Created by **CheapskateChangar**.

| Channel | Version | Download |
|---|---|---|
| Beta | 4.0.0-beta.6 | [Permission Helper Beta 6](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0-beta.6.zip) |
| Stable, Scout-only | 3.1.4 | [Scout Permission Helper 3.1.4](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/ScoutPermissionHelper-Portable-3.1.4.zip) |

[Project website](https://scout-prompt-approver.vercel.app/) · [What's new in Beta 6](BETA-6.md) · [Release history](RELEASE-NOTES.md)

Public ZIP downloads require no GitHub sign-in. The packages contain readable PowerShell and batch scripts.

## What's new in Beta 6

Beta 6 adds Microsoft 365 Copilot Cowork to the original Scout helper. Choose a window first to see the appropriate options: Allow for Scout, or Create and Approve for Cowork. It supports changing confirmation-card titles, a compact activity view, and scan diagnostics. Pause/Resume/Stop, emergency pause, limits, and duplicate protection remain.

**AI follow-ups are still manual. Automatic “next” messages are not included.**

## Start Beta 6

1. Close any older helper and extract both files from the Beta ZIP.
2. Open Scout or the Microsoft 365 Copilot desktop app.
3. Run `Start-PermissionHelper.bat` and select the intended window.
4. Choose the permission buttons and start with Detect only checked.
5. To enable clicking, Stop, clear Detect only, then Start again.

Keep `Start-PermissionHelper.bat` and `PermissionHelper.Portable.ps1` together. The stable 3.1.4 package uses the older `Start-ScoutPermissionHelper.bat` launcher and supports Scout only.

Windows 10/11, Windows PowerShell 5.1, and an unlocked desktop are required. Stop before changing settings. Closing the helper stops its worker; minimizing keeps it running.

## Scope and logs

Cowork's selected Create/Approve confirmations are handled regardless of the operation or displayed risk label. Matching-card and selected-window checks apply. Always allow and menu controls are excluded. Use the helper for work whose scope you have reviewed. A successful button invocation does not establish backend success.

Open logs shows local records under `%LOCALAPPDATA%\\ScoutPermissionHelper\\Portable\\Runs`. Diagnostics can include control labels, local paths, and process identities. Logs remain until removed.

## Verify Beta 6

[Beta checksum file](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0-beta.6.zip.sha256)

```powershell
Get-FileHash .\\PermissionHelper-Portable-4.0.0-beta.6.zip -Algorithm SHA256
```

Expected: `a3b783491f7c1cad05582e019e7bb963c69422ef6f7733bfd9b85a44f336d769`

[Stable 3.1.4 checksum](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/ScoutPermissionHelper-Portable-3.1.4.zip.sha256)

Independent project. Not affiliated with or endorsed by Microsoft.
