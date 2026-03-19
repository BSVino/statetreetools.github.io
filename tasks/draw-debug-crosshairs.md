---
title: Draw Debug Crosshairs
---

# Draw Debug Crosshairs

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a set of three crosshair lines oriented along a rotator at a world-space location. When **While Task Is Active** is enabled the crosshairs are redrawn every tick. When disabled they are drawn once on enter and the task immediately succeeds.

---

## Configuration

### Axis Loc
The world-space position of the crosshair center.

### Axis Rot
The orientation of the crosshairs.

### Scale
Uniform scale applied to the crosshair line lengths. Default is `1.0`.

### Color
The color of the crosshair lines. Default is white.

### While Task Is Active
When enabled the crosshairs are redrawn every tick and the task stays running until the state exits. When disabled they are drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the crosshairs persist until `FlushPersistentDebugLines` is called.

### Life Time
How long the crosshairs remain visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
