---
title: Call Pure Function (String)
---

# Call Pure Function (String)

**Plugin:** StateTreeToolsCore
**Category:** Utilities \| String

Calls a `BlueprintPure` function on an actor (or one of its components) at runtime and exposes the return value as a bindable `FString` output. Use this to retrieve string results from Blueprint logic — for example a formatted message, a serialized value, or a dynamically computed identifier.

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
The `BlueprintPure` function to call. Only functions with a return value compatible with `FString` are shown in the dropdown.

#### ReturnValueName
The output parameter of the function to read. This is usually `ReturnValue` for single-output functions.

### Value
The `FString` result returned by the called function.

---

[← Back to Call Pure Function](/property-functions/call-pure-function) · [← Back to home](/)
