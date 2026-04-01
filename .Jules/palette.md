## 2026-04-01 - Dropdown Menu Keyboard Accessibility
**Learning:** CSS hover-based dropdown menus are completely inaccessible via keyboard unless explicitly styled with `:focus-within`.
**Action:** Always pair `.dropdown:hover` with `.dropdown:focus-within` to ensure keyboard users can reveal and navigate nested menu items.
