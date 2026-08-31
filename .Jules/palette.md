## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-18 - Global focus-visible styles overriding component shapes
**Learning:** Hardcoding a `border-radius` (like `4px`) on global `:focus-visible` pseudo-classes (e.g. `a:focus-visible, button:focus-visible`) unintentionally overrides the natural shape of intrinsically rounded components, such as `.nav-login-btn` which is pill-shaped (`border-radius: 999px;`).
**Action:** When defining global focus styles, use `outline`, `outline-offset`, and `box-shadow` instead of setting `border-radius`, allowing the focus ring to naturally inherit the element's actual shape or just let the element's inherent border-radius control the corners of the focus ring.
