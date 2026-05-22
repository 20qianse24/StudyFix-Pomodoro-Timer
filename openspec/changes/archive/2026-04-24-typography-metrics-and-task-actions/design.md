# Design: Typography, Metrics, and Task Actions

## Typography
- **Google Fonts Integration**: Add `<link>` tags for `Playfair Display` and `DM Sans` to the `<head>` of `index.html`.
- **CSS Rule Updates**:
  - `font-family: 'DM Sans', sans-serif;` for `body` and general text.
  - `font-family: 'Playfair Display', serif;` for `h1`, `h2`, `h3`, and the `#timer-display`.

## Task Actions
- **UI Element**: Each `.task-item` will now contain:
  - Task description text.
  - A `.task-actions` button (three dots `⋮`).
- **Context Menu**: A small, absolute-positioned pop-up menu showing:
  - "Complete Task"
  - "Delete Task"
- **Logic**:
  - `Delete Task`: Removes the task from `state.tasks`.
  - `Complete Task`: Removes the task from `state.tasks`, increments `state.session.tasksCompleted`, and triggers the confetti effect.

## Session Metrics
- **State Update**:
  ```javascript
  state.session = {
      tasksCompleted: 0,
      pomodorosCompleted: 0
  };
  ```
- **Tracking**:
  - Increment `tasksCompleted` when a task is finished via the action menu.
  - Increment `pomodorosCompleted` in the `timerInterval` logic when `timeLeft` reaches 0 (only if `currentMode === 'study'`).
- **UI**:
  - Add "Your study session" button to the `#action-bar`.
  - Create `#session-modal` to display the counts.

## Visual Feedback (Confetti)
- **Implementation**: A lightweight JavaScript function that creates temporary `div` particles around the current mouse coordinates (`clientX`, `clientY`).
- **Styling**: Randomized colors (using theme accent colors), varying sizes, and a CSS animation for "falling" and fading out.

## UI Components
- **#session-modal**: Styled similarly to `#settings-modal`.
- **.task-actions-menu**: Styled as a small "floating" card to the right of the task item.

## Technical Tasks
1.  Embed Google Fonts in `index.html`.
2.  Update CSS variable and typography rules.
3.  Add "Your study session" button and modal HTML/CSS.
4.  Update `state` object and metrics tracking logic.
5.  Refactor `renderTasks` to include the action menu.
6.  Implement the confetti animation logic.
