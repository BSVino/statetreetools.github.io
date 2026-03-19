---
title: Call Pure Function (Bool)
---

# Call Pure Function (Bool)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Boolean

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `bool` output. Use this to surface any pure Blueprint function's boolean result directly in the StateTree property binding system without writing custom C++.

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
The `BlueprintPure` function to call. Only functions with a return value compatible with `bool` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `bool` result returned by the called function.

---

[← Back to Call Pure Function](/property-functions/call-pure-function) · [← Back to home](/)
