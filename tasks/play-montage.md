---
title: Play Montage
---

# Play Montage

**Plugin:** StateTreeToolsCore
**Category:** Animation

Plays an animation montage on a Skeletal Mesh Component and keeps the task running until the montage ends. Output delegate dispatchers fire for each montage lifecycle event — Completed, Interrupted, BlendOut, and BlendedIn — so downstream states or transitions can react to each phase.

---

## Configuration

### Actor *(input)*
Bind this to the actor whose Skeletal Mesh Component you want to animate. The component is resolved automatically based on the Setup.

### Setup
Editor-only helper that stores the actor class and the name of the Skeletal Mesh Component to use. The actor class is auto-populated from the Actor binding; the component picker filters to `USkeletalMeshComponent`.

### Montage To Play
The `UAnimMontage` asset to play.

### Play Rate
Playback speed multiplier. Default is `1.0`.

### Start Position
Time offset in seconds at which playback begins within the montage. Default is `0.0`.

### Start Section
The montage section to jump to when playback starts. Leave as `None` to start from the beginning.

### Stop All Montages
When enabled, all other montages playing on the same Anim Instance are stopped before this one starts. Default is `true`.

### Stop Montage On Exit
When enabled the montage is stopped and blended out when the task exits (e.g. because a higher-priority transition fired). Default is `true`. When disabled the montage continues playing after the state exits.

### Interruption Means Failure
When enabled the task completes with **Failed** status if the montage is interrupted. Default is `false`.

### On Completed / On Completed Event
Fires when the montage plays through to its natural end. Bind the `FStateTreeDelegateDispatcher` output to other parts of the tree, or configure the `OutputEventAction` to dispatch a StateTree event automatically.

### On Interrupted / On Interrupted Event
Fires when the montage is interrupted (for example by another montage). Configure the `OutputEventAction` to dispatch a StateTree event if needed.

### On Blend Out / On Blend Out Event
Fires when the montage begins blending out. Configure the `OutputEventAction` to dispatch a StateTree event if needed.

### On Blended In / On Blended In Event
Fires when the montage finishes blending in and is fully active. Configure the `OutputEventAction` to dispatch a StateTree event if needed.

---

## Error Handling

If the Actor is invalid, the Skeletal Mesh Component is not found, or the montage cannot be played, the task will fail. The task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`.

[← Back to Animation](/tasks/animation) · [← Back to home](/)
