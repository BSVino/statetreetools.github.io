---
title: Map Range Unclamped
---

# Map Range Unclamped

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Remaps **Value** from one range to another without clamping. If **Value** falls outside `[InRangeA, InRangeB]` the result is extrapolated beyond `[OutRangeA, OutRangeB]`. Use this when you want proportional scaling across ranges and are certain the input is well-bounded, or when extrapolation is intentional.

---

## Configuration

### Value
The input value to remap.

### InRangeA
The start of the input range. Defaults to `0`.

### InRangeB
The end of the input range. Defaults to `1`.

### OutRangeA
The start of the output range. Defaults to `0`.

### OutRangeB
The end of the output range. Defaults to `1`.

### Result
**Value** remapped from `[InRangeA, InRangeB]` to `[OutRangeA, OutRangeB]`, without clamping.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
