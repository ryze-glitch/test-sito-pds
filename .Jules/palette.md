## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-23 - Focus Visible Outline Inheritance
**Learning:** Hardcoding `border-radius` (e.g., `4px`) in a global `:focus-visible` selector forces all interactive elements, regardless of their native shape, to render a squared-off focus ring. This is particularly noticeable on fully rounded pill-shaped elements (like the `.nav-login-btn`). Modern browsers automatically contour the `outline` to match an element's intrinsic `border-radius`.
**Action:** When defining focus states, rely purely on `outline`, `outline-offset`, and `box-shadow` to indicate focus without overriding the native `border-radius`. Let the browser handle the curvature automatically.
