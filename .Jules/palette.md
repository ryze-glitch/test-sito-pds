## 2024-11-20 - CSS Dropdown Focus Within
**Learning:** CSS-only dropdown menus triggered by `:hover` are entirely inaccessible to keyboard users unless `:focus-within` is added alongside `:hover`. Furthermore, screen readers need `aria-haspopup="true"` on the trigger to announce the presence of a submenu.
**Action:** Whenever modifying or encountering CSS-based hover dropdowns, immediately check for and append `:focus-within` to the hover state, and ensure the trigger link has `aria-haspopup="true"`.
