
## 2024-05-18 - Keyboard Accessible CSS Dropdowns
**Learning:** CSS-only dropdowns using `.dropdown:hover .dropdown-menu` are completely inaccessible to keyboard users because hover events don't trigger on tab focus. Using `.dropdown:focus-within` allows the menu to expand when a user tabs into any element inside the dropdown container.
**Action:** When creating or maintaining CSS-only dropdowns in this repository, always pair `:hover` state selectors with `:focus-within` (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure keyboard navigability.
