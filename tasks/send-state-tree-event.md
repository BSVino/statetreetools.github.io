---
title: Send State Tree Event
---

# Send State Tree Event

**Plugin:** StateTreeToolsCore
**Category:** Gameplay|StateTree

Sends a StateTree event with an optional typed payload to an actor's StateTree component(s). If no **State Tree Component Name** is specified the event is broadcast to every StateTree component on the actor. If the task is not configured to send on exit it completes immediately after sending on enter.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose StateTree component(s) should receive the event.

### State Tree Component Name
The name of a specific `UStateTreeComponent` on the actor to target. Leave as `None` to send the event to all StateTree components on the actor.

### Event Tag
The `FGameplayTag` that identifies the event. Must be from the `StateTreeEvent` tag category.

### Payload
An `FInstancedStruct` that carries typed data with the event. Pick any struct type — its fields appear inline in the editor as the payload.

### Origin
An optional name identifying the source of the event. Leave as `None` if the origin does not matter.

---

## When to Fire

By default the event is sent when the state is **entered**. You can also send it on **exit**, with fine-grained control over which exit reasons trigger the send (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

## Error Handling

If the actor is invalid or has no StateTree component the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Gameplay \| StateTree](/tasks/statetree) · [← Back to home](/)
