---
title: Get Widget Animation
---

# Get Widget Animation

**Plugin:** StateTreeToolsCore
**Category:** UI
**Available since:** StateTree Tools 2.0

Gets a widget animation from a bound `UUserWidget` by name. Set the widget class to populate the animation dropdown, then choose one of the animations defined on that Widget Blueprint.

This is useful when another StateTree task, Blueprint event, or bound value needs a `UWidgetAnimation` reference without hard-coding the animation lookup in Blueprint or C++.

---

## Configuration

### Widget
Bind this to the widget instance that owns the animation.

### Widget Class
Set this to the widget's class. The editor uses it to populate the animation dropdown and validate that the selected animation still exists.

### Animation Name
Select the animation to retrieve. The dropdown is populated from `UWidgetAnimation` properties on the selected widget class.

### Output
The selected `UWidgetAnimation` from the bound widget. If the widget is invalid or the animation cannot be found, the output is None.

## Unreal Engine Version Notes

Property functions are not available in UE 5.4. This node requires **UE 5.5 or later**.

---

[← Back to UI](/property-functions/ui) · [← Back to home](/)