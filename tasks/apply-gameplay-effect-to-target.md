---
title: Apply Gameplay Effect to Target
---

# Apply Gameplay Effect to Target

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Effects

Applies a gameplay effect from a source actor to a separate target actor's Ability System Component. The effect is optionally removed when the state exits depending on the **Remove When State Exits** setting. Supports overrides for level, duration, stack count, and SetByCaller magnitude maps.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component is the **source** of the effect (the instigating ASC).

### Target *(input)*
Bind this to the actor whose Ability System Component should **receive** the effect.

### Instigator *(optional input)*
The actor responsible for applying the effect, used for kill credit and gameplay cue contexts. Leave unbound to use no instigator.

### Effect Causer *(optional input)*
The physical actor that caused the effect (for example the projectile). Leave unbound to use no effect causer.

### Gameplay Effect
The `UGameplayEffect` subclass to apply.

### Level
The level of the gameplay effect to apply. Default is `0`.

### Add Asset Tags
Additional asset tags to merge onto the effect spec.

### Add Granted Tags
Additional granted tags to merge onto the effect spec.

### Use Duration
When enabled overrides the effect's duration with the **Duration** value. Default is `false`.

### Duration
The override duration in seconds. Only used when **Use Duration** is enabled.

### Use Stack Count
When enabled overrides the effect's initial stack count with the **Stack Count** value. Default is `false`.

### Stack Count
The override stack count. Only used when **Use Stack Count** is enabled.

### Set By Caller Name Magnitudes
A map of `FName` tags to float magnitudes for SetByCaller magnitude overrides.

### Set By Caller Tag Magnitudes
A map of `FGameplayTag` to float magnitudes for SetByCaller magnitude overrides.

### Remove When State Exits
When enabled the applied effect handle is removed when the state exits. Useful for duration-based or infinite effects that should only be active while the state is running. Default is `true`.

---

## Error Handling

If either actor has no Ability System Component or the Gameplay Effect class is invalid the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Abilities](/tasks/abilities) · [← Back to home](/)
