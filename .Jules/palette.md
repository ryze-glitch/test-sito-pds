## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-10-17 - Avoid Hardcoded Border Radius on Global Focus Visible Styles
**Learning:** Applying a hardcoded `border-radius` (e.g., `4px`) to global `:focus-visible` pseudo-classes overrides the natural shape of inherently rounded elements (like `.nav-login-btn` with `border-radius: 999px`), resulting in mismatched focus outlines with sharp corners on pill-shaped buttons.
**Action:** Let `:focus-visible` inherit the element's base `border-radius` naturally, relying only on `outline`, `outline-offset`, and `box-shadow` for focus visualization. Avoid defining `border-radius` in global focus rules unless specifically styling squared elements that lack an inherent radius.
