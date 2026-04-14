---
title: Set Input Mode: UI Only
---

# Set Input Mode: UI Only

**Plugin:** StateTreeToolsCore
**Category:** Input
**Availability:** StateTree Tools **2.0+**

Calls Unreal's Set Input Mode UI Only function on a bound `APlayerController`. Use this to hand full input capture to the UI, preventing the game from receiving input while a menu or overlay is active.

---

## Configuration

### Player Controller *(input, optional)*
Bind this to the `APlayerController` you want to set input mode on. If not bound or invalid the task fails.

### Widget To Focus *(input, optional)*
Bind this to the widget that should receive focus when the input mode is applied. Leave unbound to apply UI-only mode without explicitly focusing a widget.

### Mouse Lock Mode
Controls how the mouse cursor is locked to the viewport while in UI-only mode. Default: **Do Not Lock**.

| Value | Behaviour |
|-------|-----------|
| Do Not Lock | Cursor moves freely |
| Lock On Capture | Locked only while a mouse button is held |
| Lock Always | Always locked to the viewport |
| Lock In Fullscreen | Locked only when the application is fullscreen |

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
