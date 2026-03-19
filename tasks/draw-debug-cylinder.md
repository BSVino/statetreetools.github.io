---
title: Draw Debug Cylinder
---

# Draw Debug Cylinder

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug cylinder between two world-space points. When **While Task Is Active** is enabled the cylinder is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Start
The world-space position of the bottom center of the cylinder.

### End
The world-space position of the top center of the cylinder. Default is `(0, 0, 100)` offset from the origin.

### Radius
The radius of the cylinder in world units. Default is `50`.

### Segments
The number of line segments used to approximate the circular cross-section. Default is `12`.

### Color
The color of the cylinder. Default is red.

### While Task Is Active
When enabled the cylinder is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the cylinder persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the cylinder remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
