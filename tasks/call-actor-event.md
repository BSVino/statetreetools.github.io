---
title: Call Actor Event
---

# Call Actor Event

**Category:** Utilities | Events

Calls a Blueprint event or function on an actor (or one of its components) when the state is entered, exited, or both. Parameters are configured directly in the StateTree editor and can be bound to other values in the tree.

---

## When to Use

Use this task when you want your StateTree to trigger behaviour defined in Blueprint — for example, playing a custom reaction, triggering a cinematic, notifying a UI widget, or starting a gameplay sequence — without writing a dedicated task for each case.

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

By default the function is called when the state is **entered**. You can change this to fire on **exit** instead, or on **both** enter and exit.

When exit firing is enabled you can further control which exit conditions trigger the call:

| Option | Default | Description |
|--------|---------|-------------|
| On Exit — Stopped | Off | Fire when the state is interrupted or the StateTree is stopped |
| On Exit — Succeeded | On | Fire when the state exits because it succeeded |
| On Exit — Failed | Off | Fire when the state exits because it failed |

When the task is set to fire only on exit, it stays **Running** for the duration of the state so it can observe the exit. When set to fire only on enter it completes immediately and does not hold up other tasks.

The task's label in the StateTree editor shows **(Enter)**, **(Exit)**, or **(Enter\|Exit)** so the timing is visible at a glance.

---

## Error Handling

If the actor is invalid, the component is not found, or the named function does not exist at runtime, the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

## Example

A patrol AI enters a **Search** state. On enter, Call Actor Event triggers `BP_StartSearchAnimation` on the character. On exit (succeeded), it triggers `BP_EndSearchAnimation`. The two calls are handled by a single task with **On Enter** and **On Exit — Succeeded** both enabled.

---

[← Back to Utilities | Events](events) · [← Back to home](..)
