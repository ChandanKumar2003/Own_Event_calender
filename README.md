# Setup and Running

Follow these steps to run the project locally:





## Clone the Repository:

git clone https://github.com/your-username/event-calendar.git
cd event-calendar



## Run with a Local Server (required to load CDN scripts):





### Option 1: VS Code Live Server (recommended):





Open the project folder in VS Code.



Install the Live Server extension.



Right-click index.html and select "Open with Live Server".



The browser opens to http://127.0.0.1:5500.



### Option 2: Python HTTP Server:

python -m http.server 8000

Open http://localhost:8000 in a browser.



Note: Opening index.html directly (file://) may cause CORS issues with CDN scripts.



Verify:





The calendar should load, showing the current month (e.g., May 2025).



Test features like adding events, dragging events, or navigating months.



Check the browser console (F12) for errors if the page is blank.

Addresses Deliverables by providing clear setup instructions, ensuring evaluators can run the project easily.

## Dependencies

The project uses CDN-hosted libraries, loaded directly in index.html:





React v17.0.2: For building the UI.



React DOM v17.0.2: For rendering React components.



date-fns v2.30.0: For date manipulation and formatting.



react-dnd v14.0.5: For drag-and-drop functionality.



react-dnd-html5-backend v14.0.2: Backend for drag-and-drop.



Babel Standalone v7.23.2: For in-browser JSX transpilation.



Tailwind CSS v2.2.19: For styling.

No Node.js, npm, or build tools are required. An internet connection is needed to load these scripts.

Supports Code Quality by clarifying the tech stack and simplifying setup.

## Usage





Navigate Months: Use the "Previous" and "Next" buttons to switch months.



Add Event:





Click a day to open the event form.



Enter title, time, description, recurrence (none, daily, weekly, monthly), and color.



Click "Save" to create the event.



Edit Event: Click an event’s title to open the form and modify details.



Delete Event: Click "Delete" on an event to remove it and its recurrences.



Drag-and-Drop: Drag an event to another day to reschedule (if enabled).



Conflict Handling: If you try to add an event at an occupied time slot, an alert will warn you.



Persistence: Events are saved in local storage and persist after page refresh.

Enhances User Experience by explaining how to interact with the calendar intuitively.

Troubleshooting





Blank Page:





Open developer tools (F12 > Console) to check for errors.



Ensure all CDN scripts load (F12 > Network tab; look for status 200).



If scripts fail, try alternative CDNs (e.g., https://cdnjs.cloudflare.com/ajax/libs/date-fns/2.30.0/date-fns.min.js for date-fns).



Clear the browser cache or use incognito mode.



Increase the dependency check timeout in index.html (change setInterval delay from 500ms to 1000ms):

const checkInterval = setInterval(() => { ... }, 1000ms);



Drag-and-Drop Disabled:





A yellow warning appears if react-dnd or react-dnd-html5-backend fails to load.



Other features (event management, navigation) remain functional.



CORS Issues:





Use a local server (Live Server or Python) instead of opening index.html directly.



Browser Compatibility:





Test in Chrome or Firefox. Safari or older browsers may have issues with CDN loading or Babel.

Addresses Functionality and User Experience by providing debugging steps to ensure the app runs reliably.

Project Structure

event-calendar/
├── index.html    # Main application file with React, JSX, and CDN scripts
└── README.md     # Project documentation

The single-file structure simplifies deployment but limits scalability. All logic, components, and styles are in index.html.

Supports Code Quality by documenting the project’s organization.

Future Improvements





Event Filtering: Add a search bar to filter events by title or description.



Weekly/Daily View: Implement toggleable weekly or daily calendar views.



Responsive Design: Use Tailwind’s responsive classes for better mobile support.



Accessibility: Add ARIA labels and keyboard navigation.



Performance: Optimize for large event sets with lazy loading or a backend (e.g., Firebase).



External Integration: Support Google Calendar API for importing/exporting events.

Aligns with Bonus criteria by outlining potential enhancements.
