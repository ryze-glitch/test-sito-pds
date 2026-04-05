## 2024-03-21 - CSS Dropdowns Accessibility
**Learning:** Pure CSS dropdown menus that use `visibility: hidden` and `:hover` block keyboard navigation entirely. Screen readers and keyboard users cannot tab into hidden elements, making submenus completely inaccessible.
**Action:** When encountering CSS-only hover dropdowns, always add `:focus-within` alongside `:hover` to the parent container. This ensures the submenu becomes visible and focusable when a user tabs onto the parent trigger, unlocking navigation to the child links.
