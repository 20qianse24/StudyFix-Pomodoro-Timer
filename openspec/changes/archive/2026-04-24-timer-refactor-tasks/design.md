# Design: Timer Refactor and Task Management

## UI Structure

### Main Page
- **Mode Tabs**: Three buttons at the top of the timer section: `Study`, `Short Break`, `Long Break`.
- **Timer Display**: Large countdown clock.
- **Controls**: `Start`, `Pause`, `Reset`.
- **Action Bar**: 
  - `Settings` button (gear icon or text).
  - `Add Task` button.
- **Task Area**: 
  - List of added tasks.
  - "Current Task" display showing the description of the selected task.

### Modals
1. **Settings Modal**:
   - Study Duration (Dropdown: 15, 25, 45, 60 or Number Input).
   - Short Break Duration (Dropdown: 5, 10 or Number Input).
   - Long Break Duration (Dropdown: 15, 20, 30 or Number Input).
   - `Save` and `Cancel` buttons.
2. **Add Task Modal**:
   - Text input for task description.
   - `Save` and `Cancel` buttons.

## State Management

```javascript
let state = {
    settings: {
        study: 25,
        short: 5,
        long: 15
    },
    currentMode: 'study', // 'study' | 'short' | 'long'
    timeLeft: 25 * 60,
    isRunning: false,
    timerInterval: null,
    tasks: [],
    selectedTaskId: null
};
```

## Behavior & Logic

### Timer Modes
- Clicking a mode tab (Study/Short/Long) immediately switches the mode, resets `isRunning` to false, and updates `timeLeft` to the duration defined in `settings`.
- Controls (`Start`, `Pause`, `Reset`) interact with the current `timeLeft` and `timerInterval`.

### Focus Mode (Active Timer)
- When `isRunning` is true:
  - Add `.hidden` class to Mode Tabs, Action Bar (Settings/Add Task), and the Task List.
  - Keep visible: Timer Display, Controls, and the "Current Task" description.
- To reveal settings/tasks again, the user must click `Pause` or `Reset`.

### Task Functionality
- `Add Task` opens the modal. Saving a task adds it to the `tasks` array.
- Clicking a task in the list sets it as the `selectedTaskId`.
- The "Current Task" description is derived from the `selectedTaskId`.

## CSS Considerations
- `.modal-backdrop`: Semi-transparent background covering the screen.
- `.modal-content`: Centered white box for inputs.
- `.hidden`: `display: none !important;` for focus mode toggling.
- Active tab styling to indicate which mode is selected.

## Technical Tasks
1. Clean up `index.html` (remove presets and music section).
2. Implement Modal HTML and CSS.
3. Update `script.js` with new state object and logic.
4. Implement "Focus Mode" visibility toggling.
5. Add task CRUD logic.
