
## 2024-05-18 - Keyboard Accessible Pure-CSS Dropdowns
**Learning:** Pure CSS dropdown menus built with `:hover` become completely inaccessible to keyboard users unless explicitly handled. Standard `a:focus` rules do not trigger the parent container to keep the submenu open.
**Action:** Always append `:focus-within` alongside `:hover` on the parent `.dropdown` container. This simple addition makes pure-CSS dropdowns fully navigable via keyboard, triggering the same smooth CSS transitions without requiring any JavaScript.
