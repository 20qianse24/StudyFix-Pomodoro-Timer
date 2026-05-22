## ADDED Requirements

### Requirement: Digital Timer Display
The system SHALL provide a digital countdown display in the format MM:SS.

#### Scenario: Initial State
- **WHEN** the page loads
- **THEN** the timer SHALL display "30:00" as the default initial value.

### Requirement: Timer Control - Start
The system SHALL provide a "Start" button that begins the countdown.

#### Scenario: Starting the timer
- **WHEN** the user clicks "Start"
- **THEN** the timer SHALL begin counting down one second at a time.

### Requirement: Timer Control - Pause
The system SHALL provide a "Pause" button that halts the countdown.

#### Scenario: Pausing the timer
- **WHEN** the timer is running and the user clicks "Pause"
- **THEN** the timer SHALL stop at the current time and the countdown SHALL cease.

### Requirement: Timer Control - Reset
The system SHALL provide a "Reset" button that returns the timer to the currently active preset value.

#### Scenario: Resetting the timer
- **WHEN** the user clicks "Reset"
- **THEN** the timer SHALL return to the initial value of the currently selected preset (e.g., "30:00", "60:00", or "90:00").

### Requirement: Study Session Presets
The system SHALL provide three dedicated preset buttons for study sessions: 30 minutes, 1 hour (60 minutes), and 1.5 hours (90 minutes).

#### Scenario: Selecting 60 minute preset
- **WHEN** the user clicks the "1 Hour" button
- **THEN** the timer display SHALL update to "60:00".

#### Scenario: Selecting 1.5 hour preset
- **WHEN** the user clicks the "1.5 Hours" button
- **THEN** the timer display SHALL update to "90:00".

### Requirement: Completion Notification
The system SHALL play a subtle audio notification sound when the timer reaches "00:00".

#### Scenario: Timer completion
- **WHEN** the timer reaches "00:00"
- **THEN** the system SHALL play the notification audio file once.
