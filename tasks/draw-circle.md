---
title: Draw Circle
---

# Draw Circle

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug circle in 3D space defined by a base position and explicit X and Y axis vectors, giving full control over the circle's plane orientation. When **While Task Is Active** is enabled the circle is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a center+YZ-axis version see [Draw Debug Circle](/tasks/draw-debug-circle).

---

## Configuration

### Base
The world-space center of the circle.

### X
The local X axis vector used to orient the circle plane.

### Y
The local Y axis vector used to orient the circle plane.

### Color
The color of the circle. Default is red.

### Radius
The radius of the circle in world units. Default is `100`.

### Num Sides
The number of line segments used to approximate the circle. Default is `12`.

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
