---
title: Getting Started
---

# Getting Started

## Supported Versions

StateTree Tools supports Unreal Engine 5.4, 5.5, and 5.6. Most features are available on all supported versions.

| Feature | UE 5.4 | UE 5.5 | UE 5.6 |
|---------|--------|--------|--------|
| Tasks | ✓ | ✓ | ✓ |
| Conditions | ✓ | ✓ | ✓ |
| Components | ✓ | ✓ | ✓ |
| Property Functions | — | ✓ | ✓ |

---

## Install the plugin

Purchase StateTree Tools on Fab and add it to your engine version from the Epic Games Launcher. The plugin comes with precompiled binaries so no source compilation is needed.

## Enable the plugin

Open your project in Unreal Engine, then go to **Edit → Plugins**. Search for **StateTree Tools** and enable whichever sub-plugins you need:

- **StateTree Tools Core** — tasks, property functions, and components for general use
- **StateTree Tools Gameplay Ability System** — GAS-specific tasks and conditions (requires the Gameplay Abilities plugin)

Restart the editor when prompted.

## Enable dependencies

StateTree Tools Core requires the **GameplayStateTree** plugin. StateTree Tools Gameplay Ability System additionally requires **Gameplay Abilities**. Both are built-in Unreal plugins — enable them in the same Plugins window if they are not already on.

## Start building

Create a StateTree asset (**Content Browser → Add → StateTree**) and add a `StateTreeComponent` to an actor. StateTree Tools nodes will appear in the task, condition, and property function pickers inside the StateTree editor alongside the built-in ones.

[← Back to home](/)
