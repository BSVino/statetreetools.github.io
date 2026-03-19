---
title: Spawn System at Location
---

# Spawn System at Location

**Plugin:** StateTreeToolsCore
**Category:** Niagara

Spawns a Niagara particle system at a world-space location when the state is entered. The task remains running until the system finishes on its own, then succeeds. On state exit the system is either destroyed immediately or deactivated (letting existing particles linger) depending on the **Destroy On Exit** setting. The spawned component is written to the **Spawned Niagara Component** output.

---

## Configuration

### System Template
The `UNiagaraSystem` asset to spawn.

### Location
The world-space position at which the system is spawned.

### Rotation
The initial world-space rotation of the spawned system.

### Scale
The world-space scale of the spawned system. Default is `(1, 1, 1)`.

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
