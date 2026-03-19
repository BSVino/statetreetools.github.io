---
title: Spawn System Attached
---

# Spawn System Attached

**Plugin:** StateTreeToolsCore
**Category:** Niagara

Spawns a Niagara particle system attached to a scene component or actor when the state is entered. The task remains running until the system finishes on its own, then succeeds. On state exit the system is either destroyed immediately or deactivated depending on the **Destroy On Exit** setting. The spawned component is written to the **Spawned Niagara Component** output.

> **Note:** There is a known issue with using property functions to supply `AttachToComponent` directly. Until it is resolved, use the **Attach To Actor** and **Attach To Actor Component Name** fields together as an alternative.

---

## Configuration

### Attach To Component *(optional input)*
The `USceneComponent` to attach to. Due to a known issue with property functions, prefer using **Attach To Actor** + **Attach To Actor Component Name** instead.

### Attach To Actor *(optional input)*
The actor whose component the system should attach to.

### Attach To Actor Component Name
The name of the component on **Attach To Actor** to attach to. Leave empty to attach to the actor's root component.

### Attach Point Name
The socket or bone name on the target component to attach to. Leave empty to attach to the component's origin.

### System Template
The `UNiagaraSystem` asset to spawn.

### Location
Offset from the attachment point.

### Rotation
Rotation offset from the attachment point.

### Location Type
Controls how Location and Rotation are interpreted relative to the attachment. Default is `KeepRelativeOffset`.

### Auto Destroy
When enabled the Niagara component destroys itself after the simulation ends. Default is `true`.

### Auto Activate
When enabled the system activates immediately on spawn. Default is `true`.

### Pooling Method
Controls whether and how the Niagara Component Pool is used for this spawn. Default is `None` (no pooling).

### Pre Cull Check
When enabled the engine performs a pre-cull visibility check before spawning. Default is `true`.

### Destroy On Exit
When enabled the system is destroyed immediately when the state exits, killing all existing particles at once. When disabled the system is deactivated and existing particles are allowed to linger until they die naturally. Default is `false`.

### Spawned Niagara Component *(output)*
Receives the `UNiagaraComponent` that was created. Bind downstream tasks or conditions to this output to control or query the running system.

---

## Error Handling

If the System Template is not set the task will fail at compile time. The task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`.

[← Back to Niagara](/tasks/niagara) · [← Back to home](/)
