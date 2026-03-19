---
title: StateTree Tools
---

# StateTree Tools

A plugin for Unreal Engine 5 that extends the StateTree system with ready-made tasks, components, and utilities — so you can build AI and gameplay logic faster without writing custom C++.

---

## [Getting Started](getting-started)

Install the plugin, enable it in your project, and set up your first StateTree using StateTree Tools tasks.

---

## [Showcase](showcase)

Examples of what you can build with StateTree Tools — patrol AI, perception-driven behaviour, ability-driven state machines, and more.

---

## Tasks

Tasks are the building blocks of your StateTree states. StateTree Tools provides tasks across several categories:

| Category | Description |
|----------|-------------|
| [Audio](tasks/audio) | Play and stop sounds on actors |
| [Animation](tasks/animation) | Trigger and control animation montages |
| [Components](tasks/components) | Enable, disable, and toggle component visibility |
| [Debug](tasks/debug) | Draw debug shapes; flush debug lines and strings |
| [Niagara](tasks/niagara) | Spawn and manage Niagara particle systems |
| [Navigation](tasks/navigation) | Find random reachable points for patrol and wandering |
| [Gameplay \| StateTree](tasks/statetree) | Send events with typed payloads to StateTree components |
| [Utilities \| Events](tasks/events) | Call Blueprint events and dispatchers on actors by name |
| [Utilities \| Properties](tasks/properties) | Set actor and component properties by name |
| [Utilities](tasks/utilities) | String, math, and general helpers |
| [Abilities](tasks/abilities) | Activate GAS abilities and send gameplay events |

---

## Components

| Component | Description |
|-----------|-------------|
| [Perception Event Forwarder](components/perception-event-forwarder) | Forwards AI perception events into the StateTree event system |
| [GAS Event Forwarder](components/gas-event-forwarder) | Forwards GAS gameplay events and tag changes into the StateTree event system |
