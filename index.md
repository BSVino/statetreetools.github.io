---
title: StateTree Tools
---

# StateTree Tools

A plugin for Unreal Engine 5 that extends the StateTree system with ready-made tasks, components, and utilities — so you can build AI and gameplay logic faster without writing custom C++.

---

## [Getting Started](/getting-started)

Install the plugin, enable it in your project, and set up your first StateTree using StateTree Tools tasks.

---

## [Showcase](/showcase)

Examples of what you can build with StateTree Tools — patrol AI, perception-driven behaviour, ability-driven state machines, and more.

---

## Tasks

Tasks run when a state is entered or exited and can keep the state alive while they do work.

| Category | Description |
|----------|-------------|
| [Audio](/tasks/audio) | Play and stop sounds on actors |
| [Animation](/tasks/animation) | Trigger and control animation montages |
| [Debug](/tasks/debug) | Draw debug shapes; flush debug lines and strings |
| [Niagara](/tasks/niagara) | Spawn and manage Niagara particle systems |
| [Navigation](/tasks/navigation) | Find random reachable points for patrol and wandering |
| [Gameplay \| Actions](/tasks/actions) | Drive async Blueprint logic from a StateTree state |
| [Gameplay \| StateTree](/tasks/statetree) | Send events with typed payloads to StateTree components |
| [Utilities \| Events](/tasks/events) | Call Blueprint events and dispatchers on actors by name |
| [Utilities \| Properties](/tasks/properties) | Set actor and component properties by name |
| [Abilities](/tasks/abilities) | Activate GAS abilities and send gameplay events |

---

## Property Functions

> **Requires UE 5.5 or later.** Property functions are not available in UE 5.4.

Property functions compute a value each time a binding is evaluated.

| Category | Description |
|----------|-------------|
| [Components](/property-functions/components) | Get root component and other component accessors |
| [Math \| Float](/property-functions/math-float) | Arithmetic, comparisons, trigonometry, and general float math |
| [Math \| Vector](/property-functions/math-vector) | Vector arithmetic, measurement, and conversion |
| [Utilities](/property-functions/utilities) | String conversion and general value utilities |
| [Call Pure Function](/property-functions/call-pure-function) | Call a BlueprintPure function and expose its return value as a binding |
| [Gameplay Attributes](/property-functions/gameplay-attributes) | Read GAS float attributes from an actor's Ability System Component |

---

## Conditions

Conditions test a value and return true or false, used in transitions and state selection.

| Category | Description |
|----------|-------------|
| [Gameplay Tags](/conditions/gameplay-tags) | Check gameplay tag state on an actor's Ability System Component |

---

## Components

| Component | Description |
|-----------|-------------|
| [Perception Event Forwarder](/components/perception-event-forwarder) | Forwards AI perception events into the StateTree event system |
| [GAS Event Forwarder](/components/gas-event-forwarder) | Forwards GAS gameplay events and tag changes into the StateTree event system |
