---
title: Draw Debug Directional Arrow
---

# Draw Debug Directional Arrow

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug line with an arrowhead pointing from one world-space point to another. When **While Task Is Active** is enabled the arrow is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Line Start
The world-space start position of the arrow shaft.

### Line End
The world-space end (tip) position of the arrow.

### Arrow Size
The size of the arrowhead in world units. Default is `50`.

### Color
The color of the arrow. Default is red.

### While Task Is Active
When enabled the arrow is redrawn every tick and the task stays running until the state exits. When disabled the arrow is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the arrow persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the arrow remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
