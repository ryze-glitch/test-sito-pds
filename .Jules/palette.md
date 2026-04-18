## 2024-05-18 - Missing Focus Indicators
**Learning:** The application lacks global focus indicators, which negatively impacts keyboard accessibility as users cannot track which element has focus.
**Action:** Applied `:focus-visible` styles to `a` and `button` elements using existing design tokens (`var(--accent-blue)`) to provide clear visual feedback without disrupting mouse users.
