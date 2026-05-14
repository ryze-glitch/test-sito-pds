## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-14 - Accessible CSS-only Dropdowns
**Learning:** Pure CSS dropdowns that rely solely on `:hover` are inaccessible to keyboard users and screen readers, making site navigation impossible for some users.
**Action:** Always pair `:hover` selectors with `:focus-within` for dropdowns, and add `aria-haspopup="true"` to the triggering element to ensure keyboard and screen reader accessibility without needing JavaScript.
