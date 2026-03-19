---
title: Draw Debug Point
---

# Draw Debug Point

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug point at a world-space position. When **While Task Is Active** is enabled the point is redrawn every tick for as long as the state is active. When disabled the point is drawn once on enter using the persistence and lifetime settings, then the task immediately succeeds.

---

## Configuration

### Position
The world-space position of the point.

### Size
The display size of the point in screen pixels. Default is `10`.

### Point Color
The color of the point. Default is red.

### While Task Is Active
When enabled the point is redrawn every tick and the task stays running until the state exits. When disabled the point is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the point persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the point remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
