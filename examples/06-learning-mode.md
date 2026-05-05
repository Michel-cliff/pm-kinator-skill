# Example 06: Learning Mode and the Why Command

**Scenario:** User in learning mode tries to create a 12-ticket milestone called "make the app better" and labels everything Must. The skill does not silently comply. It teaches.

---

**User:** create a milestone called "make the app better" with these tickets: fix slow load, better UI, add dark mode, fix the login bug, improve error messages, add CSV export, fix mobile layout, add notifications, better onboarding, refactor the auth module, add SSO, update the docs

**Assistant:**
A few things to flag before I create this.

**Milestone name:** "Make the app better" describes a direction, not an outcome. It'll be hard to know when this is done. Something like "Improve core stability" or "Ship mobile v2" gives the milestone a finish line. Want me to suggest a name based on the tickets?

**Milestone size:** 12 tickets is at the high end. A well-scoped milestone usually runs 3 to 15 tickets covering 1 to 4 weeks of work. Worth checking if some of these belong in a later milestone.

A milestone groups related tickets into a single shippable outcome, making it easier to track progress and communicate status.

Create as-is, or trim first?

---

**User:** yeah trim it, keep the most important ones

**Assistant:**
To trim well I need one signal. What's the most important outcome right now: stability, mobile experience, or enterprise readiness?

---

**User:** stability

**Assistant:**
Keeping what directly affects reliability and core flow. Everything else moves to backlog.

```
Milestone: Core stability pass
────────────────────────────────────────

In milestone

  [Must]   Fix slow load
  [Must]   Fix the login bug
  [Should] Fix mobile layout
  [Should] Improve error messages
  [Should] Refactor the auth module
           (labeled Should: foundational but no user faces it directly today)

Moved to backlog

  Better UI, dark mode, CSV export, notifications,
  better onboarding, SSO, update the docs

Definition of done
  - Load time under 2 seconds on main dashboard
  - Login flow has no known failures
  - No critical mobile issues blocking key actions
```

Confirm to create in Linear, or adjust anything.

---

**User:** why did you label auth module as Should and not Must?

**Assistant:**
The auth refactor improves internal code quality and reduces future risk, but it doesn't surface to users directly. Nothing in this milestone blocks on it, and no user is reporting a broken experience caused by the current auth code.

That's the Should definition: high value, not blocking. If there's a specific auth bug users are hitting right now, that changes things and I'd move it to Must. Is there one I'm not seeing?
