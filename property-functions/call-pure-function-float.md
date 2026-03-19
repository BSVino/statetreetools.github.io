---
title: Call Pure Function (Float)
---

# Call Pure Function (Float)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Float

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `float` output. This variant accepts both C++ `float` functions and Blueprint `float`/`double` functions. Use this to feed any pure Blueprint computation — a health ratio, a distance, a blend weight — into the StateTree binding system.

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
The `BlueprintPure` function to call. Only functions with a return value compatible with `float` or `double` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `float` result returned by the called function.

---

[← Back to Call Pure Function](/property-functions/call-pure-function) · [← Back to home](/)
