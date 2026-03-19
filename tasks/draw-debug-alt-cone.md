---
title: Draw Debug Alt Cone
---

# Draw Debug Alt Cone

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug cone defined by an origin, a rotator, a length, and angular widths. This is an alternative to [Draw Debug Cone](/tasks/draw-debug-cone) that uses a `FRotator` instead of a direction vector to orient the cone. When **While Task Is Active** is enabled the cone is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Origin
The world-space apex of the cone.

### Rotation
The orientation of the cone as a rotator. The forward direction of this rotation defines where the cone points.

### Length
The length of the cone from apex to base in world units. Default is `100`.

### Angle Width
The half-angle of the cone in the horizontal plane, in radians. Default is `0.5`.

### Angle Height
The half-angle of the cone in the vertical plane, in radians. Default is `0.5`.

### Draw Color
The color of the cone. Default is red.

### While Task Is Active
When enabled the cone is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the cone persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the cone remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
