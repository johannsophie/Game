---
name: testing-html-mocks
description: Test static HTML mock files in the Game repo. Use when verifying UI layout, CSS styling, or interactive features in mock HTML files.
---

# Testing HTML Mocks

## Overview
The Game repo contains static HTML mock files (e.g. `mock/theNewExplorer.html`) that can be tested locally without a dev server.

## Setup
- No dependencies or build steps required
- Open files directly via `file:///home/ubuntu/repos/Game/mock/<filename>.html` in Chrome
- No credentials or secrets needed

## Testing Approach

### CSS Verification
- Use Chrome DevTools Console to verify computed styles:
  ```js
  getComputedStyle(document.body).backgroundColor
  getComputedStyle(document.body).margin
  ```
- Compare actual values against expected values (e.g. `rgb(11, 22, 50)` for `#0b1632`)

### Visual Verification
- Check all four viewport edges for unexpected colors/gaps
- Scroll down to verify areas below content match the expected background
- Zoom into specific regions for detailed inspection

### UI Interaction Testing
- Click hex tiles and verify the detail panel updates with correct label, terrain, and notes
- Use arrow keys to move the ship and verify status text updates
- Test fullscreen toggle button
- Verify all 5 action buttons are visible in the side menu

## Key Files
- `mock/theNewExplorer.html` — Interactive HMI mock with hex map, ship movement, tile selection
- `doc/theNewExplorer.md` — Game design document
- `index.html` — Base HTML with universal CSS reset

## Branch Structure
- Default branch: `main-base`
- Mock files may exist on feature branches before being merged to `main-base`
- Check `git branch -a` and `git ls-tree` if files seem missing

## Recording
- Always record browser testing sessions for visual proof
- Maximize the browser window before recording
- Use annotations to mark test starts and assertions
