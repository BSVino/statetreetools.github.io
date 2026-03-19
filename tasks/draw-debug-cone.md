---
title: Draw Debug Cone
---

# Draw Debug Cone

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug cone defined by an origin, a direction vector, a length, and separate angular widths for horizontal and vertical spread. Angles are specified in radians. When **While Task Is Active** is enabled the cone is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a cone defined by origin and rotation see [Draw Debug Alt Cone](/tasks/draw-debug-alt-cone).

---

## Configuration

### Origin
The world-space apex of the cone.

### Direction
The direction the cone points, expressed as a unit vector.

### Length
The length of the cone from apex to base in world units. Default is `100`.

### Angle Width
The half-angle of the cone in the horizontal (X) plane, in radians. Default is `0.5`.

### Angle Height
The half-angle of the cone in the vertical (Y) plane, in radians. Default is `0.5`.

### Num Sides
The number of sides used to approximate the circular base. Default is `12`.

### Color
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
