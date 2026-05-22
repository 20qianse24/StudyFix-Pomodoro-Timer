# Tasks: Typography, Metrics, and Task Actions

## Phase 1: Typography and Global Styles
- [x] Add Google Fonts `<link>` (Playfair Display & DM Sans) to `index.html`.
- [x] Update `style.css` to use `DM Sans` for `body` and `Playfair Display` for headers and timer.
- [x] Ensure theme variables still apply correctly to the new fonts.

## Phase 2: Session Metrics
- [x] Initialize `state.session` with `tasksCompleted` and `pomodorosCompleted` in `script.js`.
- [x] Add "Your study session" button to the `#action-bar` in `index.html`.
- [x] Create the `#session-modal` HTML and styling.
- [x] Implement logic to increment `pomodorosCompleted` when study sessions finish.
- [x] Add `Your study session` modal opening/closing logic.

## Phase 3: Task Actions Menu
- [x] Update `.task-item` CSS to support the three-dots button and menu positioning.
- [x] Refactor `renderTasks` to inject the action button into each item.
- [x] Implement a global event listener to handle clicking the action button and showing the menu.
- [x] Implement `deleteTask(id)` logic.
- [x] Implement `completeTask(id, mousePos)` logic.

## Phase 4: Confetti Effect
- [x] Add CSS keyframes for the confetti animation (falling, fading, spinning).
- [x] Implement `triggerConfetti(x, y)` function in `script.js`.
- [x] Connect `triggerConfetti` to the "Complete Task" action.

## Phase 5: Polish and Verification
- [x] Ensure all pop-ups and menus are readable in both Light and Dark modes.
- [x] Verify metrics update correctly and reset on page reload.
- [x] Final UI audit for typography spacing and alignment.
