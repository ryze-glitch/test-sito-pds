## 2026-04-26 - Focus Visible and Dropdown Accessibility
**Learning:** Global CSS resets or missing focus styles often completely hide keyboard focus rings. Dropdowns triggered only by `:hover` are invisible to keyboard users.
**Action:** Use a universal `*:focus-visible` rule tied to the project's accent color (`var(--accent-blue)`) for accessible focus rings. Pair `:hover` with `:focus-within` for CSS-only dropdowns, and add `aria-haspopup="true"` to their triggers.
