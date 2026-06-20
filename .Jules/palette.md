## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-06-20 - Global focus-visible Border Radius
**Learning:** Hardcoding a generic `border-radius` (like `4px`) in a global `:focus-visible` selector breaks the visual polish of inherently rounded elements (like pill buttons), forcing them into rectangular focus rings instead of naturally hugging the element's actual shape.
**Action:** Remove `border-radius` from global focus states. Rely only on `outline`, `outline-offset`, and `box-shadow`, allowing browsers to automatically calculate the focus ring shape based on the target element's native `border-radius`.
