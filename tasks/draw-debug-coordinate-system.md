---
title: Draw Debug Coordinate System
---

# Draw Debug Coordinate System

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws three colored axis lines (X red, Y green, Z blue) representing a coordinate system at a world-space location and orientation. When **While Task Is Active** is enabled the axes are redrawn every tick. When disabled they are drawn once on enter and the task immediately succeeds.

---

## Configuration

### Axis Loc
The world-space origin of the coordinate system.

### Axis Rot
The orientation of the coordinate system as a rotator.

### Scale
Uniform scale applied to the axis line lengths. Default is `1.0`.

### While Task Is Active
When enabled the axes are redrawn every tick and the task stays running until the state exits. When disabled they are drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the axes persist until `FlushPersistentDebugLines` is called.

### Life Time
How long the axes remain visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
