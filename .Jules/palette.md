## 2024-05-01 - CSS Dropdown Keyboard Accessibility
**Learning:** CSS-only dropdowns relying exclusively on `:hover` completely block keyboard navigation, making sub-menus inaccessible to users navigating via tab.
**Action:** Always pair `:hover` with `:focus-within` on the dropdown container to ensure the menu is revealed when internal elements receive focus, and accompany the trigger element with `aria-haspopup="true"`.
