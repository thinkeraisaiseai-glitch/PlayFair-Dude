# PlayFair Dude — Integrity Metrics (v0.1)

This document defines the integrity metrics used by PlayFair Dude.

Metrics describe **system behavior**, not player intent.

---

## Metric Design Rules

All metrics must:
- Be server-derived
- Be aggregate-only
- Be time-windowed
- Avoid player attribution
- Be explainable to non-experts

---

## SIAR — Server Integrity Anomaly Rate

### Definition

SIAR measures the **rate at which the server detects and corrects
states that violate defined game rules**.

This includes:
- Impossible movement states
- Invalid physics transitions
- Rule-enforced rollbacks
- Server-side rejections

---

### Conceptual Formula

    SIAR = anomalyEvents / totalObservedEvents

Measured over a defined time window.

---

### What SIAR IS

- A stress indicator
- A tuning signal
- A systemic health metric

---

### What SIAR IS NOT

- Proof of cheating
- A player score
- A detection verdict
- A punishment trigger

---

### Privacy Properties

- No player identifiers required
- No per-player scoring
- No client-side inspection

---

### Interpretation Guidance

High SIAR may indicate:
- Poor rule tuning
- Latency effects
- Game design edge cases
- Exploit pressure

It does NOT automatically imply malicious behavior.
