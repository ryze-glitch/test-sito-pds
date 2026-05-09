## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.

## 2024-05-09 - CSS-Only Dropdowns Require :focus-within
**Learning:** In static sites with CSS-only hover dropdowns (using `.dropdown:hover`), screen reader and keyboard users cannot trigger the menu because hover states are not accessible via Tab navigation. Adding `aria-haspopup="true"` provides context, but the menu must be visually exposed for focus to move inside.
**Action:** When maintaining CSS-only dropdowns, always pair `:hover` state selectors with `:focus-within` (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure keyboard users can reveal and interact with the submenu links.
