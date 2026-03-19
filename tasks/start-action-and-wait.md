---
title: Start Action And Wait
---

# Start Action And Wait

**Plugin:** StateTreeToolsCore
**Category:** Gameplay | Events

Calls a Blueprint event on an actor and keeps the state alive until the Blueprint signals that the action is complete. This is the primary way to drive async Blueprint logic — such as playing a cutscene, running a custom animation sequence, or waiting for player input — directly from a StateTree state.

---

## How It Works

When the state is entered, the task calls the configured Blueprint event and passes it an `FStateTreeTools_ActionPayload` containing a **Phase** (`Starting`) and a **Handle**. The state remains active until your Blueprint calls `Finish Action` with that handle.

If the state is exited before the Blueprint finishes — because a higher-priority transition fired — the task calls the same event again with **Phase = Stopping**, giving your Blueprint a chance to clean up (stop a sound, end an animation, etc.). The task then completes regardless of whether `Finish Action` is called during the stopping phase.

---

## Setting Up the Blueprint Event

Your Blueprint event must have `FStateTreeTools_ActionPayload` as its **first parameter**. Only events with this signature appear in the Event Name dropdown.

Inside the event:

1. Branch on **Phase**: handle `Starting` to begin your work, and `Stopping` to cancel or clean up.
2. When your async work is done, call **Finish Action** (from the StateTree Tools function library), passing the **Handle** from the payload and whether the action succeeded.

`Finish Action` can be called from anywhere — a timer, an animation notify, a delegate — as long as you have the handle.

---

## Configuration

### Actor
Bind this to the actor whose Blueprint event you want to call.

### Actor Class
Set this to the Blueprint class of the actor. Used in the editor to populate the event dropdown; does not affect runtime behaviour.

### Component Name *(optional)*
If the event lives on a component rather than the actor itself, enter the component's name here.

### Event Name
Select the event to call from the dropdown. Only Blueprint events whose first parameter is `FStateTreeTools_ActionPayload` are listed.

### Parameters
Any input parameters on the event beyond the payload appear here automatically and can be filled in or bound to values elsewhere in the StateTree.

### Use Timeout
If enabled, the task automatically fails after **Timeout Seconds** if `Finish Action` has not been called. Useful as a safeguard against Blueprint logic that never completes. Whether a timeout counts as a failure or a success is controlled by the **Error Means Failure** option.

---

## Error Handling

If the actor is invalid, the component is not found, or the named event does not exist at runtime, the task will fail. You can control whether this returns **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to Gameplay \| Actions](/tasks/actions) · [← Back to home](/)
