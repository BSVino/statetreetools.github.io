---
title: Play Sound At Location
---

# Play Sound At Location

**Plugin:** StateTreeToolsCore
**Category:** Audio

Plays a spatialized sound at a world-space location when the state is entered. The task fires once and immediately succeeds — it does not wait for the sound to finish. Use [Spawn Sound At Location](/tasks/spawn-sound-at-location) instead if you need to track playback or hold a reference to the audio component.

---

## Configuration

### Sound
The sound asset to play.

### Sound Attenuation *(optional)*
An attenuation settings asset that controls how the sound falls off with distance. Leave empty to use the sound's default attenuation settings.

### Sound Concurrency *(optional)*
A concurrency settings asset that controls how this sound behaves when multiple instances are requested. Leave empty to use the sound's default concurrency rules.

### Initial Params *(optional)*
Advanced initial active sound parameters. Leave empty in most cases.

### Location
The world-space position at which the sound is played.

### Volume Multiplier
Scales the sound's base volume. Default is `1.0`.

### Pitch Multiplier
Scales the sound's base pitch. Default is `1.0`.

### Start Time
Playback start offset in seconds. Default is `0.0`.

---

## Error Handling

If the Sound asset is not set the task will fail at compile time. The task inherits **Error Means Failure** from `FStateTreeTools_TaskCommon`.

[← Back to Audio](/tasks/audio) · [← Back to home](/)
