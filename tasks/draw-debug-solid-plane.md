---
title: Draw Debug Solid Plane
---

# Draw Debug Solid Plane

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a solid-filled debug plane centered at a location, using a uniform size for both axes. When **While Task Is Active** is enabled the plane is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a version with separate X/Y extents see [Draw Debug Solid Plane (Extents)](/tasks/draw-debug-solid-plane-extents).

---

## Configuration

### Plane
The `FPlane` (normal + offset) that defines the plane's orientation.

### Location
The world-space center point of the plane visualization.

### Size
The half-size of the plane in world units along both axes. Default is `100`.

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
