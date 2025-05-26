Event Calendar Project: How It Works

1. Introduction
The Event Calendar Project is a full-stack web application designed to help users manage events efficiently. It allows users to create, edit, and delete events, with features like recurring events, categorization, filtering, and drag-and-drop functionality. The application is built with a React frontend and a Node.js/Express backend, using MongoDB for data storage.

2. Project Structure
The project is organized into two main folders:
- Frontend: Contains the React-based user interface.
  - src/components/EventForm.js: Handles the form for adding and editing events.
  - src/components/Calendar.js: Displays the calendar and events.
  - src/styles.css: Defines the styling, including a yellowish background (#fff9db) for a warm aesthetic.
- Backend: Contains the server-side logic.
  - server.js: The main server file, setting up Express and MongoDB.
  - models/Event.js: Defines the Mongoose schema for events, including fields like startDateTime.
  - routes/events.js: Defines API routes for CRUD operations on events.

3. How the Application Works
3.1 Frontend Workflow
- The user opens the app at http://localhost:3000.
- A calendar (powered by React-Calendar) is displayed, showing the current month.
- Clicking a date opens a modal form (EventForm.js) where the user can:
  - Enter event details: title, start date, start time, description, recurrence (none, daily, weekly, monthly), and category (Work, Personal, Other).
  - Save the event, cancel the form, or delete an existing event.
- Events are displayed on the calendar with color-coded backgrounds based on their category.
- Users can drag events to different dates, filter events by category, and view recurring events.

3.2 Backend Workflow
- The backend runs on http://localhost:5000 and provides RESTful API endpoints.
- When a user saves an event:
  - The frontend sends a POST request to /api/events with the event data.
  - The backend validates the data and saves it to MongoDB using the Event model.
- When the calendar loads, the frontend fetches all events via a GET request to /api/events.
- Events are stored with a startDateTime field, combining the date and time for accurate scheduling.

3.3 Key Features
- Event Management: Users can add, edit, and delete events via a modal form.
- Recurring Events: Events can recur daily, weekly, or monthly.
- Categories and Colors: Events are categorized as Work, Personal, or Other, with distinct colors for each.
- Filtering: Users can filter events by category to focus on specific types.
- Drag-and-Drop: Events can be dragged to different dates, updating their startDateTime.
- Styling: The app uses a yellowish background (#fff9db) and a compact form layout (labels and inputs on the same line).

4. Technical Details
4.1 Frontend
- Built with React for a dynamic, component-based UI.
- Uses React-Calendar for the calendar interface.
- Axios is used to make API calls to the backend.
- Styled with CSS, featuring a yellowish background and color-coded event categories.

4.2 Backend
- Built with Node.js and Express for the server.
- MongoDB is used as the database, with Mongoose for schema definition and querying.
- API Routes:
  - GET /api/events: Fetch all events.
  - POST /api/events: Create a new event.
  - PUT /api/events/:id: Update an existing event.
  - DELETE /api/events/:id: Delete an event.

4.3 Data Flow
- When a user interacts with the calendar (e.g., adding an event), the frontend sends a request to the backend.
- The backend processes the request, interacts with MongoDB, and sends a response.
- The frontend updates the UI based on the response, ensuring a seamless user experience.

5. Setup and Usage
5.1 Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- Git

5.2 Setup
- Backend:
  1. Navigate to backend/: cd backend
  2. Install dependencies: npm install
  3. Create a .env file with MONGO_URI and PORT.
  4. Start the server: npm start
- Frontend:
  1. Navigate to frontend/: cd frontend
  2. Install dependencies: npm install
  3. Start the app: npm start

5.3 Usage
- Open http://localhost:3000 in your browser.
- Click a date to add an event, fill in the details, and save.
- Use the calendar to view, edit, or delete events.

6. Conclusion
The Event Calendar Project provides a robust solution for event management with a user-friendly interface and powerful features. Its full-stack architecture ensures scalability and flexibility for future enhancements.
