---
title: Draw Debug Solid Box (Bounds)
---

# Draw Debug Solid Box (Bounds)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a solid-filled debug box defined by an `FBox` (min/max bounds) and a world-space `FTransform`. When **While Task Is Active** is enabled the box is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For an extent-based solid box see [Draw Debug Solid Box](/tasks/draw-debug-solid-box).

---

## Configuration

### Box
The `FBox` (axis-aligned min/max bounds) defining the shape of the box before the transform is applied.

### Color
The fill color of the box. Default is red.

### Transform
The world-space transform (position, rotation, scale) applied to the box.

### While Task Is Active
When enabled the box is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent
When enabled (and **While Task Is Active** is off) the box persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the box remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
