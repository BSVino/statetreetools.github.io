---
title: Call Component Event
---

# Call Component Event

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Events
**Availability:** StateTree Tools **2.0+**

Calls a Blueprint event or function on a bound component when the state is entered, exited, or both. Parameters are configured directly in the StateTree editor and can be bound to other values in the tree.

> **UE 5.7 and earlier known issue:** Unreal has a component-binding UI bug that can cause the details panel to continuously refresh when you bind a component property directly into this node's **Component** input. If that happens, create a StateTree **parameter** of the component type, set up the component reference there, and bind that parameter into **Component** instead.

---

## Configuration

### Component
Bind this to the component whose function you want to call.

### Component Class
Set this to the Blueprint class of the component. This is used in the editor to populate the event dropdown and does not affect runtime behaviour.

### Event Name
Select the function to call from the dropdown. The list is populated from the Component Class. Only Blueprint-callable functions and Blueprint-authored events are shown.

### Parameters
Once an event is selected, its parameters appear here automatically. Fill them in directly or bind them to values elsewhere in the StateTree.

---

## When to Fire

By default the event is called when the state is **entered**. You can change this to fire on **exit** instead, or on **both** enter and exit. See [Enter / Exit Firing](/enter-exit-firing) for a full explanation of how this works across all tasks.

---

## Error Handling

If the component is invalid or the named function does not exist at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Utilities | Events](/tasks/events) · [← Back to home](/)