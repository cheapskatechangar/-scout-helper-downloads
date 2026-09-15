# Permission Helper Beta 6

Version: 4.0.0-beta.6. Channel: BETA.

Permission Helper Beta 6 expands the original Scout-only helper to Microsoft 365 Copilot Cowork. Select your window first: Scout shows Allow options, while Copilot shows Create and Approve. It handles changing confirmation-card titles and keeps session activity visible in a compact layout.

## Included

- Scout and Microsoft 365 Copilot in one window picker, with application-specific permission choices.
- Create and Approve matching across Cowork operation titles, including Microsoft Graph prompts, with matching-card and selected-window checks.
- Detect only, Start, Pause, Resume, Stop, emergency pause, idle/run/request limits, and duplicate-click protection.
- A compact interface, activity log, run summary, recent runs, and scan diagnostics.
- Two portable files: Start-PermissionHelper.bat and PermissionHelper.Portable.ps1.

**AI enhancement remains manual.** Automatic follow-up sending, including automatically sending “next,” is not included in Beta 6. Use Copy follow-up, send it yourself, then confirm I sent it.

## Quick start

1. Close an older helper, download the ZIP, and extract both files into one folder.
2. Open Scout or the Microsoft 365 Copilot desktop app, then launch Start-PermissionHelper.bat.
3. Select its window and the permission options to handle.
4. Start with Detect only checked. To enable clicking, Stop, clear Detect only, then Start again.

Cowork matching targets the observed Microsoft 365 Copilot desktop window title. Differently titled/localized or browser-hosted variants are not included. It handles selected confirmation actions regardless of operation or risk label. Always allow options and menu arrows are excluded. Approval does not guarantee the underlying operation succeeds.

## Release status

The maintainer accepted Beta 6 for public beta distribution following the test sequence. Creation, update, rename, subfolder creation, copy, and deletion attempts were exercised; some backend operations returned existing-name or unsupported-operation errors after approval. Acceptance does not establish compatibility with every Copilot version or environment.

311 automated checks passed individually in the development environment. Native Windows UI behavior was evaluated through the maintainer's live feedback. This remains a beta release.

## Download and checksum

[Download Beta 6](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0-beta.6.zip) · [SHA-256 file](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/PermissionHelper-Portable-4.0.0-beta.6.zip.sha256)

SHA-256: `a3b783491f7c1cad05582e019e7bb963c69422ef6f7733bfd9b85a44f336d769`

Windows 10/11, Windows PowerShell 5.1, and an unlocked desktop are required. No installer or Power Automate is needed. Independent project, not affiliated with or endorsed by Microsoft.
