## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.
## 2024-05-22 - Keyboard Accessible Dropdowns
**Learning:** Pure CSS dropdown menus relying only on `:hover` prevent keyboard-only users from accessing submenus. Adding `:focus-within` allows the menu to open when users tab into it, meeting WCAG keyboard accessibility standards without requiring JavaScript.
**Action:** When auditing navigation menus, always ensure `:hover` selectors for dropdowns are paired with `:focus-within` to guarantee keyboard accessibility.

## 2024-05-24 - Semantic Breadcrumb Container
**Learning:** Breadcrumb navigations in this project frequently use a generic `<div class="breadcrumb">` wrapper. This creates an accessibility barrier for screen reader users who rely on semantic `<nav aria-label="Breadcrumb">` wrappers to discover and navigate breadcrumb lists. Additionally, purely decorative separator icons (like chevrons) must be explicitly hidden (`aria-hidden="true"`) to prevent screen readers from reading them out loud as separate items.
**Action:** When working on breadcrumbs, replace `<div>` with `<nav aria-label="Breadcrumb">`, hide separator icons with `aria-hidden="true"`, and indicate the active page element with `aria-current="page"`.
