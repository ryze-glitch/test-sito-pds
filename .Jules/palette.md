## 2026-02-27 - Keyboard Accessible Dropdowns
**Learning:** Static CSS-only dropdowns using `:hover` are inaccessible to keyboard users, trapping navigation.
**Action:** Pair `:hover` with `:focus-within` to ensure dropdowns remain open when interacting via keyboard, and add `aria-haspopup="true"` to the triggering element to indicate the presence of a menu to screen readers.
