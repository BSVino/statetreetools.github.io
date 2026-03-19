---
title: Play Sound 2D
---

# Play Sound 2D

**Plugin:** StateTreeToolsCore
**Category:** Audio

Plays a non-spatialized 2D sound when the state is entered. The task fires once and immediately succeeds — it does not wait for the sound to finish. Use [Spawn Sound 2D](/tasks/spawn-sound-2d) instead if you need to track playback or stop the sound when the state exits.

---

## Configuration

### Sound
The sound asset to play.

### Sound Concurrency *(optional)*
A concurrency settings asset that controls how this sound behaves when multiple instances are requested at once (limiting, stealing, etc.). Leave empty to use the sound's default concurrency rules.

### Volume Multiplier
Scales the sound's base volume. Default is `1.0`.

### Pitch Multiplier
Scales the sound's base pitch. Default is `1.0`.

### Start Time
Playback start offset in seconds. Default is `0.0`.

### Owning Actor *(optional)*
The actor that "owns" this sound for the purpose of the audio engine's listener-based culling and concurrency tracking. Leave unbound to play with no owner.

### Is UI Sound
When enabled the sound bypasses the game audio focus rules and always plays. Suitable for menu or HUD sounds. Default is `true`.

---

## Error Handling

If the Sound asset is not set the task will fail at compile time. At runtime the task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`, which controls whether a failure returns **Failed** or **Succeeded**.

[← Back to Audio](/tasks/audio) · [← Back to home](/)
