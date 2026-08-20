## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-08-20 - Global focus-visible Border Radius Conflicts with Pill Shapes
**Learning:** Hardcoding a small `border-radius` (like `4px`) on global pseudo-class selectors like `button:focus-visible` creates jarring visual conflicts with elements that possess an inherently different shape, such as fully rounded pill buttons (`border-radius: 999px`). The focus ring incorrectly snaps the element's corners during keyboard navigation.
**Action:** When defining global focus outlines, rely only on `outline`, `outline-offset`, and `box-shadow`, omitting `border-radius` so that the browser naturally draws the focus outline conforming to the element's existing border shape.
