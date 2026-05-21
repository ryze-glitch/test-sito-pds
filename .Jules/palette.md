## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-03-24 - [Keyboard Accessible CSS Dropdowns]
**Learning:** CSS-only dropdowns using just `:hover` are completely inaccessible to keyboard users as they cannot trigger the menu to appear using Tab navigation.
**Action:** Always pair `:hover` selectors on the dropdown container with `:focus-within` (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure the menu becomes visible when a child element receives keyboard focus.
