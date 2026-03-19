---
title: Matches Gameplay Tag Query
---

# Matches Gameplay Tag Query

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Returns true if the bound actor's Ability System Component satisfies the specified gameplay tag query. Use this when a single tag check is not enough — for example, requiring that the actor has a "Stunned" tag but not a "Immune" tag, or that it has any one of several debuff tags.

Returns false if the actor has no Ability System Component or the query is empty.

---

## Configuration

### Actor
Bind this to the actor whose Ability System Component you want to evaluate.

### Gameplay Tag Query
The query to evaluate against the actor's tag container. Constructed using Unreal's tag query builder, which supports AND, OR, and NOT logic over gameplay tags and tag containers.

### Invert
When enabled, the result is flipped — the condition passes when the query is **not** satisfied. Default is off.

---

[← Back to Gameplay Tags](/conditions/gameplay-tags) · [← Back to home](/)
