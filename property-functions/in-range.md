---
title: In Range
---

# In Range

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Returns `true` if **Value** falls within the range `[Min, Max]`. The inclusivity of each endpoint is configurable independently, making this suitable for both closed and half-open interval checks — for example testing whether a health percentage is within an alert band or whether a distance is inside an engagement zone.

---

## Configuration

### Value
The float value to test.

### Min
The lower bound of the range.

### Max
The upper bound of the range. Defaults to `1`.

### bInclusiveMin
When `true`, a **Value** exactly equal to **Min** returns `true`. Defaults to `true`.

### bInclusiveMax
When `true`, a **Value** exactly equal to **Max** returns `true`. Defaults to `true`.

### Result
`true` if **Value** is within the specified range, otherwise `false`.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
