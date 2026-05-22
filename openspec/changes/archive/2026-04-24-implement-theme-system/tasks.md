# Tasks: Theme System Implementation

## Phase 1: CSS Foundations
- [x] Define `:root` default variables and `:root[data-theme="light/dark"]` overrides in `style.css`.
- [x] Update global styles in `style.css` to use theme variables for `background`, `color`, and `border`.
- [x] Add smooth transitions for `background` and `color` on the `body`.

## Phase 2: Component Restyling
- [x] Update Timer Display styling with theme-specific shadows/glows.
- [x] Refactor Buttons (Start, Pause, Reset) to use success/danger/info variables and 12px radius.
- [x] Restyle Mode Tabs (Study/Breaks) for active/inactive states in both themes.
- [x] Update Task Cards and Modals to use `--surface` and `--border` variables.
- [x] Ensure hover states are correctly applied per theme (e.g., button glow in dark mode).

## Phase 3: UI Updates (Settings)
- [x] Add "Appearance" section to the settings modal in `index.html`.
- [x] Implement theme selection inputs (e.g., radio buttons for Light/Dark).
- [x] Add a small preview or label indicator in the settings for each theme.

## Phase 4: JavaScript Logic & Persistence
- [x] Implement `setTheme(theme)` function in `script.js`.
- [x] Implement `initTheme()` function to handle `localStorage` and `prefers-color-scheme`.
- [x] Add event listeners to theme selector inputs in the settings modal.
- [x] Ensure the settings UI is updated to match the active theme on initialization.

## Phase 5: Verification & Polish
- [x] Test theme switching functionality.
- [x] Verify persistence across page reloads.
- [x] Check system preference detection.
- [x] Final visual audit for contrast, cohesion, and minimalism.
