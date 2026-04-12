---
title: Get Component By Class
---

# Get Component By Class

**Plugin:** StateTreeToolsCore
**Category:** Components

Returns the first component on an actor that matches the specified component class. This mirrors Unreal's Blueprint **Get Component By Class** node and is useful when you want to retrieve a component reference without hard-coding a component name.

> **UE 5.7 and earlier known issue:** Unreal has a component-binding UI bug that can cause the details panel to continuously refresh when you bind the output of this property function directly into another node's component input. If that happens, create a StateTree **parameter** of the component type, bind **Get Component By Class** into that parameter, and then bind the parameter into the target node instead.

---

## Configuration

### Input
Bind this to the actor whose components you want to search.

### Component Class
Set this to the component class to search for. The first component on the actor that matches this class is returned.

### Output
The first component found that matches **Component Class**. If the actor is invalid or no matching component exists, the output is None.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[← Back to Components](/property-functions/components) · [← Back to home](/)