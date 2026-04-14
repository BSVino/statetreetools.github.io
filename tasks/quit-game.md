---
title: Quit Game
---

# Quit Game

**Plugin:** StateTreeToolsCore
**Category:** System
**Availability:** StateTree Tools **2.0+**

Calls `QuitGame` — the same function as Unreal's built-in **Quit Game** Blueprint node. Fire-and-forget; the task always succeeds immediately after calling it.

---

## Configuration

### Specific Player *(input, optional)*
The player controller to quit for. Leave unbound to quit the game for all players (the typical case).

### Quit Preference
How the game should quit:

| Value | Behaviour |
|-------|-----------|
| **Quit** | Exits the process immediately. |
| **Background** | Moves the application to the background instead of fully closing (mobile platforms). |

### Ignore Platform Restrictions
When enabled, forces the quit even on platforms that normally disallow it (e.g. consoles). Leave disabled for standard behaviour.

---

[← Back to System](/tasks/system) · [← Back to home](/)
