# 🏗️ SocQuery Lab Architecture

## Overview

SocQuery Lab is designed as a browser-based cybersecurity training platform.

The architecture prioritizes:

* Privacy
* Local data processing
* Modular design
* Type safety
* Educational usability

The platform runs primarily inside the user's browser.

---

# Architectural Principles

## 🔐 Privacy First

Security telemetry and user-uploaded datasets are designed to be processed locally.

The platform avoids requiring users to send security logs to a remote processing server for normal operation.

---

## 🧩 Modular Architecture

The application is divided into independent functional domains.

Core domains include:

* Search and reporting
* Query processing
* Detection engineering
* Alert management
* Incident investigation
* Data ingestion
* Challenges
* MITRE ATT&CK navigation

This separation allows individual capabilities to evolve independently.

---

## 🔍 Schema-on-Read

Security telemetry can contain different structures depending on its source.

Examples include:

* Windows Event Logs
* Linux authentication logs
* DNS logs
* Firewall telemetry
* VPN events
* PowerShell activity

SocQuery Lab uses a flexible approach that allows fields to be interpreted during analysis.

---

# High-Level Architecture

```text
                    ┌─────────────────┐
                    │      User       │
                    └────────┬────────┘
                             │
                             ▼
                ┌────────────────────────┐
                │     SocQuery Lab       │
                │       Browser UI       │
                └────────────┬───────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
     Dashboard           Search Engine       Detections
          │                  │                  │
          ▼                  ▼                  ▼
      Analytics        Query Processing      Alerts
          │                  │                  │
          └──────────────────┼──────────────────┘
                             │
                             ▼
                       IndexedDB
                             │
                             ▼
                       SocQueryLabDB
```

---

# Application Layer

The application layer provides the user-facing SOC experience.

Major components include:

* Executive SOC Dashboard
* Search & Reporting Console
* Detection Engineering Studio
* Alert Queue
* Event Investigation
* Data Upload
* Dataset Management
* SOC Challenges
* MITRE ATT&CK Navigator

---

# Query Processing Layer

The query processing layer is responsible for transforming security events through analytical pipelines.

A typical flow is:

```text
Raw Events
    ↓
Search
    ↓
Filtering
    ↓
Transformation
    ↓
Aggregation
    ↓
Results
```

The engine supports an educational subset of SPL-compatible concepts.

The implementation is original and designed specifically for SocQuery Lab.

---

# Storage Layer

The platform uses browser IndexedDB for local persistence.

The storage layer supports concepts such as:

* Security events
* Dataset isolation
* Detection rules
* Alert queues
* Query history

This allows users to work with telemetry locally.

---

# Detection Layer

Detection rules are created from analytical query logic.

The detection workflow can include:

```text
Security Events
      ↓
Detection Query
      ↓
Threshold Evaluation
      ↓
Alert Creation
      ↓
SOC Triage
```

---

# Investigation Layer

The investigation layer enables analysts to move from an alert or event toward related security activity.

Common pivots include:

* Source IP
* Username
* Host
* Event timeline

This supports an analyst-oriented investigation workflow.

---

# Architecture Goals

SocQuery Lab is designed to demonstrate how modern browser technologies can support interactive cybersecurity education.

The architecture focuses on:

* Local-first processing
* Modular design
* Interactive learning
* Realistic telemetry
* Explainable investigations
* Privacy-aware data handling
