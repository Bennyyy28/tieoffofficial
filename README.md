
<div align="center">

# Tieoff

**Tie off the loose ends your agents leave behind.**

Tieoff surfaces the open loops your Codex and Claude Code agents leave behind —
one calm, local inbox of unfinished work, so nothing falls through the cracks.

[![Latest release](https://img.shields.io/github/v/release/Bennyyy28/tieoffofficial?label=download&color=blue)](https://github.com/Bennyyy28/tieoffofficial/releases/latest)
&nbsp;·&nbsp; macOS (Apple Silicon) &nbsp;·&nbsp; local-first, your sessions never leave your Mac

<img src="docs/hero.png" alt="Tieoff — agents said done; the repo disagrees" width="820">

</div>

---

## The problem

You run coding agents all day. Sessions end with "done!" — and some of them are
lying. Work sits uncommitted. A blocker got mentioned in message 40 and never
resolved. A question is still waiting for your answer in a session you closed
last Tuesday. Multiply by two harnesses and a few hundred sessions, and things
fall through the cracks.

## What Tieoff does

- **Scans every session on your Mac** — Claude Code (`~/.claude`) and Codex
  (`~/.codex`), automatically discovered. No setup, no convention your agents
  have to follow, no cloud.
- **Detects open loops** — unfinished work, unanswered questions, blockers —
  and ranks them by evidence, not vibes.
- **Checks the repo, not the agent's word.** Tieoff's reconciliation engine
  compares what a session *claimed* against what git actually *shows*: a "done"
  with no commit and a dirty tree reads very differently from a "done" with a
  landed commit. Loops the repo contradicts surface first; loops the repo
  confirms ask for one click to close.
- **Closes the loop** — resolve, snooze, accept into a working set, copy a
  ready-to-paste follow-up prompt, or jump straight into the session file.
- **Feeds your agents back** — a built-in MCP server exposes your open loops as
  tools (`list_open_loops`, `get_loop`, `resolve_loop`, …), so Claude Code,
  Cursor, or any MCP harness can pull a loop, do the work, and mark it closed.

## Install

1. Download the latest `.dmg` from
   [Releases](https://github.com/Bennyyy28/tieoffofficial/releases/latest).
2. Open it, drag Tieoff to Applications, launch.
3. Onboarding finds your sessions and builds your first inbox in seconds.

Requirements: macOS on Apple Silicon (M-series). Signed and notarized — no
Gatekeeper gymnastics. Auto-updates via the built-in updater.

**Beta note:** 30-day full trial from first launch; after that the single-agent
view stays free, cross-agent view + MCP tools need a license.

## Local-first, by design

Your session transcripts are the most sensitive files on your machine. Tieoff
reads them locally, stores its state locally, and sends nothing anywhere.
Summaries use a local model when you have one (Ollama detected automatically)
and degrade gracefully to rule-based summaries when you don't. The repo checks
are read-only git operations, allowlisted to exactly four commands.

## Connect your agents (MCP)

Tieoff ships an MCP server so your harnesses can work the inbox themselves:

```bash
# Claude Code, one-liner (the app's MCP page has copy-paste configs for other harnesses)
claude mcp add tieoff -- /Applications/Tieoff.app/Contents/Resources/mcp-bin/agent-activity-mcp
```

Then: *"list my open loops"* → pick one → the agent does the work →
`resolve_loop`. The GUI and MCP share one store, so everything stays in sync.

## Feedback

This is a beta. If something reads wrong, flags nonsense, or misses work you
know was left hanging — that's exactly what we want to hear. Open an issue
here or reply to the DM that brought you.

---

<sub>Tieoff is independent software, not affiliated with Anthropic or OpenAI.
"Claude" and "Codex" refer to the third-party CLI tools whose local session
files Tieoff reads.</sub>
