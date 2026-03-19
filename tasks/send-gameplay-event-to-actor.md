---
title: Send Gameplay Event To Actor
---

# Send Gameplay Event To Actor

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Abilities

Sends a gameplay event to an actor's Ability System Component using `SendGameplayEventToActor`. If the task is not configured to send on exit it completes immediately after sending on enter.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component should receive the event.

### Gameplay Event Tag
The `FGameplayTag` that identifies the event.

### Gameplay Event Data
The `FGameplayEventData` payload to send with the event. This includes source and target actors, event magnitude, and an optional target data handle.

---

## When to Fire

By default the event is sent when the state is **entered**. You can also send it on **exit**, with separate toggles for which exit reasons trigger the send (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

## Error Handling

If the actor is invalid or has no Ability System Component the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Abilities](/tasks/abilities) · [← Back to home](/)
