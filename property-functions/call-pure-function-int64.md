---
title: Call Pure Function (Int64)
---

# Call Pure Function (Int64)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| Integer

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `int64` output. Use this when the function returns a large integer that exceeds the range of a standard 32-bit integer — for example a timestamp, a unique ID, or an accumulated score.

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
The `BlueprintPure` function to call. Only functions with a return value compatible with `int64` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `int64` result returned by the called function.

---

[← Back to Call Pure Function](/property-functions/call-pure-function) · [← Back to home](/)
