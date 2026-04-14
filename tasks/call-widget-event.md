---
title: Call Widget Event
---

# Call Widget Event

**Plugin:** StateTreeToolsCore
**Category:** UI
**Availability:** StateTree Tools **2.0+**

Calls a BlueprintCallable or Blueprint Event function on a bound `UUserWidget` by name. Works the same way as [Call Actor Event](/tasks/call-actor-event) but targets a widget directly — no component name needed.

---

## Configuration

### Widget *(input)*
Bind this to the `UUserWidget` you want to call the function on (e.g. the output of a [Create Widget](/tasks/create-widget) task).

### Widget Class
Set this to the class of the bound widget. The editor uses this to populate the **Event Name** dropdown. When **Widget** is bound and the class can be inferred from the binding it is filled in automatically.

### Event Name
Pick the function to call from the dropdown. Only BlueprintCallable and Blueprint Event functions defined in the widget's Blueprint class appear — native handlers such as `Construct` and `Tick` are excluded.

### Parameters
Auto-populated when **Event Name** is selected. One field appears per input parameter of the chosen function. Fill in or bind each field as needed.

---

## When to Fire

By default the event is called when the state is **entered**. You can also call it on **exit**, with separate toggles for which exit reasons trigger the call (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

## Error Handling

If **Widget** is invalid or the function cannot be found at runtime the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to UI](/tasks/ui) · [← Back to home](/)
