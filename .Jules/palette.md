## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-17 - Keyboard Access for CSS Dropdowns
**Learning:** Relying solely on `:hover` for CSS dropdowns completely locks out keyboard users. A simple `:focus-within` addition, paired with `aria-haspopup`, restores accessibility without JavaScript.
**Action:** When inspecting static HTML/CSS templates, systematically check for hover-only interactive components and pair them with focus selectors.
