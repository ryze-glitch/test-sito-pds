## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.
## 2024-05-18 - Semantic Accessibility for Custom Breadcrumbs
**Learning:** Static HTML sites often rely on custom CSS classes like `.breadcrumb` on generic `<div>` tags to represent navigation hierarchies. While visually functional, this completely hides the navigation structure from screen readers and forces them to parse decorative separators.
**Action:** When working on navigation components in plain HTML sites, proactively identify `class="breadcrumb"` or similar containers and upgrade them to semantic `<nav aria-label="Breadcrumb">` elements. Simultaneously, ensure decorative separators (like `>`) have `aria-hidden="true"` and the active element has `aria-current="page"`.
