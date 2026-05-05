
```
██████╗ ███╗   ███╗    ██╗  ██╗██╗███╗   ██╗ █████╗ ████████╗ ██████╗ ██████╗ 
██╔══██╗████╗ ████║    ██║ ██╔╝██║████╗  ██║██╔══██╗╚══██╔══╝██╔═══██╗██╔══██╗
██████╔╝██╔████╔██║    █████╔╝ ██║██╔██╗ ██║███████║   ██║   ██║   ██║██████╔╝
██╔═══╝ ██║╚██╔╝██║    ██╔═██╗ ██║██║╚██╗██║██╔══██║   ██║   ██║   ██║██╔══██╗
██║     ██║ ╚═╝ ██║    ██║  ██╗██║██║ ╚████║██║  ██║   ██║   ╚██████╔╝██║  ██╗
╚═╝     ╚═╝     ╚═╝    ╚═╝  ╚═╝╚═╝╚═╝  ╚═══╝╚═╝  ╚═╝   ╚═╝    ╚═════╝ ╚═╝  ╚═╝
```

# PM Kinator Skill for Claude

![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![Built with Claude](https://img.shields.io/badge/built%20with-Claude-blueviolet)
![No meetings required](https://img.shields.io/badge/meetings-zero-orange)

> Your inbox won't triage itself. Your backlog won't prioritize itself either. We checked.

A Claude skill that acts as your senior PM assistant. It triages emails, manages tickets, watches your roadmap for risks, and gives you a focused plan every morning. Works with whatever tools you already have connected.

---

## How it works

```
  Inbox              Board               Roadmap
     |                   |                    |
  Classify            Prioritize           Detect risks
  Draft replies       Create / update      Spot patterns
  Escalate            Triage stale         Suggest changes
     |                   |                    |
     +-------------------+--------------------+
                          |
                          v
              Morning Triage
         Your ranked plan for the day.
         No more "where do I even start."
```

---

## What it does

- **Morning triage:** reads your inbox, surfaces blockers, gives you a ranked focus list
- **Ticket management:** creates, updates, and triages tickets with MoSCoW priority baked in
- **Email handling:** classifies threads, drafts replies, escalates blockers to your board
- **Milestone tracking:** groups tickets into deliverables, watches for risks, suggests roadmap adjustments
- **Learning mode:** explains PM concepts inline if you're new to this, without being annoying about it

---

## Getting started

### Option A: Claude.ai (recommended for most users, no setup required)

You only need a Claude.ai account. No installation, no technical setup.

**Step 1: Create a Project**

1. Go to claude.ai and sign in.
2. Click "Projects" in the left sidebar, then "New project".
3. Give it a name, for example "PM Kinator".

**Step 2: Add the skill as project instructions**

1. Inside your project, click "Set project instructions" (or the settings icon).
2. Open [SKILL.md](./SKILL.md) in this repo, select all the text, and copy it.
3. Paste it into the project instructions field and save.

That's it. Every conversation you start inside this project will have PM Kinator active.

**Step 3: Connect your tools (optional but recommended)**

Claude.ai lets you connect external tools through its built-in integrations. No technical setup needed.

1. Go to claude.ai Settings > Integrations.
2. Connect the tools you use: Gmail, Google Drive, Google Calendar, and others available in the list.
3. Come back to your PM Kinator project and start a conversation. The skill will automatically use whatever you connected.

**What to expect without connected tools:** The skill still works. It will ask you to paste your inbox summary and board state, and work from that. More friction, same logic.

**A note on profile persistence in Claude.ai:** Claude.ai does not have access to your file system, so your profile cannot be saved automatically between sessions. Run `whoami` on your first conversation, then use `save session` at the end to get a compact profile block. Copy it and paste it at the start of your next conversation to restore your settings instantly.

---

### Option B: Claude Code (for developers and technical users)

Claude Code is Anthropic's CLI and IDE tool. It supports skills as slash commands and has full file system access, so your profile persists automatically between sessions.

**Step 1: Get the skill file**

```bash
git clone https://github.com/Michel-cliff/pm-kinator-skill.git
```

Or download [SKILL.md](./SKILL.md) directly.

**Step 2: Place it in your Claude skills folder**

Mac / Linux
```bash
mkdir -p ~/.claude/skills/pm-kinator
cp SKILL.md ~/.claude/skills/pm-kinator/SKILL.md
```

Windows
```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills\pm-kinator"
Copy-Item SKILL.md "$env:USERPROFILE\.claude\skills\pm-kinator\SKILL.md"
```

Restart Claude Code. Type `/pm-kinator` to invoke the skill.

**Step 3: Connect your tools**

Claude Code uses MCP (Model Context Protocol) servers for tool integrations. You install a server once and it is available in every session.

| Tool | How to connect |
|---|---|
| Gmail | Add the Gmail MCP to your Claude Code config |
| Google Calendar | Add the Google Calendar MCP |
| GitHub | Add the GitHub MCP |
| Slack | Add the Slack MCP |
| Linear, Jira, Notion, and others | Community MCPs available, quality varies |

Search for "Claude MCP [tool name]" to find setup instructions for the tool you want. Once an MCP is configured, PM Kinator will use it automatically with no changes needed.

No tools connected? The skill still works. Paste your board state or inbox summary at the start of a session and it will work from that.

---

## What you can connect

The skill adapts to whatever is available. It does not require any specific tool.

| Category | Examples |
|---|---|
| Email | Gmail, Outlook |
| Board / PM | Linear, Jira, Asana, Monday, ClickUp, Notion, Trello, Shortcut, Basecamp |
| Messaging | Slack, Microsoft Teams, Discord |
| Calendar | Google Calendar, Outlook Calendar |
| Code platform | GitHub, GitLab, Bitbucket, Azure DevOps |

The more you connect, the more the skill can do automatically. But it is useful even with nothing connected.

---

## Usage

### First run: set up your profile

```
whoami
```

Six quick questions. Claude learns your role, tools, rhythm, pain points, and experience level. Every command adapts to your answers. Takes 60 seconds.

On Claude Code: your profile is saved to disk automatically and loaded next session.
On Claude.ai: run `save session` at the end of each conversation and paste the output at the start of the next one.

Update anytime: `update my profile`.

---

### Daily habit: morning triage

```
Triage my morning
```

Every morning. Same trigger, predictable output, fast to scan. Claude reads your last 24 hours of email, surfaces blockers first, flags stale Must tickets, checks for roadmap signals, and gives you three things to focus on. That's it.

---

### Create a ticket

```
Create a ticket: users can't reset their password on mobile
```

Claude gathers the context it needs (in one message, not twenty), proposes acceptance criteria, shows you the ticket, then pushes to your board on confirmation.

---

### Turn an email into a ticket

```
Turn this email thread into a ticket: [paste or describe it]
```

Claude extracts the actionable part only. No copy-paste noise.

---

### Plan a milestone

```
Create a milestone for [goal]
```

Claude groups relevant tickets, applies MoSCoW, writes a definition of done, checks the size, and flags anything that looks off.

---

### Triage your backlog

```
Triage my backlog
```

Surfaces stale tickets, flags Must items without owners, and asks what to do with them. No silent auto-closes.

---

### Ask why

```
why?
```

After any output, type `why?` and Claude explains the reasoning behind its last decision. Works for everyone, not just learners.

---

### Draft a message

```
Draft a message to [name or channel] on [Slack / Teams / other]: [context]
```

Claude keeps it short (3 sentences for DMs, 5 lines for channels) and matches the tone of the channel.

---

### Turn a code platform issue into a ticket

```
Turn this issue into a ticket: [URL or paste]
```

Claude extracts the actionable part, links the issue URL in the ticket description, and proposes acceptance criteria.

---

### Generate a report

```
Generate a weekly status report
```
What shipped, what's blocked, what's next. Pulls from the last 7 days of ticket activity if your board is connected.

```
Generate a milestone report for [milestone name]
```
What was delivered, what carried forward and why, what slowed things down.

```
Generate a stakeholder update
```
Outcome-focused, no ticket noise, no internal jargon. Written for investors, board members, or leadership.

---

### Save your session

```
save session
```

On Claude Code: saves profile and session context to disk automatically.
On Claude.ai: outputs a compact profile block to copy and paste at the start of your next conversation.

---

### Get help

```
help
```

Prints the full command reference in one clean block.

---

## Priority framework: MoSCoW

One label per ticket. No exceptions.

| Label | Meaning | When to use |
|---|---|---|
| **Must** | Blocking. Ship stops without it. | Fix it now or explain yourself |
| **Should** | High value, not blocking. | Schedule it seriously |
| **Could** | Nice to have. | Backlog purgatory |
| **Won't** | Out of scope for now. | A decision, not a rejection |

If everything is Must, Claude will tell you that's not how this works.

---

## What this skill won't do

- **Won't make final decisions.** It recommends. You confirm. Always.
- **Won't invent context.** If it doesn't know, it asks once, then moves on.
- **Won't manage people.** No performance tracking. Go find a different tool for that.
- **Won't replace your standup.** It's a triage tool, not a team coordination layer.
- **Won't work without Claude.** It's a prompt skill. No app, no SaaS, no subscription on top of your subscription.

---

## Tips

- **Paste your board state at session start.** The more context, the better the triage.
- **Be specific about blockers.** "Blocked on X" beats "things feel slow."
- **Use it daily.** The morning triage is a habit loop. Same trigger, same format, fast to scan.
- **Say `why?` often if you're learning.** You'll pick up PM intuition faster than you'd expect.

---

## Contributing

Issues and PRs welcome. If you add a new tool integration or command pattern, include an example in `examples/`.

GitHub topics: `claude-skill` `claude-ai` `prompt-engineering` `project-management`

---

## Privacy and data

- **Your data stays in your Claude session.** PM Kinator does not collect, store, or transmit any data. Everything it reads or generates lives inside your Claude conversation. Anthropic's privacy policy governs how that session data is handled.
- **You are responsible for what you connect.** If your tools contain customer PII, confidential business data, or information subject to privacy regulations (GDPR, CCPA, HIPAA, and others), it is your responsibility to ensure your use of this skill complies with those obligations before connecting them.
- **Do not paste regulated data without understanding your obligations.** This includes customer email addresses, personal identifiers, health information, or financial records. When in doubt, anonymize before pasting.

---

## Disclaimer

This skill is provided as-is, with no warranty of any kind. The author is not liable for decisions made based on its output, data processed through it, or any consequences of its use. Always review generated content before acting on it or sending it.

---

## License

Free to use, copy, modify, and distribute. Any derivative work must carry the same terms.

The author provides no warranty and accepts no liability for any harm, loss, or consequence arising from use of this skill or its output. Users are responsible for their own compliance with applicable laws and platform terms.

See [LICENSE](./LICENSE) for the full text.
