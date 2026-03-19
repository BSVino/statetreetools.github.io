---
title: Draw Debug Float History (Transform)
---

# Draw Debug Float History (Transform)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug graph of a `FDebugFloatHistory` positioned and oriented by a full `FTransform`. The graph shows the recorded float values over time as a 2D chart in world space. When **While Task Is Active** is enabled the graph is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a location-only version see [Draw Debug Float History](/tasks/draw-debug-float-history).

---

## Configuration

### Float History
The `FDebugFloatHistory` struct containing the recorded float values to visualize.

### Draw Transform
The `FTransform` that positions and orients the graph in world space.

### Draw Size
The width and height of the graph in world units. Default is `(100, 50)`.

### Draw Color
The color of the graph lines. Default is red.

### While Task Is Active
When enabled the graph is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent
When enabled (and **While Task Is Active** is off) the graph persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the graph remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
