---
title: Set Input Mode: Game Only
---

# Set Input Mode: Game Only

**Plugin:** StateTreeToolsCore
**Category:** Input
**Availability:** StateTree Tools **2.0+**

Calls Unreal's Set Input Mode Game Only function on a bound `APlayerController`. Use this to hand full input capture to the game, hiding and locking the cursor away from the UI.

---

## Configuration

### Player Controller *(input, optional)*
Bind this to the `APlayerController` you want to set input mode on. If not bound or invalid the task fails.

### Flush Input
When enabled, flushes any pending input events immediately after switching modes. Default: off.

---

## When to Fire

By default the mode is set when the state is **entered**. You can also set it on **exit**, with separate toggles for which exit reasons trigger the call (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

## Error Handling

If **Player Controller** is invalid the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to Input](/tasks/input) · [← Back to home](/)
