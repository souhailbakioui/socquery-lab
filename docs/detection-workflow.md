# 🛡️ Detection Engineering Workflow

## Overview

Detection engineering transforms knowledge about suspicious behavior into repeatable detection logic.

SocQuery Lab introduces this workflow through a simplified educational lifecycle.

---

# Detection Lifecycle

```text
Security Telemetry
        ↓
Threat Hypothesis
        ↓
Query Development
        ↓
Detection Rule
        ↓
Threshold Evaluation
        ↓
Alert Generation
        ↓
SOC Triage
        ↓
Investigation
```

---

# 1. Identify Suspicious Behavior

The analyst begins with a security hypothesis.

Examples include:

* Repeated failed authentication
* Password spraying
* Suspicious PowerShell activity
* DNS tunneling
* Unauthorized account creation

---

# 2. Analyze Telemetry

Relevant events are searched and analyzed.

The analyst identifies patterns such as:

* High event frequency
* Unusual users
* Suspicious source IP addresses
* Abnormal process activity

---

# 3. Develop Detection Logic

The investigation query is transformed into reusable detection logic.

Example concept:

```text
Failed Authentication Events
        ↓
Count Events Per User
        ↓
Identify Threshold Breach
        ↓
Generate Alert
```

---

# 4. Configure Detection Metadata

A detection can include:

* Name
* Description
* Severity
* Threshold
* MITRE ATT&CK mapping
* Status

---

# 5. Generate Alerts

When configured conditions are met, the detection can generate an alert.

---

# 6. SOC Triage

The analyst evaluates the alert.

Possible outcomes include:

* New
* Investigating
* False Positive
* Resolved

---

# Educational Goal

The objective is to help learners understand the relationship between:

```text
Telemetry
    ↓
Query
    ↓
Detection
    ↓
Alert
    ↓
Investigation
```
