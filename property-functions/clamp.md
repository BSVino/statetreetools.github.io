---
title: Clamp
---

# Clamp

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Constrains **Value** to lie within the range `[Min, Max]`. If **Value** is below **Min** it is raised to **Min**; if it is above **Max** it is lowered to **Max**; otherwise it is returned unchanged. Use this to enforce safe limits on parameters such as speed, volume, or animation blend weight.

---

## Configuration

### Value
The float value to clamp.

### Min
The lower bound. Defaults to `0`.

### Max
The upper bound. Defaults to `1`.

### Result
**Value** constrained to `[Min, Max]`.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
