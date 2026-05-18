## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.

## 2024-05-18 - Ensure Keyboard Access for CSS Dropdowns
**Learning:** For static sites using inline CSS dropdowns mapped only to `:hover`, screen reader and keyboard accessibility is entirely blocked. Testing focus states directly with Playwright `locator.focus()` might fail to trigger complex CSS `:focus-within` state interactions.
**Action:** Always map `:hover` to `:focus-within` to maintain keyboard-accessible dropdown functionality. Verify keyboard states via `page.keyboard.press('Tab')` rather than explicitly calling `.focus()` in verification scripts to truly simulate user tab navigation.
