---
title: Call Actor Event
---

# Call Actor Event

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Events

Calls any Blueprint event or function on an actor (or one of its components) when the state is entered, exited, or both. Parameters are configured directly in the StateTree editor and can be bound to other values in the tree.

---

## Configuration

### Actor
Bind this to the actor you want to call the function on. This is typically bound from the StateTree's context or from a parent state.

### Actor Class
Set this to the Blueprint class of the actor. This is used in the editor to populate the function dropdown. It does not affect runtime behaviour — it is only needed so the editor knows which functions to list.

### Component Name *(optional)*
If the function lives on a component rather than the actor itself, enter the component's name here. Leave it empty to call the function directly on the actor.

### Event Name
Select the function to call from the dropdown. The list is populated from the Actor Class (or the selected component's class). Only Blueprint-callable functions are shown.

### Parameters
Once an event is selected, its input parameters appear here automatically. Fill them in directly or bind them to values elsewhere in the StateTree.

---

## When to Fire

By default the function is called when the state is **entered**. You can change this to fire on **exit** instead, or on **both** enter and exit. See [Enter / Exit Firing](/enter-exit-firing) for a full explanation of how this works across all tasks.

---

## Error Handling

If the actor is invalid, the component is not found, or the named function does not exist at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Utilities \| Events](/tasks/events) · [← Back to home](/)
