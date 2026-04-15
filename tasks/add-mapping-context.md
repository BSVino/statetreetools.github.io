---
title: Add Mapping Context
---

# Add Mapping Context

**Plugin:** StateTreeToolsCore
**Category:** Enhanced Input
**Availability:** StateTree Tools **2.0+**

Adds an Input Mapping Context to the Enhanced Input Local Player Subsystem. Wraps the Blueprint **Add Mapping Context** node.

Bind the **Subsystem** input from a [Get Enhanced Input Local Player Subsystem](/property-functions/get-enhanced-input-local-player-subsystem) property function.

---

## Configuration

### Subsystem *(input)*
Bind this to the `UEnhancedInputLocalPlayerSubsystem` you want to add the context to. If invalid the task fails.

### Mapping Context
The `UInputMappingContext` asset to add.

### Priority
Priority of this mapping context relative to others. Higher values take precedence. Default: `0`.

### Options

| Option | Default | Description |
|--------|---------|-------------|
| Ignore All Pressed Keys Until Release | On | Prevents currently held keys from triggering actions until they are released after the context is added. |
| Force Immediately | Off | Forces the input mapping rebuild to happen immediately rather than being deferred to the next frame. |

---

## When to Fire

By default the context is added when the state is **entered**. You can also add it on **exit**, with separate toggles for which exit reasons trigger the call (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

### Remove On Exit State
When enabled, the mapping context is removed when the task exits. Only available when **Call On Enter State** is enabled. **Remove On Exit State** and **Call On Exit State** cannot both be enabled — the StateTree compiler will reject that configuration.

---

## Error Handling

If **Subsystem** or **Mapping Context** is invalid the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to Enhanced Input](/tasks/enhanced-input) · [← Back to home](/)
