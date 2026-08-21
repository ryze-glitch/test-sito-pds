## 2024-05-30 - Accessible Breadcrumb Pattern
**Learning:** In static HTML templates using FontAwesome icons for separators, the `aria-hidden="true"` attribute is critical to prevent screen readers from reading out arbitrary text for the decorative chevrons.
**Action:** Always wrap breadcrumbs in `<nav aria-label="Breadcrumb">`, hide the separators, and mark the active element with `aria-current="page"`.
