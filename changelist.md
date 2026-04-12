---
title: Changelist
---

# Changelist

## Version 2.0 (Development Branch)

### Components

- [Primitive Event Forwarder](/components/primitive-event-forwarder)
  Forwards primitive component events into StateTree components on the same actor, similar to how the existing perception and GAS forwarders work.
  Includes support for begin/end overlap, hit, wake/sleep, physics state changed, cursor over, click/release, and touch begin/end/enter/leave events.
  Sends typed FStateTreeEvent payloads tagged under the StateTreeTools.Events.Primitive.* namespace.

### Editor and Compile Validation Improvements

- [CallComponentDelegate](/tasks/call-component-delegate)
  Added a task for broadcasting Blueprint-assignable multicast delegates directly on a bound actor component, with the same parameter bag workflow as [CallActorDelegate](/tasks/call-actor-delegate).

- Optional GAS sub-plugin loading
  StateTree Tools Gameplay Ability System is now optional instead of always-on.
  The GAS sub-plugin only becomes available and loads when Unreal's built-in Gameplay Abilities plugin is enabled; otherwise StateTree Tools Core still loads normally without GAS-specific nodes.

- Compile-time validation for selected events, delegates, properties, and functions
  Nodes that let you choose actor events, delegates, properties, and pure functions now validate those selections during compile.
  This catches cases where a Blueprint event, delegate, function, or property was deleted or renamed after the node was configured, instead of silently leaving an invalid selection behind.

### Property Functions

- [GetComponentByClass](/property-functions/get-component-by-class)
  Added a property function that mirrors Unreal's Blueprint [Get Component By Class](/property-functions/get-component-by-class) node and returns the first matching component on a bound actor.

## Version 1.0

### Tasks

- [CallActorEvent](/tasks/call-actor-event)
  Calls any event or non-pure function on any actor or its components.

- [SetActorProperty](/tasks/set-actor-property)
  Sets any property on any actor or its components.

- [CallActorDelegate](/tasks/call-actor-delegate)
  Calls any delegate on any actor or its components.

- [StartActionAndWait](/tasks/start-action-and-wait)
  Calls an event on an actor or component, then keeps the task active until the event calls the `Finish Action` Blueprint node.

- [PlayMontage](/tasks/play-montage)
  Plays animation montages from StateTree tasks.

- [PlaySoundAtLocation](/tasks/play-sound-at-location), [SpawnSoundAtLocation](/tasks/spawn-sound-at-location), [PlaySound2D](/tasks/play-sound-2d), [SpawnSound2D](/tasks/spawn-sound-2d)
  Audio playback tasks for world-space and 2D sounds.

- [DrawDebugLine](/tasks/draw-debug-line), [DrawDebugPoint](/tasks/draw-debug-point), [DrawDebugDirectionalArrow](/tasks/draw-debug-directional-arrow), [DrawDebugBox](/tasks/draw-debug-box), [DrawDebugSphere](/tasks/draw-debug-sphere), and more
  Includes the full set of debug draw helpers, plus FlushPersistentDebugLines and FlushDebugStrings.

- [GetRandomReachablePointInRadius](/tasks/get-random-reachable-point-in-radius)
  Finds a random reachable navigation point for wandering and patrol behaviors.

- [SpawnSystemAttached](/tasks/spawn-system-attached) and [SpawnSystemAtLocation](/tasks/spawn-system-at-location)
  Niagara spawning tasks for attached and world-space effects.

- [SendStateTreeEvent](/tasks/send-state-tree-event)
  Sends a StateTree event from a StateTree task.

- GAS: [WaitForGameplayTagAdded](/tasks/wait-for-gameplay-tag-added) and [WaitForGameplayTagRemoved](/tasks/wait-for-gameplay-tag-removed)
  Keeps the task active until the requested gameplay tag change occurs.

- GAS: [ApplyGameplayEffect](/tasks/apply-gameplay-effect-to-self) and [ApplyGameplayEffectToTarget](/tasks/apply-gameplay-effect-to-target)
  Applies gameplay effects through the Gameplay Ability System.

- GAS: [TryActivateAbilityByClass](/tasks/try-activate-ability-by-class)
  Tries to activate an ability by class and keeps the task active until the ability completes.

- GAS: [SendGameplayEventToActor](/tasks/send-gameplay-event-to-actor)
  Sends GAS gameplay events to an actor.

### Property Functions

- [GetRootComponent](/property-functions/get-root-component)
  Gets the root component of an actor.

- [CallPureFunction](/property-functions/call-pure-function)
  Accesses any Blueprint-exposed pure function from a property function.

- [Floating point math operations](/property-functions/math-float) and [vector math operations](/property-functions/math-vector)
  Includes reusable math property functions for float and vector calculations.

- GAS: [GetFloatAttribute](/property-functions/get-float-attribute)
  Reads a float gameplay attribute through GAS.

### Conditions

- GAS: [HasMatchingGameplayTag](/conditions/has-matching-gameplay-tag), [HasAllMatchingGameplayTags](/conditions/has-all-matching-gameplay-tags), [HasAnyMatchingGameplayTags](/conditions/has-any-matching-gameplay-tags), and [MatchesGameplayTagQuery](/conditions/matches-gameplay-tag-query)
  Gameplay tag conditions for GAS-driven StateTree transitions and selection.

### Components

- [PerceptionEventForwarder](/components/perception-event-forwarder)
  Forwards all events from AI Perception components into StateTree components on the same actor.

- [GASEventForwarder](/components/gas-event-forwarder)
  Forwards GAS events into StateTree components on the same actor.
