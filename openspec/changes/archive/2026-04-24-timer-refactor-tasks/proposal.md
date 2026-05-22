# Proposal: Timer Refactor and Task Management

## Problem
The current Pomodoro tool has several limitations:
- It includes a music generator placeholder that isn't functional or desired.
- Timer choices are fixed (e.g., 1h, 30m), lacking flexibility for user preferences.
- There is no way to manage specific tasks associated with a study session.
- The interface remains cluttered during an active session, which can be distracting.

## Solution
Refactor the timer and add a task management system to create a more focused and flexible study environment.

### Key Features
1. **Settings Modal**: Replace fixed timer buttons with a settings tab (modal) where users can:
   - Set custom study durations via dropdown or manual input.
   - Configure short and long break lengths.
2. **Break Integration**: Add "Short Break" and "Long Break" modes alongside the "Study" timer.
3. **Unified Controls**: A single set of controls (Start/Stop/Reset) that applies to whichever mode is currently active.
4. **Task Management**:
   - "Add Task" feature to store short descriptions.
   - Option to select a task for the current session.
5. **Focus Mode**: When the timer is running, the UI will simplify to show only the active timer, controls, and the current task description. All settings and task management will be hidden until the timer is paused or reset.

## Goals
- Provide flexible timing for sessions and breaks.
- Integrate task tracking into the workflow.
- Enhance focus by minimizing UI elements during active countdowns.
- Clean up unused placeholders.

## Non-Goals
- Persistence (local storage or database) - tasks and settings will reset on page reload for now.
- Actual music generation.
