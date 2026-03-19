---
title: Showcase
---

# Showcase: Patrol AI

This page walks through a simple AI built entirely with Unreal StateTree and StateTree Tools — no Blueprint or C++ required. The AI patrols by moving to random positions, chases the player when it sees them, and plays a hit animation when it catches up.

---

## The StateTree at a glance

![Full StateTree overview](/assets/showcase/Screenshot 2026-03-18 095445.png)

The tree has two selector states: **Patrol** and **ChasePlayer**. Patrol runs by default, looping between moving to a new position and waiting. ChasePlayer is entered when a perception event fires.

---

## Patrol

![Patrol state tasks](/assets/showcase/Screenshot 2026-03-18 100804.png)

The **MoveToNewPosition** state uses three tasks:

- **Get Random Reachable Point In Radius** — finds a random navigable point within a radius. The result is exposed as an output variable `RandomPoint`. This is a good example of the plugin's goal: things that previously required going out to Blueprint or C++ are now available directly in the StateTree.
- **Draw Debug Sphere** — visualises the target point. All of the Draw Debug utilities are exposed through the plugin.
- **Move To** — the standard Unreal Move To task, with its Destination bound to the `RandomPoint` output from the task above.

When Move To completes, the state transitions to **Wait**, which runs a Delay and then loops back to **MoveToNewPosition**.

---

## Perception

The AI uses Unreal's standard AI Perception system. To get those events into the StateTree, add a **Perception Event Forwarder** component alongside the AIPerception component on the same actor.

![PerceptionEventForwarder in the component list](/assets/showcase/Screenshot 2026-03-18 103728.png)

The component automatically forwards all perception events to any StateTree components on the same actor. Back in the StateTree, a transition on the Patrol state listens for the forwarded event:

![Transition on TargetUpdated event](/assets/showcase/Screenshot 2026-03-18 104356.png)

The transition fires on the `StateTreeTools.Events.Perception.TargetUpdated` event and exposes the payload — Actor, Stimulus, and Attitude — as bound outputs that downstream tasks can use.

---

## Chase state

![Chase state tasks overview](/assets/showcase/Screenshot 2026-03-18 105030.png)

The **Chase** state runs five tasks:

![Play Sound and Spawn Niagara task details](/assets/showcase/Screenshot 2026-03-18 105142.png)

**Play Sound At Location** plays a sound on enter. **Spawn System Attached** spawns a Niagara particle system. The Niagara task is aware of what the underlying system is doing — it completes when the particle system finishes. If the state exits early and the task is cancelled, you can configure whether particles are killed immediately or allowed to finish. This behaviour applies to all tasks in the plugin.

---

## Call Actor Event

![Call Actor Event SetFocus — setup expanded](/assets/showcase/Screenshot 2026-03-18 105623.png)

**Call Actor Event** lets you call any event or function on an actor or any of its components without leaving the StateTree. Set the actor, and the actor's class is determined automatically. Then pick the event from a searchable dropdown. Here, `K2_SetFocus` is called on enter, with the `New Focus` parameter bound to the perceived actor from the perception event payload.

Any event or function you have written in Blueprint or C++ will also appear in the list. For example, switching the event to `K2_SetActorLocation` exposes its own parameters inline:

![Call Actor Event SetActorLocation](/assets/showcase/Screenshot 2026-03-18 111100.png)

There are also tasks for calling delegates and setting properties:

![Call Actor Delegate example](/assets/showcase/Screenshot 2026-03-18 110649.png)

![Set Actor Property example](/assets/showcase/Screenshot 2026-03-18 110700.png)

---

## Call Pure Function

The Move To task needs a target actor to chase. Rather than storing a reference manually, its **Target Actor** is bound to a **Call Pure Function** property function.

![Move To with Call Pure Function GetFocusActor](/assets/showcase/Screenshot 2026-03-18 111100.png)

Call Pure Function works like Call Actor Event but for pure functions — it calls any `BlueprintPure` function on the actor or its components and exposes the return value as a binding. Here, `GetFocusActor` is called on the AI Controller so that Move To always chases whoever has focus.

---

## Firing on exit: ClearFocus

When the Chase state ends, the AI controller retains its focus actor and the enemy keeps staring at the player. To fix this, `K2_ClearFocus` is called on exit.

![Call Actor Event ClearFocus configured to fire on exit](/assets/showcase/Screenshot 2026-03-18 111650.png)

Tasks are started top-down but stopped bottom-up. To ensure ClearFocus is called after Move To has stopped, the ClearFocus task sits above Move To in the list. When the state exits, Move To stops first, then ClearFocus fires.

---

## Losing the player and transitions

![Chase state transitions](/assets/showcase/Screenshot 2026-03-18 112945.png)

The Chase state has two transitions:

- **On Event `TargetForgotten`** — if the enemy loses perception of the player, transition to **BeConfusedForASecond**, which delays briefly before the tree returns to Patrol.
- **On State Completed** — if Move To completes (the enemy reaches the player), transition to **Bounce**.

---

## Bounce: Play Montage

![Play Montage task](/assets/showcase/Screenshot 2026-03-18 114330.png)

The **Bounce** state plays an animation montage. The task completes when the montage finishes, at which point the tree transitions to **BeConfusedForASecond** and eventually returns to Patrol.

---

## Start Action And Wait

For cases where you do want to write Blueprint logic, **Start Action And Wait** bridges your code and the StateTree without any glue code.

![Start Action And Wait task configuration](/assets/showcase/Screenshot 2026-03-18 115310.png)

Create a Blueprint event whose first parameter is a `StateTreeToolsActionPayload`. Start Action And Wait calls that event and passes through any additional parameters. The task stays running until your Blueprint calls `Finish Action`.

![Blueprint: finishing the action](/assets/showcase/Screenshot 2026-03-18 120152.png)

![Blueprint: Starting and Stopping phases](/assets/showcase/Screenshot 2026-03-18 120420.png)

The payload has a **Phase** field that tells you whether the action is starting or being stopped early. If the state transitions out before your action calls Finish Action, the event fires again with `Phase = Stopping` so you can clean up. This makes it easy to connect any Blueprint logic to the StateTree without writing the surrounding lifecycle code yourself.

---

[← Back to home](/)
