---
title: Draw Debug Solid Box (Rotated)
---

# Draw Debug Solid Box (Rotated)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a solid-filled oriented debug box defined by a center point, half-extents, and a quaternion rotation. When **While Task Is Active** is enabled the box is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For an axis-aligned variant see [Draw Debug Solid Box](/tasks/draw-debug-solid-box).

---

## Configuration

### Center
The world-space center of the box.

### Extent
The half-extents of the box along each local axis. Default is `(50, 50, 50)`.

### Rotation
The orientation of the box as a quaternion. Default is identity (no rotation).

### Color
The fill color of the box. Default is red.

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
