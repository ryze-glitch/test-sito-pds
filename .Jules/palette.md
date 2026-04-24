
## 2024-05-24 - Static HTML Dropdown Keyboard Accessibility
**Learning:** The custom static HTML dropdowns (`.dropdown` / `.dropdown-menu`) in this application relied solely on `:hover` states, completely breaking keyboard tab navigation, and lacked native focus rings.
**Action:** Always pair `.dropdown:hover` with `.dropdown:focus-within` to enable keyboard toggling without JavaScript, and globally implement `:focus-visible` outlines using the existing `var(--accent-blue)` variable for interactive elements.
