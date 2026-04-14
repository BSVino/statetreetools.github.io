---
title: Get Actor Of Class
---

# Get Actor Of Class

**Plugin:** StateTreeToolsCore
**Category:** Actor
**Availability:** StateTree Tools **2.0+**

Finds and returns the first actor of the given class in the world. Wraps the Blueprint **Get Actor Of Class** node. The result is written to an output binding so other tasks and conditions in the same state can reference it.

---

## Configuration

### Actor Class
The class to search for. Required — the task fails if this is not set.

### Out Actor
Output. The first actor found in the world that is of (or derived from) **Actor Class**. If no matching actor exists the output is None; this is not treated as an error.

---

## Error Handling

The task fails only if **Actor Class** is not set. Finding no actor in the world is not an error — **Out Actor** will simply be None. You can control whether a failure causes the task to return **Failed** or **Succeeded** using the **Error Means Failure** option.

---

[← Back to Actor](/tasks/actor) · [← Back to home](/)
