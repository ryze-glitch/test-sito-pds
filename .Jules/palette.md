## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## $(date +%Y-%m-%d) - Focus Ring Border Radius Conflict
**Learning:** Hardcoding a specific `border-radius` (like `4px`) exclusively inside a `:focus-visible` pseudo-class overrides the element's natural geometry when focused. This is particularly noticeable on inherently round or pill-shaped buttons (like `.nav-login-btn`), where focusing causes the element to visually warp into a square/rectangle.
**Action:** Always let `:focus-visible` inherit the element's base `border-radius` naturally, relying only on `outline`, `outline-offset`, and `box-shadow` for focus visualization. Avoid setting border geometry dynamically on focus.
