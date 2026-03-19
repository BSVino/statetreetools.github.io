---
title: Draw Debug String
---

# Draw Debug String

**Plugin:** StateTreeToolsCore
**Category:** Debug

Draws a debug text string at a world-space location. When **While Task Is Active** is enabled the string is redrawn every tick for as long as the state is active. When disabled the string is drawn once on enter using the **Duration** setting, then the task immediately succeeds.

---

## Configuration

### Text Location
The world-space position where the string is drawn.

### Text
The string to display.

### Test Base Actor *(optional input)*
When bound the string follows this actor's position. Leave unbound to use the fixed **Text Location**.

### Text Color
The color of the text. Default is white.

### While Task Is Active
When enabled the string is redrawn every tick and the task stays running until the state exits. When disabled the string is drawn once on enter.

### Duration
How long the string remains visible in seconds when **While Task Is Active** is off. A value of `-1` uses the engine default.

### Draw Shadow
When enabled a drop shadow is rendered behind the text. Default is `false`.

### Font Scale
Scale multiplier applied to the debug font size. Default is `1.0`.

---

[← Back to Debug](/tasks/debug) · [← Back to home](/)
