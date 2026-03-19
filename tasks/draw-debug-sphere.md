---
title: Draw Debug Sphere
---

# Draw Debug Sphere

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug sphere at a world-space center. When **While Task Is Active** is enabled the sphere is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Center
The world-space center of the sphere.

### Radius
The radius of the sphere in world units. Default is `100`.

### Segments
The number of line segments used to approximate the sphere's great circles. Default is `12`.

### Color
The color of the sphere. Default is red.

### While Task Is Active
When enabled the sphere is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the sphere persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the sphere remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
