---
title: Call Pure Function
---

# Call Pure Function

Property functions for calling `BlueprintPure` functions on actors or their components and exposing the return value as a bindable output. Each variant covers a different output type; all share the same Setup configuration.

Every variant provides a custom details panel. Set **ActorClass** to populate a searchable dropdown of pure functions whose return type matches the variant. Set **ComponentName** if the function lives on a component rather than the actor directly.

| Property Function | Description |
|-------------------|-------------|
| [Call Pure Function (Bool)](/property-functions/call-pure-function-bool) | Return value exposed as `bool` |
| [Call Pure Function (Actor)](/property-functions/call-pure-function-actor) | Return value exposed as `Actor` reference |
| [Call Pure Function (Byte)](/property-functions/call-pure-function-byte) | Return value exposed as `byte` |
| [Call Pure Function (Int)](/property-functions/call-pure-function-int) | Return value exposed as `int32` |
| [Call Pure Function (Int64)](/property-functions/call-pure-function-int64) | Return value exposed as `int64` |
| [Call Pure Function (Float)](/property-functions/call-pure-function-float) | Return value exposed as `float` |
| [Call Pure Function (Double)](/property-functions/call-pure-function-double) | Return value exposed as `double` |
| [Call Pure Function (Name)](/property-functions/call-pure-function-name) | Return value exposed as `FName` |
| [Call Pure Function (String)](/property-functions/call-pure-function-string) | Return value exposed as `FString` |
| [Call Pure Function (Text)](/property-functions/call-pure-function-text) | Return value exposed as `FText` |
| [Call Pure Function (Vector)](/property-functions/call-pure-function-vector) | Return value exposed as `FVector` |
| [Call Pure Function (Rotator)](/property-functions/call-pure-function-rotator) | Return value exposed as `FRotator` |
| [Call Pure Function (Transform)](/property-functions/call-pure-function-transform) | Return value exposed as `FTransform` |

[← Back to home](/)
