---
title: Get Root Component
---

# Get Root Component

**Plugin:** StateTreeToolsCore
**Category:** Components

Returns the root USceneComponent of an actor. Use this to bind a component reference anywhere the StateTree editor expects a scene component — for example as the attach target for a Niagara system or as an input to another property function.

> **UE 5.7 and earlier known issue:** Unreal has a component-binding UI bug that can cause the details panel to continuously refresh when you bind the output of this property function directly into another node's component input. If that happens, create a StateTree **parameter** of the component type, bind **Get Root Component** into that parameter, and then bind the parameter into the target node instead.

---

## Configuration

### Input
Bind this to the actor whose root component you want to retrieve.

### Output
The root scene component of the bound actor. This value is recomputed each time the binding is evaluated.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[← Back to Components](/property-functions/components) · [← Back to home](/)