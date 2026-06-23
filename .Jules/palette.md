## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-23 - Focus Outlines on Pill Buttons
**Learning:** Hardcoding `border-radius` (like `4px`) on global `:focus-visible` pseudo-classes breaks the focus ring shape on inherently rounded or pill-shaped interactive elements (like `border-radius: 999px` buttons). The focus ring becomes a tight rectangle, failing to match the element's actual geometry.
**Action:** Remove hardcoded `border-radius` from global `:focus-visible` rules. Rely only on `outline` and `outline-offset`, allowing the browser to naturally inherit and draw the outline based on the element's specific `border-radius`.
