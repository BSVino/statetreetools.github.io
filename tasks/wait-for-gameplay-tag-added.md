---
title: Wait For Gameplay Tag Added
---

# Wait For Gameplay Tag Added

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Category:** Gameplay Tags

Keeps the task running until the specified gameplay tag is added to the bound actor's Ability System Component. When the tag is detected the **On Tag Changed** delegate dispatcher fires and the configured **Output Event** is dispatched, then the task succeeds.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Ability System Component should be monitored for the tag.

### Tag
The `FGameplayTag` to watch for. The task succeeds when this tag is added to the ASC.

### On Tag Changed *(output)*
A `FStateTreeDelegateDispatcher` that fires when the tag is added. Bind this output to other parts of the tree if you need to react to the change outside of normal task completion.

### Output Event
A `FStateTreeTools_OutputEventAction` that configures an optional StateTree event to dispatch automatically when the tag is added.

---

## Error Handling

If the actor is invalid or has no Ability System Component the task will fail. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

[← Back to Abilities](/tasks/abilities) · [← Back to home](/)
