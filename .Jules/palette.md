## 2024-05-18 - Dropdown Keyboard Accessibility
**Learning:** Pure CSS dropdown menus implemented with `:hover` pseudo-classes on parent elements are inaccessible to keyboard users because focusing on a child link within the hidden dropdown doesn't trigger the hover state, trapping users who rely on tab navigation.
**Action:** Always add `:focus-within` alongside `:hover` on dropdown parent containers (e.g., `.dropdown:hover .dropdown-menu, .dropdown:focus-within .dropdown-menu`) to ensure keyboard users can reveal and access nested menu items.
