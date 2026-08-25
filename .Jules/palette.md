## 2024-05-24 - Accessibility pattern for static breadcrumbs
**Learning:** For static HTML websites, breadcrumb navigation is often implemented as a generic `<div>` with string separators like `>`. These are completely invisible to assistive technologies which require proper landmark roles to navigate page structure.
**Action:** When implementing breadcrumbs in plain HTML, always wrap them in a `<nav aria-label="Breadcrumb">` tag, mark decorative separator elements (like FontAwesome chevrons) with `aria-hidden="true"`, and flag the active, final element with `aria-current="page"`.
