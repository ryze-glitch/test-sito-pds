## 2024-05-20 - Breadcrumb Accessibility Pattern
**Learning:** For static HTML implementations lacking frontend frameworks, breadcrumb navigation often relies on non-semantic generic `<div>` wrappers and decorative inline elements (`<i>` chevrons) without ARIA attributes.
**Action:** When building or fixing breadcrumbs across static sites, always use `<nav aria-label="Breadcrumb">`, apply `aria-hidden="true"` to decorative visual separators, and ensure the active node uses `aria-current="page"`.
