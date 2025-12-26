# Evaluator Module — Design Specification

The Evaluator applies **transparent thresholds**
to aggregated metrics.

---

## Responsibilities

- Compare metrics to thresholds
- Generate alerts
- Avoid false certainty

---

## Alert Rules

Alerts:
- Represent stress, not guilt
- Are non-punitive
- Are reversible
- May expire automatically

---

## Constraints

Evaluator MUST NOT:
- Trigger enforcement
- Modify gameplay
- Escalate identity by default
