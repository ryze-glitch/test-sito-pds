## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-27 - Remove Hardcoded Border Radius on Global Focus Visible

**Learning:** When applying a hardcoded `border-radius` (like `4px`) directly to global `:focus-visible` states (e.g., `a:focus-visible, button:focus-visible`), it forcibly overrides the natural shape of intrinsically rounded elements (like a `border-radius: 999px` pill button). This causes the physical element to abruptly morph into a square when receiving keyboard focus, rather than allowing the browser's native outline to smoothly contour the button.

**Action:** Remove hardcoded `border-radius` properties from global focus states. Rely on the browser's default behavior, which naturally curves the `outline` to match the element's base geometry. If a custom focus indicator requires a specific shape, scope it strictly to the component rather than applying it globally.
