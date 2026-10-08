## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-10-08 - Inherited Border Radius for Focus States
**Learning:** Applying a hardcoded `border-radius` (e.g., `4px`) to a global `:focus-visible` pseudo-class overrides the natural, intended shape of inherently rounded UI elements (such as fully rounded, pill-shaped buttons). This causes the focus ring (or the element itself) to "snap" to the hardcoded radius during keyboard interaction, resulting in a jarring visual glitch and breaking the component's design language.
**Action:** When implementing or fixing global focus states, rely only on properties like `outline`, `outline-offset`, and `box-shadow`, allowing the focus ring to naturally inherit the element's base `border-radius`.
