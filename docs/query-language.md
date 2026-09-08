# 🔍 SocQuery Lab Query Language

## Overview

SocQuery Lab provides an original query engine designed for cybersecurity education and SOC investigation training.

The syntax supports an educational subset of SPL-compatible concepts.

Queries are processed as pipelines.

Example:

```text
search EventCode=4625
| stats count by user
| sort -count
```

---

# Query Pipeline

A query can transform events through multiple stages.

```text
Security Events
      ↓
search
      ↓
filter
      ↓
transform
      ↓
aggregate
      ↓
results
```

---

# Supported Commands

## `search`

Searches and filters security events.

Supports concepts such as:

* Boolean logic
* AND
* OR
* NOT
* Wildcards
* Exact matching
* Quoted values

Example:

```text
search EventCode=4625 AND user=administrator
```

---

## `stats`

Performs aggregations.

Supported operations include:

* `count`
* `dc()`
* `distinct_count()`
* `sum()`
* `avg()`
* `min()`
* `max()`

Example:

```text
search EventCode=4625
| stats count by user
```

---

## `where`

Filters events using expressions.

Example:

```text
search EventCode=4625
| stats count by user
| where count >= 5
```

---

## `table`

Selects fields for display.

Example:

```text
search EventCode=4624
| table timestamp user source_ip
```

---

## `sort`

Orders results.

Example:

```text
search *
| stats count by user
| sort -count
```

---

## `head`

Limits results from the beginning.

Example:

```text
search *
| head 10
```

---

## `tail`

Limits results from the end.

Example:

```text
search *
| tail 10
```

---

## `dedup`

Removes duplicate events.

---

## `eval`

Supports transformations and expressions.

Example:

```text
search *
| eval severity=if(count > 10, "high", "low")
```

---

## `rename`

Renames fields.

Example:

```text
search *
| rename source_ip as attacker_ip
```

---

## `rex`

Extracts data using regular expressions and named capture groups.

---

## `timechart`

Performs time-based aggregation.

---

## `bin`

Groups timestamps into time buckets.

---

## `eventstats`

Calculates aggregate values while preserving events.

---

## `streamstats`

Supports calculations across event streams.

---

# Educational Purpose

The SocQuery Lab query engine is independently implemented for educational use.

It is not an implementation of Splunk software and is not affiliated with Splunk.

The supported syntax represents an educational subset of SPL-compatible concepts.
