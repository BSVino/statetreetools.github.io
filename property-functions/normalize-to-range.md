---
title: Normalize To Range
---

# Normalize To Range

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Returns the position of **Value** within `[RangeMin, RangeMax]` as a normalized fraction in `[0, 1]`. This is equivalent to mapping to an output range of `[0, 1]` and is useful for converting an absolute value into a proportion — for example turning a remaining health value into a 0-to-1 bar fill amount.

---

## Configuration

### Value
The value to normalize.

### RangeMin
The lower bound of the input range. Defaults to `0`.

### RangeMax
The upper bound of the input range. Defaults to `1`.

### Result
`(Value - RangeMin) / (RangeMax - RangeMin)`, representing **Value**'s position within the range.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
