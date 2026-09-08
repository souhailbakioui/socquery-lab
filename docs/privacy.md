# 🔐 Privacy Architecture

## Privacy-First Design

SocQuery Lab is designed around a local browser processing model.

Security telemetry can contain sensitive information, including:

* IP addresses
* Usernames
* Hostnames
* Authentication events
* Process activity
* DNS queries

For this reason, the platform architecture prioritizes local processing.

---

# Local Processing Model

```text
User Upload
     ↓
Browser
     ↓
Local Parsing
     ↓
Local Storage
     ↓
Local Query Processing
     ↓
Results
```

---

# Browser-Based Storage

SocQuery Lab uses browser IndexedDB for local persistence.

The local database is identified as:

```text
SocQueryLabDB
```

It can store application data such as:

* Security events
* Datasets
* Detection rules
* Alerts
* Query history

---

# User Data

The platform is designed so that uploaded datasets can remain within the user's browser environment during normal operation.

Users should still follow their organization's security and data handling policies before using any third-party or browser-based tool with real production telemetry.

---

# Privacy Principles

SocQuery Lab follows these architectural principles:

* Local-first processing
* Minimal external dependencies
* Browser-based execution
* User control over uploaded data
* No requirement for server-side SIEM infrastructure

---

# Important Note

SocQuery Lab is an educational platform.

Users should avoid uploading sensitive production data unless they have appropriate authorization and have verified that doing so complies with their organization's security, privacy, and data governance requirements.
