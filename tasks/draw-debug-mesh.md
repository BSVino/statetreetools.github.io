---
title: Draw Debug Mesh
---

# Draw Debug Mesh

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a solid debug mesh defined by an array of vertices and a triangle index array. When **While Task Is Active** is enabled the mesh is redrawn every tick. When disabled it is drawn once on enter and the task immediately succeeds.

---

## Configuration

### Verts
An array of `FVector` world-space vertex positions that make up the mesh.

### Indices
An array of `int32` triangle indices into the **Verts** array. Each group of three indices forms one triangle.

### Color
The fill color of the mesh. Default is red.

### While Task Is Active
When enabled the mesh is redrawn every tick and the task stays running until the state exits. When disabled it is drawn once on enter.

### Persistent
When enabled (and **While Task Is Active** is off) the mesh persists until `FlushPersistentDebugLines` is called.

### Life Time
How long the mesh remains visible in seconds. A value of `-1` uses the engine default. Only active when **While Task Is Active** and **Persistent** are both off.

### Depth Priority
Rendering depth priority. Default is `0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
