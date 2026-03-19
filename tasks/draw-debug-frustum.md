---
title: Draw Debug Frustum
---

# Draw Debug Frustum

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a wireframe debug frustum (view pyramid) defined by a frustum-to-world transformation matrix. When **While Task Is Active** is enabled the frustum is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Frustum To World
The `FMatrix` that transforms the canonical frustum into world space.

### Color
The color of the frustum. Default is red.

### While Task Is Active
When enabled the frustum is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the frustum persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the frustum remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
