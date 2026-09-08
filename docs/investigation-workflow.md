# 🔎 SOC Investigation Workflow

## Overview

Security investigations require analysts to move beyond individual events.

SocQuery Lab provides workflows for exploring related activity and building investigation context.

---

# Investigation Lifecycle

```text
Alert
  ↓
Initial Review
  ↓
Event Analysis
  ↓
Pivoting
  ↓
Correlation
  ↓
Timeline Analysis
  ↓
Conclusion
```

---

# 1. Initial Alert Review

The analyst begins by reviewing:

* Alert severity
* Detection context
* Triggering events
* Relevant timestamps

---

# 2. Inspect Raw Events

Raw events provide additional context.

Examples of useful fields include:

* Timestamp
* User
* Source IP
* Destination
* Host
* Event type

---

# 3. Pivot

Analysts can investigate related activity.

Common pivots include:

### Source IP

```text
Source IP
    ↓
Authentication Activity
    ↓
Related Users
    ↓
Related Hosts
```

### User

```text
User
  ↓
Authentication Events
  ↓
Failed Attempts
  ↓
Successful Login
```

---

# 4. Correlate Events

Security events become more meaningful when analyzed together.

Example:

```text
Multiple Failed Logins
        ↓
Successful Authentication
        ↓
Potential Credential Compromise
```

---

# 5. Analyze the Timeline

Chronological analysis helps analysts understand the sequence of activity.

Example:

```text
09:00 Failed Login
09:02 Failed Login
09:03 Failed Login
09:05 Successful Login
09:07 Privileged Activity
```

---

# 6. Determine the Outcome

The investigation can result in:

* Benign activity
* False positive
* Suspicious activity
* Confirmed security incident

---

# Educational Goal

SocQuery Lab helps learners develop structured investigation thinking.

The objective is not simply to find suspicious events, but to understand:

> What happened, who was involved, when it happened, and what evidence supports the conclusion?
