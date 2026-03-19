---
title: Call Actor Delegate
---

# Call Actor Delegate

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Events

Broadcasts a Blueprint event dispatcher (multicast delegate) on an actor or one of its components when the state is entered, exited, or both. Parameters are configured directly in the StateTree editor and can be bound to other values in the tree.

---

## Configuration

### Actor
Bind this to the actor whose event dispatcher you want to broadcast. This is typically bound from the StateTree's context or from a parent state.

### Actor Class
Set this to the Blueprint class of the actor. This is used in the editor to populate the delegate dropdown and does not affect runtime behaviour.

### Component Name *(optional)*
If the event dispatcher lives on a component rather than the actor itself, enter the component's name here. Leave it empty to broadcast directly on the actor.

### Delegate Name
Select the event dispatcher to broadcast from the dropdown. The list is populated from the Actor Class (or the selected component's class). Only Blueprint-assignable event dispatchers are shown.

### Parameters
Once a delegate is selected, its parameters appear here automatically. Fill them in directly or bind them to values elsewhere in the StateTree.

---

## When to Fire

By default the delegate is broadcast when the state is **entered**. You can change this to fire on **exit** instead, or on **both** enter and exit. See [Enter / Exit Firing](https://bsvino.github.io/statetreetools.github.io/enter-exit-firing) for a full explanation of how this works across all tasks.

---

## Error Handling

If the actor is invalid, the component is not found, or the named delegate does not exist at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Utilities | Events](https://bsvino.github.io/statetreetools.github.io/tasks/events) · [← Back to home](https://bsvino.github.io/statetreetools.github.io/)
