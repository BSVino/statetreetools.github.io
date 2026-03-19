---
title: Draw Debug Circle (Matrix)
---

# Draw Debug Circle (Matrix)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug circle oriented by a full transformation matrix. When **While Task Is Active** is enabled the circle is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a simpler center+axis-vector version see [Draw Debug Circle](/tasks/draw-debug-circle).

---

## Configuration

### Transform Matrix
The `FMatrix` that positions and orients the circle in world space.

### Radius
The radius of the circle in world units. Default is `100`.

### Segments
The number of line segments used to approximate the circle. Default is `12`.

### Color
The color of the circle. Default is red.

### Draw Axis
When enabled the matrix axes are drawn as lines through the center. Default is `true`.

### While Task Is Active
When enabled the circle is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the circle persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the circle remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
