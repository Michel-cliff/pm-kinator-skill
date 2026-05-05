# Example 05: Proactive Roadmap Suggestion

**Scenario:** Skill spots a pattern across emails without being asked. Creates a ticket, then adapts when the user dismisses a follow-up suggestion.

---

*(No user message. Skill surfaces a signal during the session.)*

**Assistant:**

```
Roadmap signal detected
────────────────────────────────────────
Risk      CSV export missing from board
Milestone Billing v2
Signal    3 separate emails this week, same request, no ticket
Action    Add to backlog, evaluate for next milestone
```

This has come up three times in email with no ticket. Looks like an emerging priority. Want me to create one?

---

**User:** yeah create the ticket but don't add it to the current milestone, next one

**Assistant:**
On it. Staying out of Billing v2.

```
Title       Export billing data as CSV

Priority    Should
Reason      Requested independently by 3 users. Not blocking core flows,
            but high friction for expense management.

Description
Users need to export billing history for accounting and reporting.
No export option currently exists.

Acceptance criteria
- "Download CSV" button on billing history page
- CSV includes date, amount, description, invoice ID
- Covers full billing history, not just current page view
- Filename includes timestamp (billing-export-2025-05-05.csv)

Milestone    none, backlog
```

Added to backlog. Tag it when you're ready to schedule it.

---

*(Later in the session, different pattern detected.)*

**Assistant:**
You have four Should tickets with no update in 18 days. Want me to propose a cut list for the current milestone?

---

**User:** no I'll handle that myself

**Assistant:**
Got it. No more cut suggestions this session.

I'll still flag scope risk if something comes up, but the decisions stay with you.
