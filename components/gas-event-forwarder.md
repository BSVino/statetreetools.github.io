---
title: GAS Event Forwarder
---

# GAS Event Forwarder

**Plugin:** StateTreeToolsGameplayAbilitySystem
**Class:** `UGASEventForwarder`

This component is only available when Unreal's built-in **Gameplay Abilities** plugin is enabled.

Bridges the Gameplay Ability System and the StateTree event system. Add this component to any actor that has an `UAbilitySystemComponent`. It handles two kinds of forwarding:

- **GAS gameplay events** — maps each incoming `FGameplayEventData` to a chosen StateTree event tag.
- **Gameplay tag changes** — watches specific tags and fires a StateTree event whenever one is added or removed.

Both mechanisms run automatically at `BeginPlay` with no C++ required.

---

## Configuration

### Forward GAS Events to StateTree Events

A map from a GAS gameplay event tag to a StateTree event configuration. Each entry has:

| Field | Description |
|-------|-------------|
| Key (`FGameplayTag`) | The GAS gameplay event tag to listen for |
| `StateTree Tag` | The tag to use when forwarding the event into the StateTree |

When the GAS event fires, the full `FGameplayEventData` payload is wrapped in an `FInstancedStruct` and sent to all `UStateTreeComponent`s on the actor under the mapped StateTree tag. Bind `Payload.EventTag`, `Payload.Instigator`, `Payload.Target`, `Payload.EventMagnitude`, or other fields in your StateTree transitions.

### Tags to Watch for Added

A list of gameplay tags. Whenever one of these tags is added to the actor's ASC, a StateTree event is fired with the tag `StateTreeTools.Events.TagAdded`. The payload is `FTagChangedPayload`:

| Field | Type | Description |
|-------|------|-------------|
| `ChangedTag` | `FGameplayTag` | The tag that was added |

If the tag is already present when `BeginPlay` runs, the event fires immediately.

### Tags to Watch for Removed

A list of gameplay tags. Whenever one of these tags is removed from the actor's ASC, a StateTree event is fired with the tag `StateTreeTools.Events.TagRemoved`. The payload is also `FTagChangedPayload` with the tag that was removed.

If the tag is already absent when `BeginPlay` runs, the event fires immediately.

---

## Setup

1. Enable Unreal's built-in **Gameplay Abilities** plugin.
2. Add `UGASEventForwarder` to any actor that has an `UAbilitySystemComponent`.
3. To forward GAS gameplay events: add entries to **Forward GAS Events to StateTree Events**, setting the GAS tag and the StateTree tag you want to raise.
4. To react to tag changes: add tags to **Tags to Watch for Added** or **Tags to Watch for Removed**.
5. In your StateTree, add transitions with **On Event** set to the appropriate tag (`StateTreeTools.Events.TagAdded`, `StateTreeTools.Events.TagRemoved`, or your custom mapped tag).

The component logs an error if no `UAbilitySystemComponent` is found on the owner when tag watching is configured.

---

[← Back to home](/)
