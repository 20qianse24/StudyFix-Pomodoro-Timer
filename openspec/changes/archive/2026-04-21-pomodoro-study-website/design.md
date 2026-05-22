## Context

The project is a new, standalone web application. The goal is to create a functional Pomodoro timer with a clean, minimalist UI using vanilla HTML, CSS, and JavaScript.

## Goals / Non-Goals

**Goals:**
- Implement a functional countdown timer with Start/Pause/Reset.
- Provide preset buttons for 30m, 60m, and 90m intervals.
- Ensure a centered, modern, and distraction-free UI.
- Use separate files for HTML, CSS, and JS.
- Structure the DOM to accommodate future features (Tasks, Music).
- Play a notification sound on completion.

**Non-Goals:**
- Implementing the OpenAI playlist generator (future iteration).
- Implementing the task checklist logic (future iteration).
- Server-side state persistence or user accounts.

## Decisions

### 1. Vanilla JavaScript for Logic
- **Decision:** Use vanilla JS (`setInterval`, DOM manipulation) without any frameworks.
- **Rationale:** The scope is small and self-contained. Adding a framework like React or Vue would introduce unnecessary complexity and bundle size for a simple timer.
- **Alternatives:** React/Vue (rejected for being overkill for this stage).

### 2. Standard CSS for Styling
- **Decision:** Use a single `style.css` file with Flexbox for centering and a soft color palette.
- **Rationale:** Vanilla CSS is highly flexible and sufficient for the requested minimalist design.
- **Alternatives:** Tailwind CSS (rejected as vanilla CSS is preferred for this prototype).

### 3. DOM Structure for Scalability
- **Decision:** Use a semantic HTML structure with distinct `<section>` elements for the Timer, Tasks, and Music components.
- **Rationale:** This makes it easy to add the planned features in future iterations without refactoring the core layout.

### 4. Audio Notification Implementation
- **Decision:** Use the HTML5 `<audio>` element with a small, embedded-ready sound file (or a reliable external link if local assets are restricted).
- **Rationale:** Simple to implement and widely supported.

## Risks / Trade-offs

- **[Risk] Timer accuracy in background tabs** → **Mitigation:** Browsers may throttle `setInterval` in background tabs. For a study tool, users are expected to keep the tab visible or active. Using `Web Workers` could be a future mitigation if accuracy becomes a critical issue, but for now, we will stick to standard `setInterval`.
- **[Risk] Browser support for audio autoplay** → **Mitigation:** Most browsers block audio until the user interacts with the page (e.g., clicking the "Start" button). This aligns with our UX since the user must click to start the timer.
