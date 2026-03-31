## 2024-03-31 - Keyboard Accessibility for Hover Dropdowns
**Learning:** In static HTML applications without JavaScript framework support, CSS hover-based dropdowns are completely inaccessible to keyboard users unless a `:focus-within` pseudo-class is applied alongside the `:hover` pseudo-class.
**Action:** Always verify keyboard navigation specifically on dropdown menus, and enforce a standard of mapping `.dropdown:focus-within .dropdown-menu` alongside the standard hover interaction. Also ensure `*:focus-visible` exists for clear focus rings globally.
