---
title: StateTree Tools
---

# StateTree Tools

A plugin for Unreal Engine 5 that extends the StateTree system with ready-made tasks, components, and utilities — so you can build AI and gameplay logic faster without writing custom C++.

---

## [Getting Started](https://bsvino.github.io/statetreetools.github.io/getting-started)

Install the plugin, enable it in your project, and set up your first StateTree using StateTree Tools tasks.

---

## [Showcase](https://bsvino.github.io/statetreetools.github.io/showcase)

Examples of what you can build with StateTree Tools — patrol AI, perception-driven behaviour, ability-driven state machines, and more.

---

## Tasks

Tasks run when a state is entered or exited and can keep the state alive while they do work.

| Category | Description |
|----------|-------------|
| [Audio](https://bsvino.github.io/statetreetools.github.io/tasks/audio) | Play and stop sounds on actors |
| [Animation](https://bsvino.github.io/statetreetools.github.io/tasks/animation) | Trigger and control animation montages |
| [Debug](https://bsvino.github.io/statetreetools.github.io/tasks/debug) | Draw debug shapes; flush debug lines and strings |
| [Niagara](https://bsvino.github.io/statetreetools.github.io/tasks/niagara) | Spawn and manage Niagara particle systems |
| [Navigation](https://bsvino.github.io/statetreetools.github.io/tasks/navigation) | Find random reachable points for patrol and wandering |
| [Gameplay \| Actions](https://bsvino.github.io/statetreetools.github.io/tasks/actions) | Drive async Blueprint logic from a StateTree state |
| [Gameplay \| StateTree](https://bsvino.github.io/statetreetools.github.io/tasks/statetree) | Send events with typed payloads to StateTree components |
| [Utilities \| Events](https://bsvino.github.io/statetreetools.github.io/tasks/events) | Call Blueprint events and dispatchers on actors by name |
| [Utilities \| Properties](https://bsvino.github.io/statetreetools.github.io/tasks/properties) | Set actor and component properties by name |
| [Abilities](https://bsvino.github.io/statetreetools.github.io/tasks/abilities) | Activate GAS abilities and send gameplay events |

---

## Property Functions

Property functions compute a value each time a binding is evaluated.

| Category | Description |
|----------|-------------|
| [Components](https://bsvino.github.io/statetreetools.github.io/tasks/components) | Get root component and other component accessors |
| [Utilities](https://bsvino.github.io/statetreetools.github.io/tasks/utilities) | Math, string conversion, and general value helpers |

---

## Conditions

Conditions test a value and return true or false, used in transitions and state selection.

| Category | Description |
|----------|-------------|
| [Abilities](https://bsvino.github.io/statetreetools.github.io/tasks/abilities) | Check gameplay tags on an actor's Ability System Component |

---

## Components

| Component | Description |
|-----------|-------------|
| [Perception Event Forwarder](https://bsvino.github.io/statetreetools.github.io/components/perception-event-forwarder) | Forwards AI perception events into the StateTree event system |
| [GAS Event Forwarder](https://bsvino.github.io/statetreetools.github.io/components/gas-event-forwarder) | Forwards GAS gameplay events and tag changes into the StateTree event system |
