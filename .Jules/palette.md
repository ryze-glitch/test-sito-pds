## 2024-05-18 - Single Stroke Focus for Micro-UX Changes
**Learning:** Even when multiple related a11y issues exist (like hover-only menus, missing focus visible states, and missing aria-labels), fixing all of them at once violates the "micro-UX improvement under 50 lines" constraint and results in PR rejection. A "single stroke" approach must be strictly enforced.
**Action:** When acting as Palette, identify multiple opportunities but selectively implement exactly ONE focused change (e.g., ONLY fixing keyboard access for dropdowns) to ensure the diff remains strictly under 50 lines.

## 2024-05-18 - Playwright Focus Simulation for CSS Pseudo-classes
**Learning:** When writing Playwright verification scripts to test CSS-only accessibility features (like `:focus-within` on dropdown menus), using `locator.focus()` can be unreliable and fail to trigger the intended CSS states, or timeout due to strict mode violations with multiple locators.
**Action:** Always simulate genuine user interaction by utilizing `page.keyboard.press("Tab")` to sequentially navigate focus through the DOM, exactly as a real keyboard user would. This ensures CSS pseudo-classes are correctly evaluated.
