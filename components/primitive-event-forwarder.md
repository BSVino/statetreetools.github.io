---
title: Primitive Event Forwarder
---

# Primitive Event Forwarder

**Plugin:** StateTreeToolsCore
**Class:** `UPrimitiveEventForwarder`
**Available since:** StateTree Tools 2.0

Bridges the primitive component collision and interaction system with the StateTree event system. Add this component to any actor that has a `UPrimitiveComponent` (e.g. a sphere collider, static mesh, or skeletal mesh). At runtime it binds to that primitive's delegates and fires StateTree events for overlaps, hits, physics state changes, cursor interaction, and touch input — so your StateTree can react to these without any custom C++.

---

## Configuration

### Primitive Component
The `UPrimitiveComponent` on the owner actor to watch. Select from the dropdown — only primitive components present on the actor are listed. **This must be set**; leaving it as `None` is a Blueprint compile error.

### State Tree Component Name
The name of the `UStateTreeComponent` on the owner to send events to. Leave as `None` (default) to broadcast to every StateTree component on the actor. Set this if the actor has multiple StateTree components and you want to target only one.

---

## Events Fired

All events are sent to the `UStateTreeComponent`(s) on the same actor (filtered by **State Tree Component Name** if set). Every payload includes a `SourceComponent` field pointing to the primitive that fired the event.

### Overlap

#### `StateTreeTools.Events.Primitive.BeginOverlap`
**Payload:** `FPrimitiveBeginOverlapPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `OtherActor` | `AActor*` | The other actor involved in the overlap |
| `OtherComp` | `UPrimitiveComponent*` | The other component involved |
| `OtherBodyIndex` | `int32` | Body index on the other component |
| `bFromSweep` | `bool` | Whether the overlap was triggered by a sweep |
| `SweepResult` | `FHitResult` | Hit result if triggered by a sweep |

#### `StateTreeTools.Events.Primitive.EndOverlap`
**Payload:** `FPrimitiveEndOverlapPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `OtherActor` | `AActor*` | The other actor |
| `OtherComp` | `UPrimitiveComponent*` | The other component |
| `OtherBodyIndex` | `int32` | Body index on the other component |

### Hit

#### `StateTreeTools.Events.Primitive.Hit`
**Payload:** `FPrimitiveHitPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `OtherActor` | `AActor*` | The actor that was hit |
| `OtherComp` | `UPrimitiveComponent*` | The component that was hit |
| `NormalImpulse` | `FVector` | The normal impulse applied at the hit |
| `Hit` | `FHitResult` | Full hit result |

### Physics

#### `StateTreeTools.Events.Primitive.Wake`
**Payload:** `FPrimitiveWakePayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `BoneName` | `FName` | The bone that woke (skeletal meshes) |

#### `StateTreeTools.Events.Primitive.Sleep`
**Payload:** `FPrimitiveSleepPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `BoneName` | `FName` | The bone that went to sleep (skeletal meshes) |

#### `StateTreeTools.Events.Primitive.PhysicsStateChanged`
**Payload:** `FPrimitivePhysicsStateChangedPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `StateChange` | `EComponentPhysicsStateChange` | Whether physics was `Created` or `Destroyed` |

### Cursor

#### `StateTreeTools.Events.Primitive.BeginCursorOver`
**Payload:** `FPrimitiveBeginCursorOverPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |

#### `StateTreeTools.Events.Primitive.EndCursorOver`
**Payload:** `FPrimitiveEndCursorOverPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |

### Click / Release

#### `StateTreeTools.Events.Primitive.Clicked`
**Payload:** `FPrimitiveClickedPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `ButtonPressed` | `FKey` | The mouse button that was pressed |

#### `StateTreeTools.Events.Primitive.Released`
**Payload:** `FPrimitiveReleasedPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `ButtonReleased` | `FKey` | The mouse button that was released |

### Touch

#### `StateTreeTools.Events.Primitive.InputTouchBegin`
**Payload:** `FPrimitiveInputTouchBeginPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `FingerIndex` | `ETouchIndex::Type` | The touch finger index |

#### `StateTreeTools.Events.Primitive.InputTouchEnd`
**Payload:** `FPrimitiveInputTouchEndPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `FingerIndex` | `ETouchIndex::Type` | The touch finger index |

#### `StateTreeTools.Events.Primitive.InputTouchEnter`
**Payload:** `FPrimitiveInputTouchEnterPayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `FingerIndex` | `ETouchIndex::Type` | The touch finger index |

#### `StateTreeTools.Events.Primitive.InputTouchLeave`
**Payload:** `FPrimitiveInputTouchLeavePayload`

| Field | Type | Description |
|-------|------|-------------|
| `SourceComponent` | `UPrimitiveComponent*` | The watched primitive |
| `FingerIndex` | `ETouchIndex::Type` | The touch finger index |

---

## Setup

1. Add `UPrimitiveEventForwarder` to your actor.
2. In the **Primitive Component** dropdown, select the primitive to watch.
3. In your StateTree, add a transition with **On Event** set to the desired tag (e.g. `StateTreeTools.Events.Primitive.BeginOverlap`).
4. In the transition's **Payload Struct** field, select the matching payload type (e.g. `FPrimitiveBeginOverlapPayload`). If the payload type is wrong or left unset, the event will not match and the transition will never fire.
5. Bind payload fields using the StateTree binding system.

The component logs a warning and becomes inactive at runtime if the named primitive is not found on the owner.

---

[← Back to home](/)
