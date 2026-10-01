## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-23 - Avoid Hardcoded Border-Radius on Global Focus States
**Learning:** Applying a hardcoded `border-radius` (e.g., `4px`) to global pseudo-classes like `a:focus-visible, button:focus-visible` forcefully overrides the natural shape of inherently rounded elements (such as pill-shaped buttons with `border-radius: 999px`). The focus ring should instead inherit the element's base geometry naturally, relying only on properties like `outline` and `outline-offset`.
**Action:** When defining global `:focus-visible` styles, remove any `border-radius` assignments to prevent breaking the visual design of specially shaped components across the application.
