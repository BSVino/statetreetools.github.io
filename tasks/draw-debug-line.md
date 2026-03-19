---
title: Draw Debug Line
---

# Draw Debug Line

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug line between two world-space points. When **While Task Is Active** is enabled the line is redrawn every tick for as long as the state is active. When disabled the line is drawn once on enter using the persistence and lifetime settings, then the task immediately succeeds.

---

## Configuration

### Line Start
The world-space start position of the line.

### Line End
The world-space end position of the line.

### Color
The color of the line. Default is red.

### While Task Is Active
When enabled the line is redrawn every tick. The task stays running until the state exits. When disabled the line is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the line persists until `FlushPersistentDebugLines` is called. Mutually exclusive with **Life Time**.

### Life Time
How long the line remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Higher values draw on top of lower-priority geometry. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
