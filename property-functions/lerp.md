---
title: Lerp
---

# Lerp

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Linearly interpolates between **Left** and **Right** by the factor **Alpha**. At `Alpha = 0` the result equals **Left**; at `Alpha = 1` the result equals **Right**. Values of Alpha outside `[0, 1]` extrapolate beyond the endpoints. Use this to blend between two float parameters — for example fading a volume or blending between two speeds based on a normalized input.

---

## Configuration

### Left
The value returned when **Alpha** is `0`.

### Right
The value returned when **Alpha** is `1`. Defaults to `1`.

### Alpha
The interpolation factor. Typically in `[0, 1]`.

### Result
`Left + (Right - Left) * Alpha`.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
