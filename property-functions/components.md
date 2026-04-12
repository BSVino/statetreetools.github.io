---
title: Components
---

# Components

Property functions for accessing actor components. **Requires UE 5.5+.**

> **UE 5.7 and earlier known issue:** Unreal has a component-binding UI bug that can cause the details panel to continuously refresh when a component property function is bound directly into another node's component input. The workaround is to create a StateTree **parameter** of the component type, bind the property function into that parameter, and then bind the parameter into the target node.

| Property Function | Description |
|-------------------|-------------|
| [Get Root Component](/property-functions/get-root-component) | Get the root scene component of an actor |
| [Get Component By Class](/property-functions/get-component-by-class) | Get the first actor component that matches a class |

[← Back to home](/)