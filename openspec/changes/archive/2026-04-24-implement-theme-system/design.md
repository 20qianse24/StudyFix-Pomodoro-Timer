# Design: Theme System Implementation

## Technical Strategy
The theme system will be implemented using CSS Variables (Custom Properties) scoped to a `data-theme` attribute on the `<body>` element. JavaScript will handle the switching logic, persistence in `localStorage`, and detection of system preferences.

## UI Updates

### Settings Modal
- A new "Appearance" section will be added to the settings modal.
- It will contain two radio buttons or a toggle to select between "Sunlit Study" and "City Night Focus".
- Selecting an option will immediately update the `data-theme` attribute on the `body`.

## CSS Variable Structure

### Color Tokens
Specific variables will be defined for both themes:

| Variable | Sunlit Study (Light) | City Night Focus (Dark) |
| :--- | :--- | :--- |
| `--bg` | `#F5F1EC` | `#0F1115` |
| `--bg-gradient-end` | `#EFE7DF` | `#1A1D24` |
| `--surface` | `#EAE3DC` | `#1E222B` |
| `--primary` | `#D6C3B3` | `#2A2F3A` |
| `--secondary` | `#C8AFA0` | `#3A4150` |
| `--accent` | `#E6A85C` | `#4DA3FF` |
| `--accent-alt` | N/A | `#FFB86C` |
| `--text-primary` | `#3A3A3A` | `#E6EAF0` |
| `--text-secondary` | `#7A7A7A` | `#A0A8B8` |
| `--success` | `#A8C3A0` | `#4CAF50` |
| `--danger` | `#D6A5A5` | `#E57373` |
| `--info` | `#A9B7C6` | `#64B5F6` |
| `--border` | `#D6C3B3` | `#2A2F3A` |

### Global Transitions
```css
body {
    transition: background 0.3s ease, color 0.3s ease;
}
```

## Component Styling Rules

### Background
- **Light:** `linear-gradient(to bottom, #F5F1EC, #EFE7DF)`
- **Dark:** `linear-gradient(to bottom, #0F1115, #1A1D24)` (Optionally add faint noise/vignette)

### Timer
- **Light:** `text-shadow: 0 2px 10px rgba(230, 168, 92, 0.15)`
- **Dark:** `text-shadow: 0 0 20px rgba(77, 163, 255, 0.25)`

### Buttons (Start, Pause, Reset)
- Shared: `border-radius: 12px`, `transition: all 0.2s ease`
- Hover: Slight lift (`translateY(-1px)`), slight brightness increase.
- Dark Mode Specific: Subtle glow on hover.

### Tabs (Mode Selectors)
- Active: `--secondary`
- Inactive: Transparent + Border (Light) or Muted (Dark)
- Dark Mode Specific: Add indicator using `--accent` (underline or glow).

### Task Cards
- Background: `--surface`
- Hover: Slight elevation and subtle shadow/glow.

## JavaScript Implementation

### Persistence & Initialization
```javascript
function initTheme() {
    const savedTheme = localStorage.getItem("theme");
    const systemPrefersDark = window.matchMedia("(prefers-color-scheme: dark)").matches;
    const defaultTheme = savedTheme || (systemPrefersDark ? "dark" : "light");
    setTheme(defaultTheme);
}

function setTheme(theme) {
    document.body.setAttribute("data-theme", theme);
    localStorage.setItem("theme", theme);
    // Update settings UI to reflect selection
}
```

### Event Handlers
- Listen for changes in the theme selector inputs.
- Call `setTheme()` when a selection is made.
