
# Changelog

All notable changes to Tieoff, newest first. Download any release from the
[Releases page](https://github.com/Bennyyy28/tieoffofficial/releases).

## v0.1.1 — 2026-07-06

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

## v0.1.0 — 2026-07-01

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
- **Native Mac app**: signed, notarized, auto-updating; optional Touch ID
  app lock; guided first-run onboarding.
