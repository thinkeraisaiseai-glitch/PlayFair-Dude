# Anonymizer Module — Design Specification

The Anonymizer enforces all privacy guarantees.

---

## Responsibilities

- Strip identifiers
- Enforce retention limits
- Validate privacy configuration

---

## Absolute Rules

- Identity is opt-in only
- Identity is temporary only
- Identity is never exported by default
- Identity is never persisted

The Anonymizer has veto power over all data flows.
