---
title: Changelist
---

# Changelist

## Version 2.0 (Development Branch)

### Components

- Primitive Event Forwarder
  Forwards primitive component events into StateTree components on the same actor, similar to how the existing perception and GAS forwarders work.
  Includes support for begin/end overlap, hit, wake/sleep, physics state changed, cursor over, click/release, and touch begin/end/enter/leave events.
  Sends typed `FStateTreeEvent` payloads tagged under the `StateTreeTools.Events.Primitive.*` namespace.

### Editor and Compile Validation Improvements

- Optional GAS sub-plugin loading
  StateTree Tools Gameplay Ability System is now optional instead of always-on.
  The GAS sub-plugin only becomes available and loads when Unreal's built-in Gameplay Abilities plugin is enabled; otherwise StateTree Tools Core still loads normally without GAS-specific nodes.

- Compile-time validation for selected events, delegates, properties, and functions
  Nodes that let you choose actor events, delegates, properties, and pure functions now validate those selections during compile.
  This catches cases where a Blueprint event, delegate, function, or property was deleted or renamed after the node was configured, instead of silently leaving an invalid selection behind.

## Version 1.0

### Tasks

- CallActorEvent
  Calls any event or non-pure function on any actor or its components.

- SetActorProperty
  Sets any property on any actor or its components.

- CallActorDelegate
  Calls any delegate on any actor or its components.

- StartActionAndWait
  Calls an event on an actor or component, then keeps the task active until the event calls the `Finish Action` Blueprint node.

- PlayMontage
  Plays animation montages from StateTree tasks.

- PlaySoundAtLocation, SpawnSoundAtLocation, PlaySound2D, SpawnSound2D
  Audio playback tasks for world-space and 2D sounds.

- DrawDebugLine, DrawDebugPoint, DrawDebugDirectionalArrow, DrawDebugBox, DrawDebugSphere, and more
  Includes the full set of debug draw helpers, plus `FlushPersistentDebugLines` and `FlushDebugStrings`.

- GetRandomReachablePointInRadius
  Finds a random reachable navigation point for wandering and patrol behaviors.

- SpawnSystemAttached and SpawnSystemAtLocation
  Niagara spawning tasks for attached and world-space effects.

- SendStateTreeEvent
  Sends a StateTree event from a StateTree task.

- GAS: WaitForGameplayTagAdded and WaitForGameplayTagRemoved
  Keeps the task active until the requested gameplay tag change occurs.

- GAS: ApplyGameplayEffect and ApplyGameplayEffectToTarget
  Applies gameplay effects through the Gameplay Ability System.

- GAS: TryActivateAbilityByClass
  Tries to activate an ability by class and keeps the task active until the ability completes.

- GAS: SendGameplayEventToActor
  Sends GAS gameplay events to an actor.

### Property Functions

- GetRootComponent
  Gets the root component of an actor.

- CallPureFunction
  Accesses any Blueprint-exposed pure function from a property function.

- Floating point and vector math operations
  Includes reusable math property functions for float and vector calculations.

- GAS: GetFloatAttribute
  Reads a float gameplay attribute through GAS.

### Conditions

- GAS: HasMatchingGameplayTag, HasAllMatchingGameplayTags, HasAnyMatchingGameplayTags, and MatchesGameplayTagQuery
  Gameplay tag conditions for GAS-driven StateTree transitions and selection.

### Components

- PerceptionEventForwarder
  Forwards all events from AI Perception components into StateTree components on the same actor.

- GASEventForwarder
  Forwards GAS events into StateTree components on the same actor.
