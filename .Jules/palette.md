## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.

## 2024-05-20 - Ensure comprehensive deployment of CSS fixes
**Learning:** Fixing a micro-UX issue (like adding `:focus-within` for keyboard accessibility) in multiple duplicate inline HTML `<style>` blocks requires careful inspection. If one file is missed or if the codebase uses identical templates, the rollout is considered incomplete.
**Action:** When finding and replacing CSS in inline blocks, always double-check all HTML files (using `grep`) to ensure the target pattern does not exist in missed files before considering the patch complete.
