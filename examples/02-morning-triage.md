# Example 02: Morning Triage

**Scenario:** Gmail and Linear connected. Three unread emails, two open Must tickets, one pattern emerging.

---

**User:** Triage my morning

**Assistant:**

```
Morning Triage, May 5
════════════════════════════════════════

Emails to act on

  "Re: API integration broken" (david@acme.com)
      Webhook stops firing after v2 deploy.
      -> Create ticket

  "Quick question on pricing" (lea@startup.io)
      Prospective customer asking about annual plan discount.
      -> Reply

  "Partnership opportunity" (growth@vendorco.com)
      Cold outreach, no fit signal.
      -> Ignore

────────────────────────────────────────

Blockers

  [Must] Implement rate limiting on /export endpoint
      Open 11 days. No update. No acceptance criteria.
      Someone is waiting on this to close the billing milestone.

────────────────────────────────────────

Must tickets needing attention

  [Must] Fix SAML login for enterprise accounts
      Last updated 9 days ago. No owner.
      -> Confirm if still blocking the enterprise pilot or move to Should.

────────────────────────────────────────

Roadmap signals

  Three separate emails this week mentioned missing CSV export.
  No ticket exists. May be an emerging priority.

────────────────────────────────────────

Focus for today

  1. Create the webhook ticket and reply to David.
        External customer, unblocks their integration.
  2. Clarify the rate limiting ticket.
        No acceptance criteria means it can't close cleanly.
  3. Reply to Lea on pricing.
        Short, fast, moves a prospect forward.
```

Ready to move. Say "create the webhook ticket", "draft the Lea reply", or pick a number.
