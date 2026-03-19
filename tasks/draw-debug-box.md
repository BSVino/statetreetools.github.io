---
title: Draw Debug Box
---

# Draw Debug Box

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws an axis-aligned debug box centered at a world-space position. When **While Task Is Active** is enabled the box is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a rotated box see [Draw Debug Box (Rotated)](/tasks/draw-debug-box-rotated).

---

## Configuration

### Center
The world-space center of the box.

### Extent
The half-extents of the box along each axis. Default is `(50, 50, 50)`.

### Color
The color of the box outline. Default is red.

### While Task Is Active
When enabled the box is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the box persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the box remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
