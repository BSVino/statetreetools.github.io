---
title: Showcase
---

# Showcase: Patrol AI

A simple AI built entirely with Unreal StateTree and StateTree Tools — no Blueprint or C++ required. The AI patrols by moving to random positions, chases the player when it sees them, and plays a hit animation when it catches up.

[Watch the showcase video on YouTube](https://www.youtube.com/watch?v=E8ofooxPY4M)

![Full StateTree overview](/assets/showcase/Screenshot 2026-03-18 095445.png)

---

## Call Actor Event

![Call Actor Event SetFocus — setup expanded](/assets/showcase/Screenshot 2026-03-18 105623.png)

[Call Actor Event](/tasks/call-actor-event) lets you call any event or function on an actor or any of its components directly from a StateTree state. Set the actor, and the actor's class is determined automatically. Then pick the event from a searchable dropdown. Here, `K2_SetFocus` is called on enter, with the `New Focus` parameter bound to the perceived actor from the perception event payload.

Any event or function you have written in Blueprint or C++ will also appear in the list. For example, switching to `K2_SetActorLocation` exposes its own parameters inline:

![Call Actor Event SetActorLocation](/assets/showcase/Screenshot 2026-03-18 111100.png)

You can also configure when the event fires — on enter, on exit, or both. Here `K2_ClearFocus` is called on exit to clear the AI's focus when the Chase state ends:

![Call Actor Event ClearFocus configured to fire on exit](/assets/showcase/Screenshot 2026-03-18 111650.png)

Tasks are started top-down but stopped bottom-up. The ClearFocus task sits above Move To so that Move To stops first and ClearFocus fires after.

There are also tasks for [Call Actor Delegate](/tasks/call-actor-delegate) and [Set Actor Property](/tasks/set-actor-property):

![Call Actor Delegate example](/assets/showcase/Screenshot 2026-03-18 110649.png)

![Set Actor Property example](/assets/showcase/Screenshot 2026-03-18 110700.png)

---

## Call Pure Function

[Call Pure Function](/property-functions/call-pure-function) is a property function — it calls any `BlueprintPure` function on an actor or its components and exposes the return value as a binding anywhere a value can be bound in the StateTree editor. Here the Move To task's **Target Actor** is bound to `GetFocusActor` on the AI Controller, so it always chases whoever has focus without needing to store the reference manually:

![Move To with Call Pure Function GetFocusActor](/assets/showcase/Screenshot 2026-03-18 111100.png)

---

## Start Action And Wait

For cases where you want to write Blueprint logic, [Start Action And Wait](/tasks/start-action-and-wait) lets you tie that code into the StateTree without writing any glue code.

![Start Action And Wait task configuration](/assets/showcase/Screenshot 2026-03-18 115310.png)

Create a Blueprint event whose first parameter is a `StateTreeToolsActionPayload`. [Start Action And Wait](/tasks/start-action-and-wait) calls that event, passes through any additional parameters, and keeps the task running until your Blueprint calls `Finish Action`:

![Blueprint: finishing the action](/assets/showcase/Screenshot 2026-03-18 120152.png)

The payload has a **Phase** field — `Starting` or `Stopping`. If the state transitions out before Finish Action is called, the event fires again with `Phase = Stopping` so you can clean up:

![Blueprint: Starting and Stopping phases](/assets/showcase/Screenshot 2026-03-18 120420.png)

---

## Perception

The AI uses Unreal's standard AI Perception system. To get those events into the StateTree, add a [Perception Event Forwarder](/components/perception-event-forwarder) component alongside the AIPerception component on the same actor:

![PerceptionEventForwarder in the component list](/assets/showcase/Screenshot 2026-03-18 103728.png)

The component automatically forwards all perception events to any StateTree components on the same actor. A transition on the Patrol state listens for the forwarded event and carries the full payload — Actor, Stimulus, and Attitude — as bound outputs for downstream tasks:

![Transition on TargetUpdated event](/assets/showcase/Screenshot 2026-03-18 104356.png)

The Chase state transitions out when perception is lost or when Move To completes:

![Chase state transitions](/assets/showcase/Screenshot 2026-03-18 112945.png)

---

## Patrol

![Patrol state tasks](/assets/showcase/Screenshot 2026-03-18 100804.png)

The **MoveToNewPosition** state uses three tasks:

- [Get Random Reachable Point In Radius](/tasks/get-random-reachable-point-in-radius) — finds a random navigable point and exposes it as an output variable.
- **Draw Debug Sphere** — visualises the target point. All Draw Debug utilities are available through the plugin.
- **Move To** — the standard Unreal Move To task, with its Destination bound to the output above.

---

## Chase state

![Chase state tasks overview](/assets/showcase/Screenshot 2026-03-18 105030.png)

![Play Sound and Spawn Niagara task details](/assets/showcase/Screenshot 2026-03-18 105142.png)

On entering Chase, [Play Sound At Location](/tasks/play-sound-at-location) fires a sound and [Spawn System Attached](/tasks/spawn-system-attached) spawns a Niagara particle system. The Niagara task completes when the particle system finishes. If the state exits early you can configure whether particles are killed immediately or allowed to complete.

---

## Play Montage

![Play Montage task](/assets/showcase/Screenshot 2026-03-18 114330.png)

The **Bounce** state plays a [Play Montage](/tasks/play-montage) task and completes when it finishes, at which point the tree returns to Patrol.

---

[← Back to home](/)
