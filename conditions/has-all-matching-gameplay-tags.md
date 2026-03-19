---
title: Has All Matching Gameplay Tags
---

# Has All Matching Gameplay Tags

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Returns true if the bound actor's Ability System Component has **every** tag in the specified container. Use this when you need all of a set of conditions to be simultaneously active — for example, requiring both a "Charged" tag and a "TargetAcquired" tag before entering an attack state.

Returns false if the actor has no Ability System Component or the container is empty.

---

## Configuration

### Actor
Bind this to the actor whose Ability System Component you want to check.

### Gameplay Tags
The container of tags to check. All tags in the container must be present on the ASC for the condition to pass. Each tag follows Unreal's standard tag hierarchy rules — a more specific tag satisfies a parent tag check.

### Invert
When enabled, the result is flipped — the condition passes when the actor does **not** have all of the tags. Default is off.

---

[← Back to Gameplay Tags](/conditions/gameplay-tags) · [← Back to home](/)
