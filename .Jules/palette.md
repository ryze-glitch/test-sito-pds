## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2023-10-25 - Dynamic Focus Styles over Hardcoded Shapes
**Learning:** Applying hardcoded `border-radius` (e.g., `4px`) globally on `:focus-visible` states is a subtle anti-pattern, as it overrides the natural design of inherently rounded components (like pill-shaped buttons or circular avatars), causing jarring, deformed focus rings.
**Action:** Let `:focus-visible` styles inherit the target element's base `border-radius` implicitly by only declaring `outline`, `outline-offset`, and `outline-color`, allowing the browser to wrap the outline naturally around the element's actual shape.
