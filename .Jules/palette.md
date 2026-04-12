## 2024-04-12 - Missing Keyboard Accessibility for Dropdowns
**Learning:** CSS-only hover dropdown menus completely lock out keyboard users. A dropdown revealed only on `:hover` cannot be accessed using the `Tab` key.
**Action:** Always include `:focus-within` whenever using `:hover` to display interactive sub-elements (e.g., `.dropdown:hover, .dropdown:focus-within`). Additionally, explicitly define a custom `:focus-visible` outline for interactive elements to improve navigation clarity.
