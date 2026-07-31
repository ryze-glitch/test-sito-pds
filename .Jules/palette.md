## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-07-31 - [Avoid hardcoding border-radius in global focus-visible states]
**Learning:** Hardcoding a specific `border-radius` (like `4px`) in a global CSS reset for `:focus-visible` states inadvertently overrides the natural border-radius of uniquely shaped components, such as fully rounded "pill" buttons. This causes the outline and the element itself to appear broken or boxy during keyboard navigation.
**Action:** Let `:focus-visible` naturally inherit the target element's base `border-radius`. Rely only on `outline`, `outline-offset`, and optionally `box-shadow` to style the focus indicator globally.
