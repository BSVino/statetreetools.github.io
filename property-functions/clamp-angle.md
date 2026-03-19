---
title: Clamp Angle
---

# Clamp Angle

**Plugin:** StateTreeToolsCore
**Category:** Math \| Float

Constrains an angle in degrees to lie within a specified angular range, wrapping the angle first so the comparison is performed in a consistent space. Use this to restrict a turret or camera yaw to an allowed arc, or to keep a rotation offset within a comfortable range.

---

## Configuration

### AngleDegrees
The angle in degrees to clamp.

### MinAngleDegrees
The lower angular bound in degrees. Defaults to `0`.

### MaxAngleDegrees
The upper angular bound in degrees. Defaults to `360`.

### Result
**AngleDegrees** constrained to `[MinAngleDegrees, MaxAngleDegrees]`.

---

[← Back to Math \| Float](/property-functions/math-float) · [← Back to home](/)
