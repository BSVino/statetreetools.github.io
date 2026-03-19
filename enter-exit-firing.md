---
title: Enter / Exit Firing
---

# Enter / Exit Firing

Many StateTree Tools tasks can fire their action when a state is **entered**, when it is **exited**, or on **both**. This is controlled by a pair of options on the task: **Call On Enter State** and **Call On Exit State** (the exact names vary by task).

---

## Firing on Enter

When **Call On Enter State** is enabled, the action fires immediately as the state is entered. If exit firing is not also enabled, the task completes right away and does not hold the state open.

This is the default for most tasks and is the right choice for fire-and-forget actions — playing a sound, triggering an animation, sending an event.

## Firing on Exit

When **Call On Exit State** is enabled, the task stays **Running** for as long as the state is active, then fires the action as the state is leaving. Because the task holds a Running status, it will appear as an active task in the StateTree debugger for the duration of the state.

When only exit firing is enabled, nothing happens on enter — the task simply waits.

### Exit Conditions

When exit firing is on, three additional options let you control *which* kind of exit triggers the action:

| Option | Default | Description |
|--------|---------|-------------|
| On Exit — Stopped | Off | Fire when the state is interrupted or the StateTree is stopped externally |
| On Exit — Succeeded | On | Fire when the state exits because it succeeded normally |
| On Exit — Failed | Off | Fire when the state exits because it failed |

You can enable any combination of these. If none are enabled, the action will never fire on exit — the editor will warn you about this when the StateTree is compiled.

## Firing on Both

When both enter and exit firing are enabled, the action fires twice: once on enter and once on exit (subject to the exit conditions above). The task stays Running between the two.

---

## At a Glance

The task's label in the StateTree editor reflects the current setting:

| Label | Meaning |
|-------|---------|
| **(Enter)** | Fires on enter only |
| **(Exit)** | Fires on exit only |
| **(Enter\|Exit)** | Fires on both |

---

## Compile Validation

If a task is configured such that it would never fire — enter is off, and either exit is also off or all exit conditions are disabled — the StateTree editor will report a compile error on that task.
