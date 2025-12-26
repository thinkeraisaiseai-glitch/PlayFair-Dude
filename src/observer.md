# Observer Module — Design Specification

The Observer is responsible for **listening to server-side events**
that indicate integrity-relevant behavior.

---

## Responsibilities

- Observe server-only state transitions
- Emit normalized anomaly signals
- Remain passive and non-invasive

---

## Constraints

The Observer MUST:
- Run server-side only
- Avoid player inspection
- Avoid modifying gameplay state

The Observer MUST NOT:
- Read client memory
- Inspect packets
- Track players
- Enforce rules

---

## Output

The Observer emits:
- Timestamped anomaly events
- Metric identifiers
- No identity data by default

---

## Failure Handling

If an event source fails:
- The Observer disables itself
- No cascading failure occurs
