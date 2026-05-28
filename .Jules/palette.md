## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-28 - Focus Ring Shape Preservation
**Learning:** Hardcoding `border-radius: 4px;` directly into a global `:focus-visible` pseudo-class (e.g., `a:focus-visible, button:focus-visible`) forces all focused elements to take on a slightly rounded rectangular shape. This overrides the natural shape of inherently rounded elements (like pill-shaped `.nav-login-btn`), causing an awkward shape-shift during keyboard navigation.
**Action:** When defining global focus states, apply the `outline` and `outline-offset` but omit `border-radius`. Modern browsers automatically contour the `outline` to match the element's inherited `border-radius`, ensuring a smooth and consistent focus ring across elements of all shapes.
