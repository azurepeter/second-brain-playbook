# Build an AI Second Brain with Claude Code

A playbook for building a personal knowledge base that maintains itself: scheduled agent runs that assemble a briefing before the working day, file everything captured during it, and leave the vault in a state worth opening the next morning.

This is the generic, placeholder-only version of a system that has run every weekday since it was built. Nothing in it is specific to my sources, employer or conventions — you answer an interview and it adapts.

**→ [`second-brain-playbook.md`](second-brain-playbook.md)**

## How to use it

Open Claude Code with your notes folder as the working folder and say:

> Read `second-brain-playbook.md` and build my second brain with it. Interview me first, and ask before anything that sends data outside this machine.

Allow an afternoon. You answer about sixteen multiple-choice questions, approve a few actions, and do the handful of things only you can — sign-ins, phone setup, a mail filter.

## What you end up with

- **Two Obsidian vaults** and one rules file every run reads first
- **A morning brief** — priorities, a prep block per meeting, replies owed, open tickets; Monday adds a weekly review
- **An evening wrap** — files captures, writes up meetings, closes finished tasks, sets up tomorrow
- **A backup brief** that writes the morning one only if the first failed or never started
- **Capture from everywhere** — a hotkey box on the laptop, a phone shortcut, photographed handwriting, a browser clipper
- **A daily backup** to a private repository, run outside the agent so it works whether or not the app is open
- **Optional modules** — health tracking from a one-line note or a fitness app's weekly email, and reference pages assembled from your own history

## What is in the playbook

Nine phases, each ending in a check you can actually run:

| | |
|---|---|
| **Phase 0** | Look before you connect anything — inventory, secret scan, and where work data is allowed to live |
| **Phase 1** | Interview |
| **Phase 2** | Vault structure, plus the rules-file and profile templates |
| **Phase 3** | Connectors, including several Atlassian sites from one machine |
| **Phase 4** | Permissions, so unattended runs never hit a prompt |
| **Phase 5** | The four scheduled runs, with their prompts |
| **Phase 6** | Daily backup |
| **Phase 7** | Capture everywhere |
| **Phase 8** | Test and tune — read the transcript, not just the output |
| **Phase 9** | Optional modules |

Plus **26 recorded gotchas**, each with a symptom, a cause and a fix. Roughly a third of them are not about the agent at all, but about the plumbing around it: how a scheduler behaves after the machine sleeps, which window styles stop drawing after a resume, why a mail filter does not apply to messages that already arrived.

Both PowerShell scripts are included in full — an always-on-top capture box with a self-test, and the daily backup job.

## Prerequisites

Claude Code (the desktop app, for scheduled tasks), Obsidian, and connectors for whatever you already use. The two scripts are written for Windows and PowerShell 7; the playbook tells Claude how to port them to macOS.

## Design notes

Two decisions do most of the work, and both are explained in the playbook:

- **Everything environment-specific lives in one rules file**, so the task prompts stay generic and a changed fact is changed in one place rather than four.
- **Scheduled runs are read-only on every external system**, enforced by the approved-tool list rather than by the prompt. A rule written in a prompt is input to a model; an unapproved tool is a gate outside it.

Written up in more detail at [newcombe.dev](https://newcombe.dev/).

## Licence

GPL-3.0. See [LICENSE](LICENSE).
