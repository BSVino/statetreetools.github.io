---
title: Set Component Property
---

# Set Component Property

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Properties
**Availability:** StateTree Tools **2.0+**

Sets any exposed property on a bound component when the state is entered, exited, or both. The property and its value are configured directly in the StateTree editor.

> **UE 5.7 and earlier known issue:** Unreal has a component-binding UI bug that can cause the details panel to continuously refresh when you bind a component property directly into this node's **Component** input. If that happens, create a StateTree **parameter** of the component type, set up the component reference there, and bind that parameter into **Component** instead.

---

## Configuration

### Component
Bind this to the component whose property you want to set.

### Component Class
Set this to the Blueprint class of the component. This is used in the editor to populate the property dropdown and does not affect runtime behaviour.

### Property Name
Select the property to set from the dropdown. The list is populated from the Component Class.

### Property
Once a property is selected, a matching value field appears here automatically. Fill it in directly or bind it from elsewhere in the StateTree.

StateTree Tools **2.0+** adds array support here, so array properties can be set directly through the node.

---

## When to Set

By default the property is set when the state is **entered**. You can change this to set on **exit** instead, or on **both** enter and exit. See [Enter / Exit Firing](/enter-exit-firing) for the shared timing behaviour used by these task nodes.

---

## Error Handling

If the component is invalid, the named property does not exist, or there is a type mismatch at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Utilities | Properties](/tasks/properties) · [← Back to home](/)
