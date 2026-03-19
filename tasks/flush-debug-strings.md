---
title: Flush Debug Strings
---

# Flush Debug Strings

**Plugin:** StateTreeToolsCore
**Category:** Debug

Calls `FlushDebugStrings` on the world to remove all debug strings that have been drawn with `DrawDebugString`. Useful for clearing stale on-screen text at defined state transitions.

---

## Configuration

This task has no geometry parameters. All fields below control when the flush is executed.

---

## When to Fire

By default the flush happens when the state is **entered**. You can also trigger it on **exit**, with separate toggles for which exit reasons fire it (Stopped, Succeeded, or Failed). See [Enter / Exit Firing](/enter-exit-firing) for a full explanation.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
