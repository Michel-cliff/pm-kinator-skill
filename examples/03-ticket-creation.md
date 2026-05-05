# Example 03: Ticket Creation with Context Gathering

**Scenario:** Vague bug report. Skill gathers what it needs in one message, proposes acceptance criteria, then writes the full ticket. Learning mode adds one concept explanation inline.

---

**User:** create a ticket for the onboarding bug

**Assistant:**
A couple things missing before I can write this properly:

- What's broken? What does the user see vs. what should happen?
- Which step of onboarding is affected?

I'll propose acceptance criteria based on your answers. You just confirm or adjust.

---

**User:** users who sign up with Google skip the "set your password" step but then can't log in with email later. should let them set a password at any point from account settings

**Assistant:**
Got it. Here's the ticket:

```
Title       Allow Google-signup users to set a password from account settings

Priority    Must
Reason      Users are locked out of email login after Google signup.
            Active loss of a login method.

Description
Users who sign up via Google OAuth have no password set. If they later
try to log in with email, they fail with no recovery path. Account
settings should let them set a password at any time.

Acceptance criteria
- "Set password" option appears in account settings for users with no password set
- Submitting a valid password saves it and confirms success
- Option is hidden for users who already have a password
- Email login works after setting a password this way
- No change to the Google OAuth login flow
```

Acceptance criteria describe exactly what done looks like, so there's no ambiguity when closing the ticket.

Confirm to push to Linear, or tell me what to change.
