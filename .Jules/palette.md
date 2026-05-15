## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.

## 2024-05-19 - Keyboard Accessibility for CSS Dropdowns
**Learning:** In static sites with CSS-only dropdowns, relying solely on `:hover` makes the navigation inaccessible to keyboard users. Adding `:focus-within` to the existing `:hover` selector is a simple, robust CSS-only fix that doesn't require JavaScript.
**Action:** When encountering CSS dropdowns, ensure `:hover` is paired with `:focus-within`. Additionally, add `aria-haspopup="true"` to the trigger link to inform screen readers of the submenu.
