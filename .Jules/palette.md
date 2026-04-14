## 2024-05-24 - Dropdown Navigation Accessibility
**Learning:** Dropdowns using only `:hover` for their menus are inaccessible to keyboard users because the hover state isn't triggered on focus.
**Action:** Add `:focus-within` alongside `:hover` to any parent elements containing a hidden menu to ensure the menu becomes visible when a user tabs into it.
