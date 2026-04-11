## 2024-04-11 - Dropdowns Missing Keyboard Focus States
**Learning:** Pure CSS dropdown menus implemented via `.dropdown:hover .dropdown-menu` are inherently inaccessible to keyboard navigation because standard tabbing does not trigger hover. The dropdown simply never appears for users tabbing through the `nav`.
**Action:** When working on navigation menus, verify that CSS-based dropdowns include `.dropdown:focus-within .dropdown-menu` alongside `:hover` to ensure that when a nested anchor tag receives focus, the dropdown remains visible.
