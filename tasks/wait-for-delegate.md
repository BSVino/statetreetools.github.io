---
title: WaitForDelegate
---

# WaitForDelegate

**Plugin:** StateTreeToolsCore
**Category:** Utilities | Events
**Availability:** StateTree Tools **2.0+**

Waits for one Blueprint-assignable multicast delegate on an actor or one of its components. When the selected delegate fires, the task copies supported payload values into fixed generic outputs and completes.

WaitForDelegate does not tick. On Unreal versions where StateTree supports async task completion, it stays active and is considered for state completion until the delegate fires.

---

## Configuration

### Actor
Bind this to the actor whose delegate you want to wait for. This is typically bound from the StateTree context or from a parent state.

### Actor Class
Set this to the Blueprint class of the actor. This is used in the editor to populate the component and delegate dropdowns and to validate that the selected delegate still exists.

### Component Name *(optional)*
If the delegate lives on a component rather than the actor itself, select the component here. Leave it empty to wait for a delegate directly on the actor.

### Delegate Name
Select the delegate to wait for from the dropdown. The list is populated from the Actor Class, or from the selected component's class if Component Name is set.

Only Blueprint-assignable inline multicast delegates with supported signatures are shown. Sparse delegates are not supported.

### Delegate Outputs Used
Read-only multiline legend showing which delegate parameters are copied into which output properties.

Example:

```text
Damage -> FloatOutput1
DamagedActor -> ActorOutput1
DamageCauser -> ActorOutput2
```

Unsupported parameters are ignored and are not listed in the legend.

---

## Outputs

WaitForDelegate exposes fixed generic outputs. The selected delegate determines which ones are populated.

Supported generic output types:
- `BoolOutput1`, `BoolOutput2`
- `FloatOutput1`, `FloatOutput2`
- `IntOutput1`, `IntOutput2`
- `NameOutput1`, `NameOutput2`
- `StringOutput1`, `StringOutput2`
- `TextOutput1`, `TextOutput2`
- `ActorOutput1`, `ActorOutput2`
- `ActorComponentOutput1`, `ActorComponentOutput2`
- `UserWidgetOutput1`, `UserWidgetOutput2`
- `HitResultOutput`

For primitive payloads, one-parameter delegates and every ordered two-parameter combination of `bool`, `float`, `int32`, `FName`, `FString`, and `FText` are supported.

Common actor, component, widget, hit result, enum, and engine event payload signatures are also supported. Enum and other unsupported parameters can still be accepted for completion, but they are ignored for outputs unless they map to one of the generic output types above.

---

## Runtime Behaviour

When the state enters, WaitForDelegate resolves the actor or selected component, binds to the chosen delegate, and returns Running.

When the delegate fires:
- Supported payload values are copied into the generic outputs.
- The task unbinds from the delegate.
- The task finishes successfully.

If the state exits before the delegate fires, the task unbinds cleanly.

The task completes only once, even if the underlying delegate fires multiple times.

---

## Error Handling

If the actor is invalid, the selected component cannot be found, the delegate has been renamed or deleted, or the delegate signature is unsupported, the task fails. You can control whether a failure causes the task to return Failed or Succeeded using **Error Means Failure**.

The editor validates the selected component and delegate when Actor Class is set, so renamed or deleted delegates are caught at compile time when possible.

[← Back to Utilities | Events](/tasks/events) · [← Back to home](/)
