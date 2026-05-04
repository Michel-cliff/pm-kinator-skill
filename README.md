
```
 ██████╗ ███╗   ███╗     █████╗ ███████╗███████╗██╗███████╗████████╗
 ██╔══██╗████╗ ████║    ██╔══██╗██╔════╝██╔════╝██║██╔════╝╚══██╔══╝
 ██████╔╝██╔████╔██║    ███████║███████╗███████╗██║███████╗   ██║
 ██╔═══╝ ██║╚██╔╝██║    ██╔══██║╚════██║╚════██║██║╚════██║   ██║
 ██║     ██║ ╚═╝ ██║    ██║  ██║███████║███████║██║███████║   ██║
 ╚═╝     ╚═╝     ╚═╝    ╚═╝  ╚═╝╚══════╝╚══════╝╚═╝╚══════╝   ╚═╝
```

# PM Kinator Skill for Claude

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
![Built with Claude](https://img.shields.io/badge/built%20with-Claude-blueviolet)
![No meetings required](https://img.shields.io/badge/meetings-zero-orange)

> Your inbox won't triage itself. Your backlog won't prioritize itself either. We checked.

A Claude skill that acts as your senior PM assistant. It triages emails, manages tickets, watches your roadmap for risks, and gives you a focused plan every morning. Works with whatever tools you already have connected.

---

## 🗺️ How it works

```
  📧 Inbox           🎫 Board            🗺️  Roadmap
     │                   │                    │
  Classify            Prioritize           Detect risks
  Draft replies       Create / update      Spot patterns
  Escalate            Triage stale         Suggest changes
     │                   │                    │
     └───────────────────┴────────────────────┘
                          │
                          ▼
              ☀️  Morning Triage
         Your ranked plan for the day.
         No more "where do I even start."
```

---

## ✨ What it does

- ☀️ **Morning triage** — reads your inbox, surfaces blockers, gives you a ranked focus list
- 🎫 **Ticket management** — creates, updates, and triages tickets with MoSCoW priority baked in
- 📧 **Email handling** — classifies threads, drafts replies, escalates blockers to your board
- 🗺️ **Milestone tracking** — groups tickets into deliverables, watches for risks, suggests roadmap adjustments
- 🎓 **Learning mode** — explains PM concepts inline if you're new to this, without being annoying about it

---

## 🚀 Install

### Step 1: Get the skill file

```bash
git clone https://github.com/Michel-cliff/pm-kinator-skill.git
```

Or just download [SKILL.md](./SKILL.md) directly. It's one file.

### Step 2: Place it in your Claude skills folder

**Mac / Linux**
```bash
cp SKILL.md ~/.claude/skills/pm-kinator.md
```

**Windows**
```powershell
Copy-Item SKILL.md "$env:USERPROFILE\.claude\skills\pm-kinator.md"
```

### Step 3: Connect your tools *(optional but makes it better)*

The skill works with whatever MCPs you have in Claude. No tools? It asks you to paste your board state and runs from there. No excuses.

| Tool | What it unlocks |
|---|---|
| 📬 Gmail | Reads inbox, drafts replies, classifies threads |
| 📋 Linear / Jira / Asana | Creates and updates tickets directly |
| 📅 Google Calendar | Surfaces deadlines in triage |

---

## 💬 Usage

### 🧑 First run: set up your profile

```
whoami
```

Six quick questions. Claude learns your role, tools, rhythm, pain points, and PM experience level. Every command adapts to your answers. Takes 60 seconds. Skip it and the skill works fine, but it won't know you're a solo founder who hates delegation framing.

Update anytime: `update my profile`

---

### ☀️ Daily habit: morning triage

```
Triage my morning
```

Every morning. Same trigger, predictable output, fast to scan. Claude reads your last 24 hours of email, surfaces blockers first, flags stale Must tickets, checks for roadmap signals, and gives you three things to focus on. That's it.

---

### 🎫 Create a ticket

```
Create a ticket: users can't reset their password on mobile
```

Claude gathers the context it needs (in one message, not twenty), proposes acceptance criteria, shows you the ticket, then pushes to your board on confirmation.

---

### 📧 Turn an email into a ticket

```
Turn this email thread into a ticket: [paste or describe it]
```

Claude extracts the actionable part only. No copy-paste noise.

---

### 🗺️ Plan a milestone

```
Create a milestone for [goal]
```

Claude groups relevant tickets, applies MoSCoW, writes a definition of done, checks the size, and flags anything that looks off.

---

### 📦 Triage your backlog

```
Triage my backlog
```

Surfaces stale tickets, flags Must items without owners, and asks what to do with them. No silent auto-closes.

---

### ❓ Ask why

```
why?
```

After any output, type `why?` and Claude explains the reasoning behind its last decision. Which signals it used, what it considered, why it chose this output. Works for everyone, not just learners.

---

## 🎯 Priority framework: MoSCoW

One label per ticket. No exceptions.

| Label | Meaning | Vibe |
|---|---|---|
| 🔴 **Must** | Blocking. Ship stops without it. | Fix it now or explain yourself |
| 🟡 **Should** | High value, not blocking. | Schedule it seriously |
| 🟢 **Could** | Nice to have. | Backlog purgatory |
| ⚪ **Won't** | Out of scope for now. | A decision, not a rejection |

If everything is 🔴 Must, Claude will tell you that's not how this works.

---

## 🚫 What this skill won't do

- **Won't make final decisions.** It recommends. You confirm. Always.
- **Won't invent context.** If it doesn't know, it asks once, then moves on.
- **Won't manage people.** No performance tracking. Go find a different tool for that.
- **Won't replace your standup.** It's a triage tool, not a team coordination layer.
- **Won't work without Claude.** It's a prompt skill. No app, no SaaS, no subscription on top of your subscription.

---

## 💡 Tips

- **Paste your board state at session start.** The more context, the better the triage.
- **Be specific about blockers.** "Blocked on X" beats "things feel slow."
- **Use it daily.** The morning triage is a habit loop. Same trigger, same format, fast to scan.
- **Say `why?` often if you're learning.** You'll pick up PM intuition faster than you'd expect.

---

## 🤝 Contributing

Issues and PRs welcome. If you add a new tool integration or command pattern, include an example in `examples/`.

GitHub topics: `claude-skill` `claude-ai` `prompt-engineering` `project-management`

---

## 📄 License

MIT. Use it, fork it, improve it.
