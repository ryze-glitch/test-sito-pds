
## 2024-05-18 - Keyboard Navigation for CSS Dropdowns
**Learning:** The application uses a custom floating navbar with CSS-only dropdowns relying exclusively on `:hover` for visibility, rendering the main navigation inaccessible to keyboard and screen reader users.
**Action:** When maintaining or adding new navigation items, pair `:hover` with `:focus-within` on the `.dropdown` container and add `aria-haspopup="true"` to the trigger link to ensure complete keyboard and screen reader accessibility without requiring JavaScript.
