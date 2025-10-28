# Bitasmbl-ManageTasksLikeABoss

## Description
Develop a secure, scalable full-stack task management application featuring React and Redux on the frontend, Node.js with Express on the backend, MongoDB for data persistence, JWT-based authentication, project-focused task grouping, priority-sorted views, and full CRUD operations following best practices.

## Tech Stack
- React
- Redux
- Node.js (Express)
- MongoDB

## Requirements
- Implement secure JWT authentication endpoints (Hint: Use bcryptjs to hash passwords and jsonwebtoken to sign tokens)
- Develop full CRUD REST API for tasks (Hint: Separate routes and controllers for maintainability)
- Configure centralized Redux state management (Hint: Combine reducers and apply middleware for async actions)
- Display priority-sorted task views (Hint: Sort tasks array before rendering)

## Installation
bash
# Clone the repository
git clone https://github.com/<your-username>/Bitasmbl-ManageTasksLikeABoss.git
cd Bitasmbl-ManageTasksLikeABoss

# Server setup
cd server
npm install
# Create a .env file in /server with:
# MONGO_URI=your_mongodb_connection_string
# JWT_SECRET=your_jwt_secret_key
# PORT=5000 (optional)

# Client setup
cd ../client
npm install
# Create a .env file in /client with:
# REACT_APP_API_URL=http://localhost:5000/api


## Usage
1. Start the backend server:
   bash
   cd server
   npm run dev  # or npm start
   
2. Start the React frontend:
   bash
   cd client
   npm start
   
3. Open your browser at `http://localhost:3000`.
4. Register or log in to manage your projects and tasks.

## Implementation Steps
1. Structure the repo into `/server` and `/client` directories.
2. Initialize the Express server in `/server` and install dependencies (express, mongoose, bcryptjs, jsonwebtoken, dotenv).
3. Connect to MongoDB using Mongoose and configure environment variables.
4. Define User and Task Mongoose schemas and models in `/server/models`.
5. Implement authentication controllers (`register`, `login`) using bcryptjs for hashing and jsonwebtoken for signing tokens.
6. Create auth middleware to protect task routes by validating JWT tokens.
7. Build task controllers with full CRUD operations and set up Express routers in `/server/routes`.
8. Initialize React app in `/client` using Create React App and install Redux, react-redux, redux-thunk, axios.
9. Configure Redux store in `/client/src/store.js`, combine reducers, and apply thunk middleware.
10. Create Redux slices/reducers and actions for authentication and tasks in `/client/src/features`.
11. Develop React components: `Login`, `Register`, `TaskList`, `TaskItem`, `TaskForm`, and `ProjectView`.
12. Implement async actions to interact with API endpoints using axios and dispatch state updates.
13. Sort tasks by priority before rendering and group tasks by project.
14. Wire up components to Redux store using `useSelector` and `useDispatch` hooks.
15. Test all flows: user registration, login, creating, reading, updating, deleting, and prioritizing tasks.

## API Endpoints
### Authentication
- POST /api/auth/register  - Register a new user
- POST /api/auth/login     - Authenticate user and receive JWT

### Tasks (Protected)
- GET    /api/tasks        - Get all tasks for the authenticated user
- POST   /api/tasks        - Create a new task
- GET    /api/tasks/:id    - Get a single task by ID
- PUT    /api/tasks/:id    - Update an existing task
- DELETE /api/tasks/:id    - Delete a task