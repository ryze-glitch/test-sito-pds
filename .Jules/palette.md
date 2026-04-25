## 2024-05-24 - Accessibility Anti-Pattern: CSS Dropdowns
**Learning:** This repository uses pure CSS dropdown menus (`.dropdown:hover .dropdown-menu`) which are not keyboard accessible, as they require mouse hover to trigger visibility.
**Action:** Always pair `:hover` state selectors with `:focus-within` (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure dropdowns can be navigated via keyboard tabbing.
