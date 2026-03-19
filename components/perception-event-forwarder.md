---
title: Perception Event Forwarder
---

# Perception Event Forwarder

**Plugin:** StateTreeToolsCore
**Class:** `UPerceptionEventForwarder`

Bridges the AI perception system and the StateTree event system. Add this component alongside a `UAIPerceptionComponent` on an AI controller or character. At runtime it listens to the perception component's delegates and fires StateTree events whenever a target is detected or forgotten, so your StateTree can react to perception without any custom C++.

---

## Events Fired

Both events are sent to all `UStateTreeComponent`s on the same actor (or filtered to one by name — see **State Tree Component Name** below).

### `StateTreeTools.Events.Perception.TargetUpdated`

Fired by `OnTargetPerceptionUpdated`. The event payload is `FTargetPerceptionUpdatedPayload`:

| Field | Type | Description |
|-------|------|-------------|
| `Actor` | `AActor*` | The perceived actor |
| `Stimulus` | `FAIStimulus` | Full stimulus data — sense class, strength, age, success flag |
| `Attitude` | `ETeamAttitude` | Relationship between owner and perceived actor (`Friendly`, `Neutral`, `Hostile`) |

### `StateTreeTools.Events.Perception.TargetForgotten`

Fired by `OnTargetPerceptionForgotten`. The event payload is `FTargetPerceptionForgottenPayload`:

| Field | Type | Description |
|-------|------|-------------|
| `Actor` | `AActor*` | The forgotten actor |
| `Attitude` | `ETeamAttitude` | Relationship between owner and forgotten actor |

---

## Configuration

### State Tree Component Name
The name of the `UStateTreeComponent` on the owner to send events to. Leave as `None` (default) to broadcast to every StateTree component on the actor. Set this if the actor has multiple StateTree components and you want to target only one.

---

## Setup

1. Add a `UAIPerceptionComponent` to your AI character or controller and configure the senses you need (e.g. Sight, Hearing).
2. Add `UPerceptionEventForwarder` to the same actor.
3. In your StateTree, add a transition with **On Event** set to `StateTreeTools.Events.Perception.TargetUpdated` or `StateTreeTools.Events.Perception.TargetForgotten`.
4. Bind the event payload fields (e.g. `Payload.Actor`, `Payload.Stimulus.bWasSuccessfullySensed`, `Payload.Attitude`) using the StateTree binding system.

The component logs a warning and becomes inactive if no `UAIPerceptionComponent` is found on the owner at `BeginPlay`.

---

[← Back to home](/)
