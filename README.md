# Codex Usage Tracker

Codex Usage Meter is a lightweight Cursor and VS Code extension for tracking Codex usage with minimal friction.

It focuses on the signals that are actually useful during real work:
- weekly usage
- current task burn
- lightweight local task history

The extension is designed to stay unobtrusive. You can glance at a compact status bar item when available, or use the small sidebar view as a stable fallback inside Cursor.

This project is currently weekly-first. OpenAI's visible 5-hour meter has become inconsistent or unavailable in recent Codex surfaces, so the extension treats weekly usage as the primary live signal and keeps older 5-hour logic as legacy fallback where possible.




## Installation

1. Download the latest `.vsix` file from the [Releases page](https://github.com/threshold-lion/Codex-Usage-Tracker/releases).
2. In Cursor or VS Code, Press `F1` or `Ctrl+Shift+P`.
3. Run `Extensions: Install from VSIX...`.
4. Select the downloaded `.vsix` file.
5. Reload the editor if necessary.

## Usage

Use the Command Palette to access the main commands:

- `Codex Usage: Start Task`
- `Codex Usage: Stop Task`
- `Codex Usage: Quick Stop Task`
- `Codex Usage: Show Current Burn`
- `Codex Usage: Show Live Audit`
- `Codex Usage: Show History Summary`

The extension currently treats weekly Codex usage as the primary live signal and keeps a lightweight local task history for quick review and export.

## Notes

OpenAI's visible 5-hour Codex meter has recently become inconsistent or unavailable in some surfaces, so this extension currently focuses on weekly usage as the most reliable live value.

## Accuracy note

Codex Usage Tracker reads usage signals from local Codex/session data when that data is available. Because this is not an official billing or quota API, the displayed value can sometimes be delayed, stale, incomplete, or temporarily wrong.

In practice, the tracker may occasionally show values such as `0%`, `100%`, or an older weekly value when fresh data has not been written yet. It usually corrects itself once newer Codex session data becomes available.

Treat the extension as a practical usage tracker and warning aid, not as an authoritative quota meter.

## History storage

Codex Usage Tracker works immediately after installation. By default, it stores task history in the editor's local extension storage.

If you want a visible or portable history file, run:

- `Codex Usage: Set Data File`

Choose a `.json` file location. After that, completed task history will be written to that file, and backup copies will be created alongside it when the file is updated.

Active tasks are local to the current editor window. Completed tasks are the part that gets saved into the shared history file.

## Possible future improvements

This is an early release. Possible future improvements include:

- better handling of stale or missing usage data
- clearer warnings when the tracker cannot find fresh Codex session data
- improved task burn estimates
- optional charts or weekly summaries
- better support for multi-window and multi-project workflows
- support for restored or changed 5-hour usage signals if OpenAI exposes them again

