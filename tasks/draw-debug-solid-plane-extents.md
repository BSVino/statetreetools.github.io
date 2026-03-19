---
title: Draw Debug Solid Plane (Extents)
---

# Draw Debug Solid Plane (Extents)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a solid-filled debug plane centered at a location, using separate X and Y extents to control its dimensions. When **While Task Is Active** is enabled the plane is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a version with a single uniform size see [Draw Debug Solid Plane](/tasks/draw-debug-solid-plane).

---

## Configuration

### Plane
The `FPlane` (normal + offset) that defines the plane's orientation.

### Location
The world-space center point of the plane visualization.

### Extents
A `FVector2D` giving the half-extents of the plane along its local X and Y axes. Default is `(100, 100)`.

### Color
The fill color of the plane. Default is red.

### While Task Is Active
When enabled the plane is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent
When enabled (and **While Task Is Active** is off) the plane persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the plane remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
