---
title: Debug
---

# Debug

Tasks that wrap Unreal's built-in debug drawing functions. Most tasks support a **While Task Is Active** mode that redraws every tick, or a one-shot mode that draws once on enter and immediately succeeds.

| Task | Description |
|------|-------------|
| [Flush Persistent Debug Lines](/tasks/flush-persistent-debug-lines) | Removes all persistent debug geometry from the world. |
| [Flush Debug Strings](/tasks/flush-debug-strings) | Removes all debug strings drawn with DrawDebugString. |
| [Draw Debug Line](/tasks/draw-debug-line) | Draws a line between two world-space points. |
| [Draw Debug Point](/tasks/draw-debug-point) | Draws a point at a world-space position. |
| [Draw Debug Directional Arrow](/tasks/draw-debug-directional-arrow) | Draws a line with an arrowhead between two world-space points. |
| [Draw Debug Box](/tasks/draw-debug-box) | Draws an axis-aligned wireframe box. |
| [Draw Debug Box (Rotated)](/tasks/draw-debug-box-rotated) | Draws an oriented wireframe box with a quaternion rotation. |
| [Draw Debug Coordinate System](/tasks/draw-debug-coordinate-system) | Draws X/Y/Z axis lines at a world location and rotation. |
| [Draw Debug Crosshairs](/tasks/draw-debug-crosshairs) | Draws crosshair lines at a world location and rotation. |
| [Draw Debug Circle](/tasks/draw-debug-circle) | Draws a circle oriented by Y and Z axis vectors. |
| [Draw Debug Circle (Matrix)](/tasks/draw-debug-circle-matrix) | Draws a circle oriented by a transformation matrix. |
| [Draw Debug Circle Arc](/tasks/draw-debug-circle-arc) | Draws a partial arc of a circle. |
| [Draw Debug 2D Donut](/tasks/draw-debug-2d-donut) | Draws a 2D donut (annulus) oriented by a transformation matrix. |
| [Draw Debug Sphere](/tasks/draw-debug-sphere) | Draws a wireframe sphere. |
| [Draw Debug Cylinder](/tasks/draw-debug-cylinder) | Draws a wireframe cylinder between two points. |
| [Draw Debug Cone](/tasks/draw-debug-cone) | Draws a wireframe cone defined by an origin, direction vector, length, and angular widths. |
| [Draw Debug Alt Cone](/tasks/draw-debug-alt-cone) | Draws a wireframe cone defined by an origin, rotator, length, and angular widths. |
| [Draw Debug Capsule](/tasks/draw-debug-capsule) | Draws a wireframe capsule. |
| [Draw Debug Frustum](/tasks/draw-debug-frustum) | Draws a wireframe camera frustum from a transformation matrix. |
| [Draw Debug Camera](/tasks/draw-debug-camera) | Draws a camera frustum wireframe at a world location and orientation. |
| [Draw Debug String](/tasks/draw-debug-string) | Draws a text string at a world-space location. |
| [Draw Debug Solid Box (Bounds)](/tasks/draw-debug-solid-box-bounds) | Draws a solid filled box defined by FBox bounds and a transform. |
| [Draw Debug Solid Box](/tasks/draw-debug-solid-box) | Draws a solid filled axis-aligned box defined by center and extents. |
| [Draw Debug Solid Box (Rotated)](/tasks/draw-debug-solid-box-rotated) | Draws a solid filled oriented box defined by center, extents, and quaternion rotation. |
| [Draw Debug Solid Plane](/tasks/draw-debug-solid-plane) | Draws a solid filled plane with a uniform size. |
| [Draw Debug Solid Plane (Extents)](/tasks/draw-debug-solid-plane-extents) | Draws a solid filled plane with separate X and Y extents. |
| [Draw Debug Mesh](/tasks/draw-debug-mesh) | Draws a solid filled mesh from vertex and index arrays. |
| [Draw Debug Float History](/tasks/draw-debug-float-history) | Draws a float history graph at a world-space location. |
| [Draw Debug Float History (Transform)](/tasks/draw-debug-float-history-transform) | Draws a float history graph positioned by a full transform. |
| [Draw Circle](/tasks/draw-circle) | Draws a circle defined by a base position and explicit X and Y axis vectors. |
| [Draw Centripetal Catmull-Rom Spline](/tasks/draw-centripetal-catmull-rom-spline) | Draws a smooth Catmull-Rom spline through a list of control points with a single color. |
| [Draw Centripetal Catmull-Rom Spline (Multi Color)](/tasks/draw-centripetal-catmull-rom-spline-multi-color) | Draws a smooth Catmull-Rom spline with a separate color per segment. |

[← Back to home](/)
