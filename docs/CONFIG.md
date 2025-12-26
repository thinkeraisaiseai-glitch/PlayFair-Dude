# PlayFair Dude — Configuration Specification (v0.1)

This document defines the **explicit configuration contract**
used to initialize PlayFair Dude.

No implicit defaults are assumed.
No configuration is inferred.
Everything must be intentional.

---

## Configuration Philosophy

- Explicit over implicit
- Privacy-first defaults
- Safe failure on misconfiguration
- No hidden behavior

If a configuration is invalid or unsafe, PlayFair Dude does nothing.

---

## Root Configuration Object

Conceptual structure:

    {
      enabled = boolean,
      metrics = table,
      privacy = table,
      alerts = table,
      export = table
    }

---

## enabled

Controls whether PlayFair Dude is active.

Rules:
- Must be explicitly set to true
- If false or missing, the system does not start

---

## metrics

Defines which integrity metrics are enabled.

Example (conceptual):

    metrics = {
      SIAR = {
        enabled = true,
        threshold = number,
        windowSeconds = number
      }
    }

Rules:
- Metrics must be explicitly enabled
- Thresholds must be finite numbers
- Window size must be time-based (seconds)
- Invalid metrics are ignored silently

---

## privacy

Controls identity handling and data retention.

Conceptual structure:

    privacy = {
      allowTemporaryIdentity = false,
      retentionSeconds = 0
    }

Rules:
- Identity handling is disabled by default
- Retention defaults to zero
- Identity data is never persisted
- Identity is never exported automatically

---

## alerts

Controls alert generation behavior.

Conceptual structure:

    alerts = {
      enabled = true,
      escalation = false
    }

Rules:
- Alerts represent system stress, not violations
- Escalation is disabled by default
- Alerts never trigger enforcement actions

---

## export

Controls how aggregated data is exposed.

Conceptual structure:

    export = {
      mode = "log",
      endpoint = nil
    }

Modes:
- log   → server logs only
- json  → structured local output
- http  → developer-owned endpoint (opt-in)

Rules:
- No external export by default
- No raw event streaming
- Exporters receive summaries only

---

## Invalid Configuration Behavior

If configuration:
- Is missing required fields
- Enables unsafe combinations
- Violates privacy constraints

Then:
- PlayFair Dude fails silently
- No observers start
- No data is collected
