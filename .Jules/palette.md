## 2026-04-23 - Keyboard Accessibility for CSS Dropdowns
**Learning:** Dropdowns styled solely with `:hover` are inaccessible to keyboard users and screen readers, locking them out of secondary navigation.
**Action:** When implementing or fixing CSS-only dropdown menus, always pair `:hover` selectors with `:focus-within` (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure the menu activates seamlessly during keyboard tab navigation.
