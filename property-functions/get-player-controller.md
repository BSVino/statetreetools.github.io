---
title: Get Player Controller
---

# Get Player Controller

**Plugin:** StateTreeToolsCore
**Category:** Game
**Availability:** StateTree Tools **2.0+**

Returns the player controller for the given player index. This mirrors Unreal's Blueprint **Get Player Controller** node.

---

## Configuration

### Player Index
The index of the local player whose controller you want. Default: `0` (the first local player).

### Output
The `APlayerController` for the given index. If no player controller exists for that index, the output is None.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[← Back to Game](/property-functions/game) · [← Back to home](/)
