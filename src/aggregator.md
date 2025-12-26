# Aggregator Module — Design Specification

The Aggregator converts raw anomaly signals into
**time-windowed aggregate metrics**.

---

## Responsibilities

- Count anomaly events
- Maintain rolling windows
- Normalize values for evaluation

---

## Privacy Rules

- No per-player storage
- No identity persistence
- No raw event export

---

## Failure Behavior

If aggregation fails:
- Data is dropped
- No retries with identity data
- No alerts are generated
