# Changelog

All notable changes to Tieoff, newest first. Download any release from the
[Releases page](https://github.com/Bennyyy28/tieoffofficial/releases).

<!-- releasenotes:insert -->

## 0.1.9 — 2026-07-09

- **The open beta has ended.** The cross-agent **"All"** view — the combined
  Codex + Claude inbox, plus open-loop history and analytics — now requires a
  license. It unlocked automatically during the beta; after this update it will
  ask you to upgrade. The single-agent **Codex** and **Claude** views stay free,
  and nothing you've resolved, snoozed, or dismissed is lost.
- **Enter your license key in the app.** Settings now has a **License** section:
  paste the `AA-…` key from your purchase to unlock the cross-agent view. It
  shows your plan, your renewal date, and a masked copy of your key. Previously
  there was nowhere to enter a key you'd paid for.
- **Security:** hardened the read-only git integration against a hostile
  `.git/config`, removed shell access from the app's webview, tightened the
  local path checks, and validated more API input. No action needed.



## 0.1.8 — 2026-07-08

- **Updates:** when a new version is available, the app now shows a "Later / Install Now" prompt and can install + relaunch in one click, instead of asking you to quit and reopen manually.
- **Build visibility:** the Settings panel and `/api/health` now show the exact build (git SHA + build time), so you can confirm precisely which build you're running.

## 0.1.7 — 2026-07-08

- **Settings:** now shows the current app version.
- **Activity timeline:** your own messages are labeled "You" instead of a hard-coded name.

## 0.1.6 — 2026-07-08

- **Settings:** now displays the current app version number.

## 0.1.2 – 0.1.5 — beta maintenance (2026-07-07 – 08)

A run of internal/beta iterations, grouped here for brevity:

- **0.1.5:** the built-in auto-updater — the app checks for a newer version on launch and updates in place.
- **0.1.3:** an in-progress Agents view was gated behind a flag (off in shipped builds).
- **0.1.2:** inbox polish, clearer thread titles, and a leaner bundled MCP server.

*(0.1.4 was an internal release-pipeline fix with no user-facing change.)*

## 0.1.1 — 2026-07-06

The evidence release: the inbox now leads with what the repo can prove.

### New

- **Evidence tiers replace "Most urgent."** The inbox is now organized by
  what Tieoff can verify, not an editorial ranking: **Repo contradicts the
  claim** (the agent said done; git disagrees — with the receipts shown) →
  **Reconciled, confirm to close** (the repo backs the claim; one click
  closes it) → **Unverified** (no repo to check against) → **Worth a
  glance**. A status strip up top gives the counts at a glance.
- **Repo evidence everywhere it matters.** Loop cards show what was claimed
  vs. what git shows; the chat dialog now carries the same repo-facts block,
  so the place you decide has the evidence too.
- **Project view rebuilt.** Click a project and get *that project's* open
  loops in the same tiers with the same actions, fronted by a burn-down bar
  (resolved vs. open) — the timeline is still there, one click away.
- **Agent conventions, offered at setup.** Onboarding now offers (strictly
  opt-in, one-click skip) to append a short "session hygiene" block to your
  `CLAUDE.md`/`AGENTS.md` — rules like "commit before you report done" that
  make agents easier to audit and Tieoff's verification sharper.
- **Optional Touch ID app lock.** Turn it on in Settings and Tieoff asks for
  your fingerprint on launch — a sensible extra for an app whose whole job is
  reading your session history.
- **MCP connection status in the header**, and the theme toggle moved into
  Settings.

### Changed

- **30-day trial.** Fresh installs get every feature free for 30 days from
  first launch; after that the single-agent view stays free and the
  cross-agent view + MCP tools need a license. (v0.1.0 shipped fully
  unlocked; the gate is now real.)
- **The chat dialog slimmed down** — the stats sidebar is now a single meta
  line, and the summary gets the space.
- **Quieter with Ollama.** Tieoff no longer wakes your local model on every
  launch — it only asks for summaries when there's genuinely something new
  to summarize, and releases the model promptly afterward.

### Fixed

- "Didn't get to it" on an active loop now returns it to plain open instead
  of keeping a stale "Picked up" tag.
- Resolving a loop from the project view updates the inbox counts correctly.

## 0.1.0 — 2026-07-01

First release.

- **The open-loops inbox**: Tieoff scans every Claude Code and Codex session
  on your Mac and surfaces unfinished work — unanswered questions, abandoned
  tasks, steps handed back to you — in one local inbox.
- **Close the loop**: resolve, snooze, dismiss, or accept loops into an
  active working set; copy a ready-to-paste follow-up prompt; jump straight
  into the original session file.
- **MCP server built in**: attach Tieoff to Claude Code, Cursor, or any MCP
  harness and let your agents list, work, and resolve loops themselves.
- **Local summaries**: uses Ollama when you have it, degrades to rule-based
  summaries when you don't; nothing leaves your machine.
- **Native Mac app**: signed, notarized, auto-updating, with guided
  first-run onboarding.
