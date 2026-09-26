## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-06-25 - [Breadcrumb Accessibility Pattern]
**Learning:** When implementing or modifying breadcrumb navigation across standard static HTML pages (like capo-polizia.html and qualifiche.html), standard `<div>` elements are not semantically meaningful for screen readers. Decorator separator icons without `aria-hidden` attributes cause screen reader noise, and the current active page lacks context.
**Action:** Always use a semantic `<nav aria-label="Breadcrumb">` wrapper, mark decorative separator icons (like `fa-chevron-right`) with `aria-hidden="true"`, and indicate the active page element (usually the last `<span>` or text node) with `aria-current="page"`.
