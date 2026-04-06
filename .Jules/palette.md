## 2024-04-06 - Pure CSS Dropdowns Need `:focus-within`
**Learning:** Pure CSS dropdown menus that rely solely on `:hover` for visibility become completely inaccessible to keyboard users tabbing through the navigation. The elements inside remain hidden but focusable, breaking tab order predictability.
**Action:** Always append `:focus-within` to the same CSS rule that triggers visibility on `:hover` for dropdowns, and ensure all interactive elements (`a`, `button`) have a visible focus outline (`:focus-visible`).
