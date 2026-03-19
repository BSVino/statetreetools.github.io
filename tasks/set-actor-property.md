---
title: Set Actor Property
---

# Set Actor Property

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Properties

Sets any exposed property on an actor or one of its components when the state is entered, exited, or both. The property and its value are configured directly in the StateTree editor — no custom task or Blueprint function needed.

---

## Configuration

### Actor
Bind this to the actor whose property you want to set. This is typically bound from the StateTree's context or from a parent state.

### Actor Class
Set this to the Blueprint class of the actor. This is used in the editor to populate the property dropdown and does not affect runtime behaviour.

### Component Name *(optional)*
If the property lives on a component rather than the actor itself, enter the component's name here. Leave it empty to target the actor directly.

### Property Name
Select the property to set from the dropdown. The list is populated from the Actor Class (or the selected component's class).

### Value
Once a property is selected, a value field appears matching the property's type. Fill it in directly or bind it to a value elsewhere in the StateTree.

---

## When to Fire

By default the property is set when the state is **entered**. You can change this to fire on **exit** instead, or on **both** enter and exit. See [Enter / Exit Firing](/enter-exit-firing) for a full explanation of how this works across all tasks.

A common pattern is to set a property to one value on enter and restore it to another on exit, using two Set Actor Property tasks in the same state with opposite timing settings.

---

## Error Handling

If the actor is invalid, the component is not found, the named property does not exist, or there is a type mismatch at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

The StateTree editor will warn you at compile time if neither enter nor exit firing is enabled.

[← Back to Utilities \| Properties](/tasks/properties) · [← Back to home](/)
