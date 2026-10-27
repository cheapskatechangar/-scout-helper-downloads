# Scout permissions below the conversation viewport

**October 27 acceptance update:** the maintainer confirmed "its working!" after trying the local build and authorized stable publication. This fix is promoted to 4.0.0. The earlier inspection and unverified status below describe the state before that user-reported live acceptance; other target/provider combinations still need their own validation.

Scout can leave the conversation scrolled above its current permission prompt and show a small down arrow above the composer. The old helper rejected offscreen approval buttons and never brought them into view, so it could wait without finding an eligible action.

The development fix finds an exact selected, enabled session permission Button in the bound Scout/Autopilot window. If it is offscreen and exposes both InvokePattern and ScrollItemPattern, it requests ScrollIntoView once per control identity per run. It then waits for the next worker tick and rescans. Approval still requires the normal visible, enabled, nonzero-size button checks and immediate cancellation/target checks. Navigation does not count as an approval or reset the idle timeout. A pending approval blocks further navigation.

Detect only performs no navigation. Cowork behavior is unchanged. The helper does not click the unlabeled down arrow, open More ways to allow, choose Always allow, or expand permission scope. A scroll failure is logged and is not retried for that control during the run.

If Scout does not expose the hidden button, does not provide ScrollItemPattern, or keeps the control offscreen after scrolling, click the conversation down arrow manually. The helper continues to require a visible approval button. There is no coordinate or keyboard fallback.

## Evidence and acceptance

Live read-only inspection on October 27, 2026 found Scout (Frontier) exposing the exact Allow for this session Button while the conversation down arrow was visible. The arrow did not expose a named Button in the captured accessibility tree. This observation does **not** verify native ScrollItemPattern support or successful scrolling.

Regression fixtures exercise hidden-to-visible navigation followed by fresh validation and approval, one-attempt bounds, unsupported providers, scroll failure, Detect only, Cowork exclusion, cancellation, controller/target loss and unavailable desktop. The real worker/scanner/reveal/approval pipeline is covered using simulated controls and a virtual clock. These tests do not establish live Scout acceptance.

October 27 validation: the initial full gate passed all then-current 432 checks and built/verified the two-file ZIP, payload and checksum. Five additional worker integration assertions subsequently passed (49 new checks total). Repeat full gates failed in the existing atomic file-replacement test with `Unable to remove the file to be replaced`. The same failure was reproduced using unchanged HEAD source in an isolated baseline folder. A later 4.0.0 full gate passed all 437 checks using C:/GitHub/scout-validation-temp as TEMP. No production file-replacement code or assertions were changed; the directory-specific cause remains unconfirmed. The maintainer then accepted the Scout fix for stable release.

Before publication:

1. Extract the newly built local Beta 7 ZIP and restart the helper.
2. Use a harmless reviewed Scout permission prompt. Scroll above it so the conversation down arrow appears.
3. In Detect only, confirm the helper does not scroll or approve anything.
4. Stop, enable only the intended session action, clear Detect only and start. Check for PermissionRevealRequested followed by the exact Invoked label and verify the prompt disappears. If there is no reveal event, native ScrollItemPattern support remains unverified; use the manual arrow.
5. Repeat with Pause/Stop, an unsupported provider, and a persistent prompt. Confirm no repeated scrolling or duplicate approval.

The maintainer authorized stable publication on October 27 after confirming the Scout fix works. See RELEASE-4.0.0.md for the upgrade path.
