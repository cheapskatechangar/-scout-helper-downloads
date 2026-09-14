# Scout Permission Helper | Portable

Created by **CheapskateChangar**.

**STABLE release:** Portable 3.1.4 | Sep 14, 2026 7:25 PM -04:00

[Download Portable 3.1.4 ZIP](https://github.com/cheapskatechangar/-scout-helper-downloads/raw/refs/heads/main/dist/ScoutPermissionHelper-Portable-3.1.4.zip) · [Project website](https://scout-prompt-approver.vercel.app/) · [Release notes](RELEASE-NOTES.md)

Public downloads for the Windows Scout Permission Helper. No GitHub sign-in is required. Development history, internal notes, and run logs are not included here. The ZIP contains readable PowerShell and batch scripts.

## Quick start

1. Download the ZIP above, then extract both files into the same local folder.
2. Open Microsoft Scout, then double-click `Start-ScoutPermissionHelper.bat`.
3. Select the intended Scout window and permission labels.
4. Leave **Detect only** checked for your first run. Select **Start** to see matches without clicking.
5. To enable selected-button clicking, select **Stop**, clear **Detect only**, then select **Start** again.

Keep these two files together:

- `Start-ScoutPermissionHelper.bat`
- `ScoutPermissionHelper.Portable.ps1`

**Pause** suspends new actions after acknowledgement; **Resume** continues; **Stop** ends the helper run. Closing the interface stops its worker. Minimizing keeps it running. Stop before changing settings.

## Requirements and limits

Windows 10 or 11, Windows PowerShell 5.1, an unlocked interactive desktop, and the Microsoft Scout desktop app are required. No Power Automate, installer, extra modules, or administrator elevation is required. The scripts are unsigned; your organization's script controls can block them. Follow your approved signing or allowlisting process.

The helper recognizes three exact labels in the selected Scout window:

- Allow for this session
- Allow all file reads this session
- Allow all file writes this session

File-read and file-write choices start unchecked. Idle, run-duration, and request limits bound each run. Default limits are 5 idle minutes, 60 run minutes, and 100 invoke requests. Paused time counts toward the run-duration limit.

**A button label does not identify or validate the underlying operation.** This utility automates selected permission-button interactions; it does not provide approval from Microsoft or your organization. Use it only where permitted and for work whose scope you have reviewed. An invoked button or a changed prompt is not proof of backend success.

## Optional AI enhancement

Enable the checkbox for one editable follow-up message and a maximum count, default 3. Copy the message, paste and send it in the intended Scout conversation, then select **I sent it in Scout** to count the handoff. Copying does not count as sending.

Detect only and permission choices remain independent. The ordinary idle/run/request limits still apply. Pause and Stop also gate follow-up actions, and reaching the follow-up cap stops the helper.

**Automatic Scout completion detection and message sending are not implemented.** This is a manual follow-up feature, not unattended AI continuation. Stopping the helper does not cancel Scout's own task or recall text already copied or sent.

## Logs and privacy

Use **Open logs** to view run records under:

`%LOCALAPPDATA%\ScoutPermissionHelper\Portable\Runs\<run-id>`

Logs can contain local paths, process identities, and exception diagnostics. Review them before sharing. Follow-up message content is not written to run configuration or activity logs. Explicitly copied text may remain in clipboard history. Logs remain until you remove them.

## Verify the download

The [SHA-256 checksum](dist/ScoutPermissionHelper-Portable-3.1.3.zip.sha256) is published beside the ZIP. In PowerShell:

```powershell
Get-FileHash .\ScoutPermissionHelper-Portable-3.1.3.zip -Algorithm SHA256
```

Expected SHA-256:

`f766df6d8dbf6bf8bf1150025f61669a1d3480ef4b28bbfe591aa25b7277a1d2`

## Validation status

Pilot build. Portable 3.1.3 includes the 3.1.2 status, emergency-pause, summary, optional-AI, generic-window-label, and branding work plus a Windows shutdown hotfix so closing the app no longer races the UI timer or attempts to unregister a hotkey after the form handle is gone.

The project is independent and is not affiliated with or endorsed by Microsoft.
