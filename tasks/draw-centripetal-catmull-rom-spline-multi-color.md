---
title: Draw Centripetal Catmull-Rom Spline (Multi Color)
---

# Draw Centripetal Catmull-Rom Spline (Multi Color)

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a smooth centripetal Catmull-Rom spline through an array of world-space control points, with a separate color specified per segment. When **While Task Is Active** is enabled the spline is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds. For a single-color variant see [Draw Centripetal Catmull-Rom Spline](/tasks/draw-centripetal-catmull-rom-spline).

---

## Configuration

### Points
An array of world-space `FVector` control points that the spline passes through. At least two points are required.

### Colors
An array of `FLinearColor` values, one per segment (interval between consecutive points). If the Colors array is shorter than the number of segments the last color is reused for remaining segments.

### Alpha
The centripetal parameterization value. `0.5` is the standard centripetal form. `0.0` is uniform and `1.0` is chordal. Default is `0.5`.

### Num Samples Per Segment
The number of line segments drawn per interval between consecutive control points. Higher values produce a smoother curve. Default is `8`.

### While Task Is Active
When enabled the spline is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent Lines
When enabled (and **While Task Is Active** is off) the spline persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the spline remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent Lines** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

### Thickness
Line thickness in world units. Default is `0` (hairline).

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
