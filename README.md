# Focus Timer

A lightweight, browser-based focus timer created with **M365 Copilot Code**. It provides a clean countdown experience for focused work sessions without requiring a build step, package installation, or external dependencies.

## Features

- Custom focus sessions from 1 to 180 minutes
- Quick presets for 5, 15, 25, 45, and 60 minutes
- Start, pause, resume, and reset controls
- Circular progress indicator and completion percentage
- Optional three-note completion chime generated with the Web Audio API
- Keyboard shortcuts for common timer actions
- Responsive, glass-style interface that works on desktop and mobile browsers

## Prompts used to build the Focus Timer

```
Read only my next upcoming timed calendar event within the next 24 hours, using its title and start time. Build a beautifully designed focus timer with an animated progress ring, editable session length, and start, pause, and reset controls. Show a separate countdown to that event. If no event is available, build it without the meeting countdown. Don't modify my calendar.
```

Add the Chime

```
Can we modify the code so it makes a noise (something subtle) to let the user no the time ended and you should reset for next focus interval
```

## Getting Started

No installation or build process is required.

1. Clone the repository:

   ```powershell
   git clone https://github.com/DataSnowman/M365CopilotCodeFocusTimer.git
   cd M365CopilotCodeFocusTimer
   ```

2. Open `src/index.html` in a modern web browser.

You can also serve the project locally if you prefer:

```powershell
cd src
python -m http.server 8000
```

Then visit [http://localhost:8000](http://localhost:8000).

## Using the Timer

1. Enter a session length or select one of the preset buttons.
2. Select **Start** to begin the countdown.
3. Use **Pause** and **Resume** as needed.
4. Select **Reset** to restart the selected interval.
5. Toggle **Chime on/off** to control the completion sound.

### Keyboard Shortcuts

| Shortcut | Action |
| --- | --- |
| <kbd>Space</kbd> | Start, pause, or resume the timer |
| <kbd>R</kbd> | Reset the timer |

Keyboard shortcuts are ignored while the session-length input has focus.

## Project Structure

```text
M365CopilotCodeFocusTimer/
├── README.md
└── src/
    └── index.html
```

All markup, styling, and timer logic are contained in `src/index.html`.

## How It Works

- The timer calculates an expected completion timestamp and compares it with the current time, helping it remain accurate if browser rendering is briefly delayed.
- The progress ring is rendered with SVG and updated throughout the session.
- The completion chime is synthesized in the browser, so no audio files are required.
- Audio is initialized after user interaction to comply with browser autoplay restrictions.

## Browser Support

Use a current version of Microsoft Edge, Google Chrome, Mozilla Firefox, or Safari. JavaScript must be enabled. Completion audio requires Web Audio API support.

## Current Limitation

The app does not currently connect to a Microsoft 365 calendar. Because no upcoming timed calendar event is available to the page, a meeting countdown is not shown.

## Built With

- HTML5
- CSS
- JavaScript
- SVG
- Web Audio API
- M365 Copilot Code
