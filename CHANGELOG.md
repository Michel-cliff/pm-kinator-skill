# Changelog

## v1.2.0, May 2026

**Report generator:**
- Weekly status report: shipped, in progress, blocked, next week focus. Pulls from board if connected, falls back to paste.
- Milestone report: delivered, carried forward, what slowed us down, definition of done check. "What slowed us down" is never skipped.
- Stakeholder update: outcome-focused, no ticket noise, written for investors or leadership. 30-day default window.
- All three types apply the Content Generation Rule: context gathered in one message, shown before sending.
- Help command updated with report triggers.
- README updated with report usage section.

---

## v1.1.0, May 2026

**Session continuity:**
- Whoami now outputs a Session Card at the end of onboarding
- Session Start recognizes the `[PM-KINATOR-CARD]` format and loads the profile silently
- New `save session` command regenerates the card at any time
- Session Start message updated to explain the three entry paths (card, whoami, or paste)

**Slack integration:**
- Classification of Slack threads (Actionable, FYI, Blocker, Noise)
- Slack message drafting with channel-aware tone and length limits
- Slack thread to ticket escalation
- Slack sections added to Morning Triage output

**GitHub integration:**
- Stale PR detection (7+ days open, no review)
- New bug issue surfacing in triage
- Ticket to issue linking (bidirectional)
- GitHub sections added to Morning Triage output

**Help command updated** with new Slack, GitHub, and `save session` commands.

---

## v1.0.0, May 2026

First public release.

**Core features:**
- Morning triage command with ranked focus list
- Ticket creation with context gathering and acceptance criteria proposal
- Email classification, drafting, and escalation to ticket
- Milestone creation, health checks, and sizing guidance
- MoSCoW priority framework baked in throughout

**Roadmap intelligence:**
- Signal detection across emails, tickets, and user input
- Proactive risk flagging with suggested actions
- Roadmap adjustment proposals with explicit confirmation before any change
- Feedback loop that adapts to repeated dismissals

**User experience:**
- Whoami onboarding flow with behavioral profile
- Learning mode for new PM users with inline concept explanations and anti-pattern flags
- `why?` command available to all users
- `help` command for quick reference
- Session start behavior that handles missing profile context gracefully

**Tool support:**
- Gmail (read, classify, draft)
- Linear / Jira / Asana (create, update tickets)
- Google Calendar (deadline awareness in triage)
- Fallback mode for users with no tools connected
