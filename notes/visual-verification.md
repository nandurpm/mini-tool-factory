# Local visual verification

The generated workbench at `http://127.0.0.1:4092` displayed the safe-generation boundary, a prompt field, four deterministic template choices, a structured JSON specification panel, export control, and a controlled runnable form. Its default balanced three-phase real-power template exposed line-to-line voltage, line current, and power factor with explicit units and produced `5.54256258422 kW` for `400 V`, `10 A`, and `0.8`.

Selecting the Celsius-to-Fahrenheit template replaced the form and structured specification without evaluating generated code. The one-field temperature preview showed the formula `°F = °C × 9 ÷ 5 + 32` and returned `77 °F` for the stated `25 °C` example.

A `390 × 844` narrow-viewport capture saved as `notes/screenshots/mobile-390.png` verified that the hero, safety notice, prompt, generation/export controls, and template cards stack in a readable single-column layout without horizontal clipping. The controlled preview form uses the same responsive breakpoint.
