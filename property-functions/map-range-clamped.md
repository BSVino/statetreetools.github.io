---
title: Map Range Clamped
---

# Map Range Clamped

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Remaps **Value** from one range to another, clamping the result so it never falls outside `[OutRangeA, OutRangeB]`. Use this when the input may exceed the expected range but you need the output to remain within bounds — for example mapping a raw sensor reading to a safe parameter range.

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
**Value** remapped from `[InRangeA, InRangeB]` to `[OutRangeA, OutRangeB]`, clamped to `[OutRangeA, OutRangeB]`.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
