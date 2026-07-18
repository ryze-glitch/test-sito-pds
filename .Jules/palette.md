## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-07-18 - Global Focus Styles Overriding Component Shapes
**Learning:** Applying hardcoded `border-radius` (e.g., `4px`) to global `:focus-visible` states (like `a:focus-visible, button:focus-visible`) breaks the focus outline shape for inherently rounded components (like pill buttons). The global rule forces the outline into a square-ish box, misaligning with the element's actual curved boundaries.
**Action:** Remove `border-radius` from global focus utility classes. Let `:focus-visible` naturally inherit the element's base `border-radius` by relying only on `outline`, `outline-offset`, and `box-shadow` properties to ensure focus rings wrap the component's true shape organically.
