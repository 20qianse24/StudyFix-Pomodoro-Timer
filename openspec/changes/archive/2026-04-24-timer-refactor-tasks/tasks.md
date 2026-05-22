# Tasks: Timer Refactor and Task Management

## Phase 1: Cleanup and Base UI
- [x] Remove `#presets` div from `index.html`.
- [x] Remove `#music-section` from `index.html`.
- [x] Add Mode Tabs (`#mode-tabs`) to `index.html`.
- [x] Add Modal structures (Settings and Task) to `index.html` (initially hidden).
- [x] Add `.hidden` class and basic modal styling to `style.css`.
- [x] Add styling for Mode Tabs and Action Bar.

## Phase 2: Core Logic Refactor
- [x] Update `script.js` to use a unified `state` object.
- [x] Implement `switchMode(mode)` function to handle Study/Short/Long logic.
- [x] Connect Mode Tab buttons to `switchMode`.
- [x] Implement Settings Modal logic:
  - Opening/Closing modal.
  - Saving new durations to `state.settings`.
  - Updating `timeLeft` if the current mode's duration was changed.

## Phase 3: Task Management
- [x] Implement "Add Task" modal logic.
- [x] Implement task rendering logic (refreshing the list in the DOM).
- [x] Implement task selection logic (clicking a task to set as current).
- [x] Show selected task description below the timer.

## Phase 4: Focus Mode & Final Polish
- [x] Implement `toggleFocusMode(isFocus)` function.
- [x] Call `toggleFocusMode(true)` in `startTimer`.
- [x] Call `toggleFocusMode(false)` in `pauseTimer` and `resetTimer`.
- [x] Final UI/UX review and bug fixes.

