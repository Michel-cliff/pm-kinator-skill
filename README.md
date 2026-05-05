
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

## Install

### Step 1: Get the skill file

```bash
git clone https://github.com/Michel-cliff/pm-kinator-skill.git
```

Or just download [SKILL.md](./SKILL.md) directly. It's one file.

### Step 2: Place it in your Claude skills folder

**Mac / Linux**
```bash
mkdir -p ~/.claude/skills/pm-kinator
cp SKILL.md ~/.claude/skills/pm-kinator/SKILL.md
```

**Windows**
```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills\pm-kinator"
Copy-Item SKILL.md "$env:USERPROFILE\.claude\skills\pm-kinator\SKILL.md"
```

### Step 3: Connect your tools

The skill adapts to whatever MCPs you have configured in Claude. It does not care which specific product you use, only which category it belongs to.

| Category | Examples | What it unlocks |
|---|---|---|
| Email | Gmail, Outlook, any other | Reads inbox, drafts replies, classifies threads |
| Board / PM | Linear, Jira, Asana, Monday, ClickUp, Notion, Trello, Shortcut, Height, Basecamp, and others | Creates and updates tickets directly |
| Messaging | Slack, Microsoft Teams, Discord, and others | Reads threads, drafts messages, converts threads to tickets |
| Calendar | Google Calendar, Outlook Calendar, and others | Surfaces deadlines in triage |
| Code platform | GitHub, GitLab, Bitbucket, Azure DevOps, and others | Tracks stale PRs, links issues to tickets, flags new bugs |

**The experience scales with what you connect:**

| Setup | What you get |
|---|---|
| No tools | Manual mode. Paste your inbox and board state, get structured output to copy-paste. Still useful, more friction. |
| Board tool only | Ticket creation, triage, and milestone management work automatically. Morning triage needs manual email paste. |
| Email + board | Full morning triage. Automatic email classification, ticket creation, and roadmap signals. |
| Email + board + messaging | Complete picture. Blockers from all channels surface in one place. |
| All categories | Maximum signal. Roadmap intelligence has the most data to work with. |

No tools at all? The skill still works. It will ask you to paste context and output text you can copy into whatever you use.

---

## Usage

### First run: set up your profile

```
whoami
```

Six quick questions. Claude learns your role, tools, rhythm, pain points, and PM experience level. Every command adapts to your answers. Takes 60 seconds. Skip it and the skill works fine, but it won't know you're a solo founder who hates delegation framing.

Your profile is saved automatically to disk. Next session, the skill loads it silently and picks up where you left off. No copy-pasting required.

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

After any output, type `why?` and Claude explains the reasoning behind its last decision. Which signals it used, what it considered, why it chose this output. Works for everyone, not just learners.

---

### Draft a message on your messaging tool

```
Draft a message to [name or channel] on [Slack / Teams / other]: [context]
```

Claude keeps it short (3 sentences for DMs, 5 lines for channels) and matches the tone of the channel. Works with Slack, Teams, Discord, or whatever messaging tool you have connected.

---

### Turn a code platform issue into a ticket

```
Turn this issue into a ticket: [URL or paste]
```

Claude extracts the actionable part, links the issue URL in the ticket description, and proposes acceptance criteria. Works with GitHub, GitLab, Bitbucket, Azure DevOps, and others.

---

### Generate a report

Three types, each adapted to its audience:

```
Generate a weekly status report
```
What shipped, what's blocked, what's next. For yourself, your team, or a manager. Pulls from the last 7 days of ticket activity if your board is connected.

```
Generate a milestone report for [milestone name]
```
What was delivered, what carried forward and why, what slowed things down. Triggered when a milestone closes. Honest by design: "what slowed us down" is never skipped.

```
Generate a stakeholder update
```
Outcome-focused, no ticket noise, no internal jargon. Written for investors, board members, or leadership. Timeframe defaults to the last 30 days.

---

### Save your session

```
save session
```

Saves your current profile and session context to disk: open items, key decisions, and any risks flagged this session. The skill reads this automatically at the start of your next session.

---

### Get help

```
help
```

Prints the full command reference in one clean block. Useful when you forget a command name or want to show the skill to someone new.

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
