## 2024-05-24 - CSS-only Dropdown Accessibility
**Learning:** Static CSS-only hover dropdowns completely break keyboard accessibility and lack screen reader context. Using `aria-expanded` statically is an anti-pattern since it cannot be toggled without JavaScript.
**Action:** Always pair `:hover` selectors with `:focus-within` to enable Tab navigation, and use static `aria-haspopup="true"` on the trigger element to properly indicate the presence of a menu without asserting its open/closed state.
