---
name: testing-html
description: Test static HTML/CSS changes in the Game repo. Use when verifying layout, styling, or markup changes.
---

# Testing HTML/CSS Changes

## Setup
- No credentials or secrets needed
- No build step required — static HTML files
- Open files directly in Chrome via `file:///home/ubuntu/repos/Game/<filename>`

## How to Test

1. **Open the file in Chrome**: Navigate to `file:///home/ubuntu/repos/Game/index.html` in the browser address bar. Make sure to click the actual URL bar (not the search/omnibox) and use the full `file:///` prefix.

2. **Verify CSS with DevTools**:
   - Open DevTools (F12)
   - Select the element in the Elements tab
   - Check the **Styles** tab to see which CSS rules are applied and which are overridden (struck through)
   - Check the **Computed** tab to see the final computed values for properties like margin, padding, box-sizing

3. **Visual verification**: Inject test elements via the Console tab to visually confirm layout behavior. For example:
   ```js
   document.body.innerHTML = '<div style="background:red;height:50px;width:100%">Test</div>'
   ```
   This helps verify properties like zero margins (content should be flush against viewport edges).

## Tips
- When typing `file:///` URLs in Chrome, click the address bar (not the search box) to avoid Google search
- The browser's default body margin is 8px — a CSS reset with `* { margin: 0 }` should override this (visible as strikethrough in Styles tab)
- Use the Computed tab for definitive proof of computed values rather than relying on visual inspection alone

## Devin Secrets Needed
None — static HTML testing requires no authentication.
