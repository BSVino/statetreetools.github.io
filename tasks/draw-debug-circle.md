---
title: Draw Debug Circle
---

# Draw Debug Circle

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug circle in 3D space at a center point, oriented by explicit Y and Z axis vectors. When **While Task Is Active** is enabled the circle is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a matrix-oriented circle see [Draw Debug Circle (Matrix)](/tasks/draw-debug-circle-matrix).

---

## Configuration

### Center
The world-space center of the circle.

### Radius
The radius of the circle in world units. Default is `100`.

### Segments
The number of line segments used to approximate the circle. More segments produce a smoother circle. Default is `12`.

### Color
The color of the circle. Default is red.

### Y Axis
The local Y axis vector used to orient the circle plane. Default is `(0, 1, 0)`.

### Z Axis
The local Z axis vector used to orient the circle plane. Default is `(0, 0, 1)`.

### Draw Axis
When enabled the Y and Z axis vectors are drawn as lines through the center. Default is `true`.

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
