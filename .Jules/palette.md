## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-09-28 - Focus Styles on Rounded Elements
**Learning:** Hardcoding a strict `border-radius` (like `4px`) on global `:focus-visible` states will override the natural border-radius of inherently rounded or pill-shaped interactive elements (like an oval `.nav-login-btn`), causing the focus outline to clash aggressively with the element's shape.
**Action:** Let `:focus-visible` inherit the element's base `border-radius` naturally instead of hardcoding it globally. Rely only on `outline`, `outline-offset`, and `box-shadow` to define the focus ring styling.
