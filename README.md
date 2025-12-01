# CollabRoom - Real-time Collaborative Project Management

CollabRoom is a web-based platform that enables teams to collaborate on projects in real-time. It features task management with drag-and-drop Kanban boards, live document editing, instant messaging, file sharing, and comprehensive analytics.

## Features

- **Real-time Collaboration**: Live updates across all team members
- **Task Management**: Drag-and-drop Kanban board with To Do, Doing, and Done columns
- **Room-based Organization**: Create or join rooms with unique codes
- **Live Editing**: Collaborative document editing in tasks with cursor indicators
- **Messaging**: Room-level and task-specific chat
- **File Sharing**: Upload and share files with organized folder structure
- **Analytics Dashboard**: Track team performance and task completion rates
- **Member Management**: View team members and their work status
- **Multi-room Support**: Users can be part of multiple rooms

## Tech Stack

**Frontend:**
- React 18
- Vite
- Tailwind CSS
- Socket.io Client
- Y.js (Collaborative editing)

**Backend:**
- Node.js
- Express
- MongoDB
- Socket.io
- Cloudinary (File storage)

## Prerequisites

Before you begin, ensure you have installed:
- Node.js (v14 or higher)
- npm or yarn
- MongoDB (local or cloud instance)
- Cloudinary account (for file uploads)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Mohan3030/CollabRoom.git
cd collabroom
```

### 2. Backend Setup

```bash
cd server
npm install
```

Create a `.env` file in the server directory:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
PORT=3000
```

Start the backend server:

```bash
npm start
```

The server will run on `http://localhost:3000`

### 3. Frontend Setup

```bash
cd client
npm install
```

Start the development server:

```bash
npm run dev
```

The application will open at `http://localhost:5173`

## Usage

### Creating a Room

1. Click "Create Room" on the home page
2. Enter your name and project name
3. Share the room code with team members

### Joining a Room

1. Click "Join Room"
2. Enter your name and the room code
3. Click "Join Room"

### Managing Tasks

- **Create Task**: Use the quick add input or "Create Detailed" button
- **Assign Task**: Select a team member when creating a task
- **Move Task**: Drag tasks between columns (To Do, Doing, Done)
- **Edit Task**: Click on a task to open the editor
- **Delete Task**: Hover over a task and click the × button

### Collaboration

- **Live Editing**: Edit task descriptions in real-time with other team members
- **Cursor Indicators**: See where other users are editing with color-coded cursors
- **Chat**: Send messages at room level or within specific tasks
- **File Sharing**: Upload files to rooms or tasks

### Analytics

- Click the "Members" dropdown in the top right
- Click "View Full Analytics" to see:
  - Task distribution
  - Team performance metrics
  - Individual member statistics
  - Download analytics as PDF

## Project Structure
```

### API Endpoints

### Rooms
- `POST /api/rooms/create` - Create a new room
- `POST /api/rooms/join` - Join an existing room
- `POST /api/rooms/leave` - Leave a room

### Tasks
- `GET /api/tasks/room/:roomCode` - Get all tasks in a room
- `POST /api/tasks/create` - Create a new task
- `PUT /api/tasks/:taskId` - Update a task
- `DELETE /api/tasks/:taskId` - Delete a task

### Messages
- `GET /api/messages/room/:roomCode` - Get room messages
- `POST /api/messages/room` - Send room message
- `GET /api/messages/task/:taskId` - Get task messages
- `POST /api/messages/task` - Send task message

### Files
- `POST /api/upload/room` - Upload file to room
- `POST /api/upload/task` - Upload file to task
- `GET /api/upload/room/:roomCode` - Get room files
- `GET /api/upload/task/:taskId` - Get task files

## Environment Variables

### Server (.env)

```
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/collabroom
JWT_SECRET=your_secret_key_here
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
PORT=3000
```

