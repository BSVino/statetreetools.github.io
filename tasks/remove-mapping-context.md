---
title: Remove Mapping Context
---

# Remove Mapping Context

**Plugin:** StateTreeToolsCore
**Category:** Enhanced Input
**Availability:** StateTree Tools **2.0+**

Removes an Input Mapping Context from the Enhanced Input Local Player Subsystem. Wraps the Blueprint **Remove Mapping Context** node.

Bind the **Subsystem** input from a [Get Enhanced Input Local Player Subsystem](/property-functions/get-enhanced-input-local-player-subsystem) property function.

---

## Configuration

### Subsystem *(input)*
Bind this to the `UEnhancedInputLocalPlayerSubsystem` you want to remove the context from. If invalid the task fails.

### Mapping Context
The `UInputMappingContext` asset to remove.

### Options

| Option | Default | Description |
|--------|---------|-------------|
| Ignore All Pressed Keys Until Release | On | Prevents currently held keys from triggering actions until they are released after the context is removed. |
| Force Immediately | Off | Forces the input mapping rebuild to happen immediately rather than being deferred to the next frame. |

---

## When to Fire

By default the context is removed when the state is **entered**. You can also remove it on **exit**, with separate toggles for which exit reasons trigger the call (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

## Error Handling

If **Subsystem** or **Mapping Context** is invalid the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to Enhanced Input](/tasks/enhanced-input) · [← Back to home](/)
