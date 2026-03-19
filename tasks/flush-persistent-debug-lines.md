---
title: Flush Persistent Debug Lines
---

# Flush Persistent Debug Lines

**Plugin:** StateTreeToolsCore
**Category:** Debug

Calls `FlushPersistentDebugLines` on the world to remove all persistent debug geometry that has been drawn with a persistent lifetime. Useful for cleaning up lingering debug visuals at defined state transitions.

---

## Configuration

This task has no geometry parameters. All fields below control when the flush is executed.

---

## When to Fire

By default the flush happens when the state is **entered**. You can also trigger it on **exit**, with separate toggles for which exit reasons fire it (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
