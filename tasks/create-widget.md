---
title: Create Widget
---

# Create Widget

**Plugin:** StateTreeToolsCore
**Category:** UI
**Availability:** StateTree Tools **2.0+**

Creates a `UUserWidget` from a widget class, optionally adds it to the viewport, and outputs the created widget so other nodes can reference it.

---

## Configuration

### Widget Class
The widget class to instantiate.

### Player Controller
Optional owning player for the widget. Bind this when the widget should belong to a specific local player or player controller context.

### Expose On Spawn Properties
Automatically populated from the selected **Widget Class**. Any widget properties marked **Expose on Spawn** appear here and can be filled in directly or bound from elsewhere in the StateTree.

### Add To Viewport
When enabled, the created widget is immediately added to the viewport.

### ZOrder
Only shown when **Add To Viewport** is enabled. Higher values appear in front of lower values.

### Remove From Parent On Exit
When enabled, the task calls `RemoveFromParent()` on the created widget when the state exits.

### Widget
Output reference to the created widget.

---

## Runtime Behaviour

### UE 5.6 and later
The task creates the widget and then stays running until the widget is destroyed. It completes asynchronously without using per-frame tick.

### UE 5.5 and earlier
The task creates the widget and succeeds immediately after creation. Earlier StateTree versions do not support the same async completion path used by newer engine versions.

---

## Error Handling

If the widget class is invalid, widget creation fails, or the expose-on-spawn property bag no longer matches the selected widget class at runtime, the task will fail. You can control whether that produces **Failed** or **Succeeded** using **Error Means Failure**.

[← Back to UI](/tasks/ui) · [← Back to home](/)