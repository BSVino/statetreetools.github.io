---
title: Get Float Attribute
---

# Get Float Attribute

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Attributes

Returns the current (modified) value of a Gameplay Attribute on an actor's Ability System Component. This is the value after all active gameplay effects and modifiers have been applied. Use this to read the live state of any float attribute — such as Health, Stamina, or MovementSpeed — and feed it into StateTree bindings or transition conditions.

---

## Configuration

### Actor
The actor whose Ability System Component holds the attribute. Bind this to the actor you want to query.

### Attribute
The `FGameplayAttribute` to read. Select the attribute from the picker in the details panel.

### AttributeValue
The current modified value of **Attribute** on **Actor**'s Ability System Component.

---

[← Back to Gameplay Attributes](/property-functions/gameplay-attributes) · [← Back to home](/)
