## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2023-10-11 - Semantic Breadcrumb Navigation
**Learning:** Hardcoded HTML breadcrumbs (`<div class="breadcrumb">`) are often implemented purely for visual layout without consideration for screen reader semantics. They lack the structural role (`nav`), explicit label (`aria-label`), marker for the current page (`aria-current`), and often expose decorative separators (like `>`) to assistive technology.
**Action:** When implementing or modifying breadcrumbs, always use a `<nav aria-label="Breadcrumb">` wrapper, mark the active item with `aria-current="page"`, and explicitly hide visual separators from screen readers using `aria-hidden="true"`.
