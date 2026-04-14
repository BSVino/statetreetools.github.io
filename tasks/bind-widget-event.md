---
title: BindWidgetEvent
---

# BindWidgetEvent

**Plugin:** StateTreeToolsCore
**Category:** UI
**Availability:** StateTree Tools **2.0+**

Listens to one selected widget event on a bound `UUserWidget` and forwards it into StateTree. The task can either broadcast a StateTree delegate for **On Delegate** transitions or send a typed StateTree event.

Use one task instance per forwarded UI event. If you want to react to several buttons or widget events, place several BindWidgetEvent tasks.

---

## Configuration

### Widget
Bind this to the root `UUserWidget` that contains the widget you want to listen to. This can come from [Create Widget](/tasks/create-widget) or from any other widget reference you already have.

### Root Widget Class
Used in the editor to discover named widgets and validate the selected event. It does not control runtime lookup. The selected target widget still needs to already exist when the task enters.

### Target Widget
Select the named widget to listen to from the dropdown. Entries are shown as `WidgetName (WidgetClass)`.

Only widgets that support at least one bindable event are shown in this list. This includes regular `UButton` widgets and Common UI buttons derived from `UCommonButtonBase`.

### Widget Event
Select which event on that widget should be forwarded.

The following built-in UMG controls are supported:
- Button clicked, pressed, and released, including Common UI buttons based on `UCommonButtonBase`
- Common UI buttons based on `UCommonButtonBase`: clicked
- CheckBox state changed
- Editable text changed and committed
- Slider value changed
- ComboBoxString selection changed

### Output Mode
Choose how the UI event should be forwarded:
- **Broadcast Delegate**: broadcasts the task's output delegate so transitions can use **On Delegate**
- **Send StateTree Event**: sends a StateTree event with a typed payload

### StateTree Event Tag
Shown only when **Output Mode** is set to **Send StateTree Event**. This is the event tag that will be sent when the selected widget event fires.

### Event Payload Name
When **Send StateTree Event** is selected, the task shows a read-only field containing the exact payload struct type name that will be sent for the selected widget event.

### Delegate Outputs Used
When **Output Mode** is set to **Broadcast Delegate**, the task shows a read-only multiline legend describing which task outputs are populated for the selected widget event.

---

## Delegate Mode Outputs
When **Output Mode** is **Broadcast Delegate**, the task exposes one output delegate plus output values describing the last forwarded event.

### On Triggered
Bind transitions to this using **On Delegate**.

### Shared Outputs
These are populated for every supported widget event:
- `TriggeredWidget`
- `TriggeredWidgetName`
- `TriggeredEventKind`

### Event-specific Outputs
Additional outputs depend on the selected widget event:
- Common UI buttons based on `UCommonButtonBase`: clicked
- CheckBox state changed: `BoolValue`
- Text changed: `TextValue`
- Text committed: `TextValue`, `CommitMethod`
- Slider value changed: `FloatValue`
- ComboBox selection changed: `StringValue`, `SelectionType`

`CommitMethod` uses `ETextCommit::Type`.

`SelectionType` uses `ESelectInfo::Type`.

Common UI buttons currently support the click event. Pressed and released remain regular `UButton`-only events in BindWidgetEvent.

---

## StateTree Event Payloads
When **Output Mode** is **Send StateTree Event**, the payload type is chosen automatically from the selected widget event.

Examples:
- Regular button events and Common UI button click events send a button payload with the triggering widget and widget name
- Common UI buttons based on `UCommonButtonBase`: clicked
- CheckBox state changed sends a payload with the widget, widget name, and checked state
- Text changed sends a payload with the widget, widget name, and text
- Text committed sends a payload with the widget, widget name, text, and commit method
- Slider value changed sends a payload with the widget, widget name, and float value
- ComboBox selection changed sends a payload with the widget, widget name, selected item, and selection type

---

## Runtime Behaviour
The task stays active while the root widget exists.

The selected target widget must already exist when the task enters. BindWidgetEvent no longer polls for widgets that are added later at runtime.

If the root widget is destroyed, the task completes.

---

## Error Handling
If the bound root widget is invalid when the task starts, the task fails. The task also fails if the selected target widget does not already exist when the task enters. If a root widget class is provided, the editor also validates that the selected target widget and selected widget event are still valid for that class.

[← Back to UI](/tasks/ui) · [← Back to home](/)