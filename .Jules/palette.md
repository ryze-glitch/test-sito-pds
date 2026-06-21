## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-06-21 - CSS Focus State Shapes
**Learning:** Hardcoded `border-radius` values in generic global `:focus-visible` pseudo-classes (e.g., `a:focus-visible, button:focus-visible { border-radius: 4px; }`) create UI jank. When focused, uniquely shaped elements like fully rounded pills (`border-radius: 999px`) are forced into a square shape, overriding their natural curve.
**Action:** When creating global focus styles, omit `border-radius` and let the browser's native outline automatically inherit and follow the element's base curvature.
