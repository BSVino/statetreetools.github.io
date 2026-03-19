---
title: Wait For Gameplay Tag Removed
---

# Wait For Gameplay Tag Removed

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Keeps the task running until the specified gameplay tag is removed from the bound actor's Ability System Component. When the tag is no longer present the **On Tag Changed** delegate dispatcher fires and the configured **Output Event** is dispatched, then the task succeeds.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component should be monitored for the tag.

### Tag
The `FGameplayTag` to watch. The task succeeds when this tag is removed from the ASC.

### On Tag Changed *(output)*
A `FStateTreeDelegateDispatcher` that fires when the tag is removed. Bind this output to other parts of the tree if you need to react to the change outside of normal task completion.

### Output Event
A `FStateTreeTools_OutputEventAction` that configures an optional StateTree event to dispatch automatically when the tag is removed.

---

## Error Handling

If the actor is invalid or has no Ability System Component the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Abilities](/tasks/abilities) · [← Back to home](/)
