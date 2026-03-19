---
title: Draw Debug Circle Arc
---

# Draw Debug Circle Arc

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a partial arc of a circle at a world-space center, defined by a direction vector and an angular width. When **While Task Is Active** is enabled the arc is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Center
The world-space center of the circle the arc belongs to.

### Radius
The radius of the circle in world units. Default is `100`.

### Direction
The center direction of the arc, expressed as a unit vector.

### Angle Width
The half-angle of the arc in radians. The arc spans `[-AngleWidth, +AngleWidth]` around Direction. Default is `1.0`.

### Segments
The number of line segments used to approximate the arc. Default is `12`.

### Color
The color of the arc. Default is red.

### While Task Is Active
When enabled the arc is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the arc persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the arc remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
