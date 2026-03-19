---
title: Draw Debug 2D Donut
---

# Draw Debug 2D Donut

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a 2D donut (annulus) shape — two concentric circles connected by radial lines — oriented by a transformation matrix. When **While Task Is Active** is enabled the donut is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Transform Matrix
The `FMatrix` that positions and orients the donut in world space.

### Inner Radius
The radius of the inner circle in world units. Default is `50`.

### Outer Radius
The radius of the outer circle in world units. Default is `100`.

### Segments
The number of line segments used to approximate each circle. Default is `12`.

### Color
The color of the donut. Default is red.

### While Task Is Active
When enabled the donut is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the donut persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the donut remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
