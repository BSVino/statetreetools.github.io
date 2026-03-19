---
title: Draw Debug Capsule
---

# Draw Debug Capsule

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug capsule at a world-space center with a quaternion rotation. When **While Task Is Active** is enabled the capsule is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Center
The world-space center of the capsule.

### Half Height
The half-height of the capsule (from center to the tip of a hemisphere), in world units. Default is `100`.

### Radius
The radius of the capsule in world units. Default is `50`.

### Rotation
The orientation of the capsule as a quaternion. Default is identity (capsule aligned with Z axis).

### Color
The color of the capsule. Default is red.

### While Task Is Active
When enabled the capsule is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the capsule persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the capsule remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
