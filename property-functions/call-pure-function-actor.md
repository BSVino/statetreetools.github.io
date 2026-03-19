---
title: Call Pure Function (Actor)
---

# Call Pure Function (Actor)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Actor

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `Actor` output. Use this to retrieve actor references computed by Blueprint logic — for example fetching the current target, the nearest ally, or any actor derived from a pure calculation.

The Setup section provides a custom details panel: select an **ActorClass** to populate a dropdown of compatible pure functions, then choose the function and the specific output parameter to read.

---

## Configuration

### Actor
The actor instance to call the function on. Bind this to the actor you want to query.

### Setup

#### ActorClass
The class of actor used to populate the function picker. Set this to the class that defines the function you want to call.

#### ComponentName
Optional. If set, the function is called on the named component of the actor rather than the actor itself.

#### FunctionName
The `BlueprintPure` function to call. Only functions with a return value compatible with `Actor` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `Actor` reference returned by the called function.

---

[← Back to Call Pure Function](/property-functions/call-pure-function) · [← Back to home](/)
