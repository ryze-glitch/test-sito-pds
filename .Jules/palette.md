## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-23 - Dynamic Focus Rings
**Learning:** Hardcoding a static `border-radius` (e.g., `4px`) on global `:focus-visible` pseudo-classes breaks the visual design of inherently rounded elements (like pill-shaped buttons), forcing them into a rectangular outline. Removing the hardcoded radius allows modern browsers to automatically calculate the outline to match the element's base border-radius.
**Action:** When designing global focus states, rely only on `outline`, `outline-offset`, and `outline-color` (or `box-shadow` if `outline` isn't supported). Never hardcode `border-radius` on focus pseudo-classes to ensure focus rings gracefully adapt to any component's shape.
