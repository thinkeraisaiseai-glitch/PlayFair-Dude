# PlayFair Dude — Public API (v0.1)

This document defines the **stable public interface** exposed to developers.
No breaking changes will be made within v0.1.

---

## Module Name

PlayFairDude

Installed as a **Server-side ModuleScript**.

---

## Initialization

### PlayFairDude.init(configTable)

Initializes the system.

- Must be called once
- Server-side only
- Fails silently if misconfigured (no crashes)

Returns:
- boolean (success)

---

## Runtime Controls

### PlayFairDude.start()

Begins integrity observation.

---

### PlayFairDude.stop()

Stops all observers and exporters.

---

## Reporting

### PlayFairDude.getSnapshot()

Returns an **anonymous summary snapshot** of current metrics.

Returns:
```lua
{
  timestamp = number,
  metrics = {
    SIAR = number,
  },
  alerts = number
}
