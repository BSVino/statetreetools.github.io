---
title: Draw Debug Float History
---

# Draw Debug Float History

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug graph of a `FDebugFloatHistory` at a fixed world-space location. The graph shows the recorded float values over time as a 2D chart in world space. When **While Task Is Active** is enabled the graph is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a version positioned by a full `FTransform` see [Draw Debug Float History (Transform)](/tasks/draw-debug-float-history-transform).

---

## Configuration

### Float History
The `FDebugFloatHistory` struct containing the recorded float values to visualize.

### Draw Location
The world-space position of the bottom-left corner of the graph.

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
