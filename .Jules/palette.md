
## 2024-04-15 - CSS Dropdown Keyboard Accessibility
**Learning:** CSS-only dropdown menus using `:hover` are inaccessible to keyboard users because `Tab` navigation doesn't trigger the hover state. This is a common pattern in simple static sites that lack JavaScript for menu handling.
**Action:** Always add `:focus-within` alongside `:hover` (e.g., `.dropdown:hover .menu, .dropdown:focus-within .menu`) for CSS-driven dropdowns to ensure they become visible when a user tabs into the trigger or the menu items.
