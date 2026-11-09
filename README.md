# @cpzombie/pi-raw-context-counter

[pi](https://pi.dev) coding agent extension: a TUI footer whose context
counter shows **raw token counts** (e.g. `25k/200k (auto)`) instead of a
percentage (e.g. `12.5%/200k (auto)`) — the absolute count is more useful
than a percentage, and rounding follows the built-in footer's token
formatting (24,600 tokens renders as `25k`).

## How it works

Replaces the built-in footer with a version that shows the context counter
in raw tokens. Everything else mirrors the built-in footer: pwd + git
branch + session name line, token stats (cache/cost omitted), color
thresholds (>90% red, >70% yellow), model name + thinking level on the
right, and the extension status line. It is a line-for-line mirror of the
built-in footer internals, so a pi release that changes the footer may need
a sync pass.

## Install

```bash
pi install npm:@cpzombie/pi-raw-context-counter
# or pinned to a version:
pi install npm:@cpzombie/pi-raw-context-counter@1.0.0
```

Uninstall (or `pi remove` then `/reload` in an interactive session):

```bash
pi remove npm:@cpzombie/pi-raw-context-counter
```

To revert to the built-in footer without uninstalling: run `/reload` after
disabling the extension, or `pi remove npm:@cpzombie/pi-raw-context-counter`.

## Notes

- The extension is TypeScript, loaded by pi via jiti — no build step.
- `@earendil-works/pi-coding-agent`, `-pi-ai`, and `-pi-tui` are peer
  dependencies provided by your pi installation; they are not bundled here.
