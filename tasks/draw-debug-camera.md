---
title: Draw Debug Camera
---

# Draw Debug Camera

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a camera frustum wireframe at a world-space location and orientation, useful for visualizing a camera's field of view during development. When **While Task Is Active** is enabled the camera shape is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Location
The world-space position of the camera.

### Rotation
The orientation of the camera.

### FOV Deg
The horizontal field of view in degrees used to shape the frustum. Default is `90`.

### Scale
Uniform scale applied to the camera frustum visualization. Default is `1.0`.

### Color
The color of the camera wireframe. Default is white.

### While Task Is Active
When enabled the camera shape is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the camera shape persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the camera shape remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
