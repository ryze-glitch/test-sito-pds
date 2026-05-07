## 2024-05-07 - CSS-Only Dropdown Accessibility
**Learning:** Pure CSS dropdowns that rely exclusively on `:hover` prevent keyboard navigation for screen reader and tab-key users.
**Action:** Pair `:hover` selectors with `:focus-within` for CSS dropdowns, and add `aria-haspopup="true"` to the trigger link to ensure screen readers announce the menu correctly.
