## 2024-05-24 - Accessibility Initialization
**Learning:** Initializing palette journal.
**Action:** Ready to log critical a11y learnings.
## 2024-05-24 - Inheriting Border Radius for Focus Visible
**Learning:** Hardcoded `border-radius: 4px;` in a global `:focus-visible` pseudo-class (e.g. `a:focus-visible, button:focus-visible`) overrides the natural shape of inherently rounded elements (like `.nav-login-btn` with `border-radius: 999px;`), making focus styles look misaligned.
**Action:** Removed hardcoded `border-radius` from the focus pseudo-class so it naturally inherits the element's base shape. Let the focus visual rely on `outline`, `outline-offset`, and `box-shadow` instead.
