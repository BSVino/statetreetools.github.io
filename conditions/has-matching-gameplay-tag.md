---
title: Has Matching Gameplay Tag
---

# Has Matching Gameplay Tag

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Returns true if the bound actor's Ability System Component currently has the specified gameplay tag. Use this in transitions or state selection to react to tag state — for example blocking a transition while a cooldown tag is present, or entering a state only when a status effect tag is active.

Returns false if the actor has no Ability System Component or the tag is not set.

---

## Configuration

### Actor
Bind this to the actor whose Ability System Component you want to check.

### Gameplay Tag
The tag to check for. The condition passes if the ASC has this tag (or a child of it, matching Unreal's standard tag hierarchy rules).

### Invert
When enabled, the result is flipped — the condition passes when the tag is **not** present. Default is off.

---

[← Back to Gameplay Tags](/conditions/gameplay-tags) · [← Back to home](/)
