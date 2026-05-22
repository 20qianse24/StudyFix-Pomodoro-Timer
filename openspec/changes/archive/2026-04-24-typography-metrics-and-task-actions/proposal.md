# Proposal: Typography, Metrics, and Task Actions

## Problem
The current application uses system fonts, which may not align with the desired "premium productivity app" aesthetic. Additionally, tasks can be selected but not completed or deleted, and there is no tracking of session progress (tasks done, Pomodoros finished).

## Solution
Enhance the visual appeal and functional depth of the app by:
1.  **Typography Overhaul**: Integrating "Playfair Display" for titles and "DM Sans" for body text to create a more sophisticated look.
2.  **Task Management**: Adding a context menu (three dots) to each task for "Complete" and "Delete" actions.
3.  **Session Metrics**: Implementing a "Your study session" dashboard to track and display the number of tasks and Pomodoros completed during the current session.
4.  **Positive Reinforcement**: Adding a confetti effect to celebrate task completion.

## Goals
- Update all title fonts to "Playfair Display" and body fonts to "DM Sans".
- Add a three-dots action menu to each task item.
- Track "Tasks Completed" and "Pomodoros Completed" metrics.
- Add a "Your study session" button and modal to display metrics.
- Trigger a confetti effect upon task completion.
- Ensure the new features respect the existing theme system.

## Non-Goals
- Persistent storage of session metrics (reset on refresh for now).
- Complex task editing (limited to complete/delete).
- Social sharing of metrics.
