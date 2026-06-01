## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-06-01 - Focus Visible Border Radius Override
**Learning:** Applying a hardcoded `border-radius` directly to global `:focus-visible` pseudo-classes (e.g., `a:focus-visible, button:focus-visible`) overrides the natural shape of inherently rounded elements like pill buttons. This forces a jarring visual transition from a curved pill to a rounded square when the element receives keyboard focus.
**Action:** Remove hardcoded `border-radius` rules from global `:focus-visible` selectors to ensure focus rings gracefully inherit the element's natural geometry while maintaining accessibility.
