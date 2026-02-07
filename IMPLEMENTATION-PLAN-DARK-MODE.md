# Implementation Plan: Dark Mode Toggle Feature

## TL;DR
Implement a dark mode toggle button in the game header that switches between light and dark themes, persists user preference in localStorage, and maintains WCAG AA contrast compliance across all UI elements.

## Steps

### 1. Add Dark Mode Styles to CSS
- Create CSS custom properties for dark mode (e.g., `html.dark-mode { --background-color: #1e1e1e; }`)
- Define color variables: background (#1e1e1e), text (#e0e0e0), card backgrounds, button colors
- Update `.modal-content`, `.controls`, `.scores-list` to use dynamic color variables instead of hardcoded white
- Ensure all interactive elements have sufficient contrast ratios (4.5:1 for text, 3:1 for graphics)

### 2. Update HTML Structure
- Restructure `.header` to use flexbox layout with space between title and toggle button
- Add toggle button: `<button class="dark-mode-toggle">🌙 Dark Mode</button>`
- Ensure button has proper `aria-label` for accessibility

### 3. Add JavaScript Functionality
- Create `initializeDarkMode()` function to load preference from localStorage on page load
- Create `toggleDarkMode()` function to toggle `dark-mode` class on `<html>` element
- Store preference in localStorage as key `darkMode` with boolean value
- Update button label dynamically: "☀️ Light Mode" when dark mode is active
- Attach click listener to dark mode toggle button

### 4. Update Event Listeners
- Add event listener for `.dark-mode-toggle` button to call `toggleDarkMode()`
- Initialize dark mode on page load (call `initializeDarkMode()` before other initialization)

### 5. Test Accessibility & Contrast
- Verify color contrast ratios meet WCAG AA standards
- Test button in light and dark modes
- Check keyboard navigation (Tab, Enter/Space to activate)
- Verify theme applies instantly without page reload

### 6. Test Cross-Browser Compatibility
- Test on Chrome, Firefox, Safari (desktop)
- Test on mobile browsers
- Verify localStorage persists across sessions

## Verification

**Visual Testing:**
- Toggle button visible in header, theme switches on click

**Persistence:**
- Close browser tab, reopen—theme preference preserved

**Accessibility:**
- Use contrast checker tool (WebAIM) or browser DevTools accessibility panel

**Performance:**
- Toggle should be instant (no animation lag)

**Unit Tests (optional):**
- Create test suite for `toggleDarkMode()` and `initializeDarkMode()`

## Decisions

- **CSS Approach:** Chose CSS custom properties (`:root` and `html.dark-mode`) for simplicity over JavaScript-only theming
- **Button Placement:** Toggle button placed in header (right-aligned) for prominent visibility
- **Persistence:** Used localStorage for persistence (simple, no backend required)
- **Button Label:** Includes emoji for visual clarity without text-only reliance

## Status
✅ Ready for review
