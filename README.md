<h1 align="center"> Chatly </h1>
<p align="center"> The Next-Generation Real-Time Messaging Platform </p>

<p align="center">
  <img alt="Build Status" src="https://img.shields.io/badge/Build-Passing-brightgreen?style=for-the-badge">
 
  <img alt="Frontend" src="https://img.shields.io/badge/Frontend-React%2019-61DAFB?style=for-the-badge&logo=react">
  <img alt="Backend" src="https://img.shields.io/badge/Backend-Express.js-000000?style=for-the-badge&logo=express">

</p>
<!-- 
  **Note:** These are static placeholder badges. Replace them with your project's actual badges.
  You can generate your own at https://shields.io
-->



- [⭐ Overview](#-overview)
- [✨ Key Features](#-key-features)
- [🛠️ Tech Stack & Architecture](#-tech-stack--architecture)
- [📁 Project Structure](#-project-structure)
- [🚀 Getting Started](#-getting-started)
- [🔧 Usage](#-usage)


---

## ⭐ Overview

Chatly is a high-performance, full-stack web application designed for interactive, real-time messaging. It provides a robust, scalable foundation for modern chat services, ensuring users can connect instantly through a clean, intuitive interface.

### The Problem

> Building a reliable, low-latency messaging application requires integrating complex features such as real-time updates, secure authentication flows, and dynamic state management. Developers often struggle to piece together these disparate elements into a cohesive and visually appealing experience. The resulting applications can be slow, difficult to maintain, and lack the fluidity users expect from modern communication tools.

### The Solution

Chatly solves this architectural challenge by implementing a streamlined, component-based architecture built on the powerful combination of React and Express. This structure delivers a fast, responsive user interface (Interactive user interface with React) while providing the necessary backend framework for robust communication (RESTful API). The clear separation of concerns, utilizing dedicated components for UI elements like `ChatContainer` and `MessageInput`, ensures that the application remains modular, easily testable, and highly performant under load.

### Architecture Overview

Chatly follows a decoupled architectural pattern, primarily relying on a **REST API** approach for structured data exchange and a **Component-based Architecture** on the frontend for rendering efficiency. The system leverages **Express** for handling server logic and routing, while the dynamic client experience is managed entirely by **React**. This separation allows for independent scaling and development of both the client and server components.

---

## ✨ Key Features

Chatly is engineered to deliver a seamless, feature-rich messaging experience, focusing on usability, responsiveness, and structured organization.

#### 💬 Dedicated Messaging Interface
The core experience is housed within the dynamic `ChatContainer` component, complemented by the specialized `MessageInput`. This separation ensures that sending and receiving messages is fast and fluid, supporting continuous, uninterrupted conversation flows.
*   **Benefit for the User:** Enjoy a streamlined, focused interface designed exclusively for efficient text-based communication.

#### 🛡️ Comprehensive Authentication Flow
User security and identity management are core to Chatly. The application provides dedicated pages (`LoginPage.jsx` and `SignUpPage.jsx`) and utilizes authentication controllers (`auth.controller.js`) and middleware (`auth.middleware.js`) to manage secure user sessions and access controls.
*   **Benefit for the User:** Secure access to personalized messaging history and contacts, ensuring private data remains protected.

#### 👤 Personalized User Experience
Users maintain control over their identity and application settings via dedicated `ProfilePage.jsx` and `SettingsPage.jsx` components. User data is structured using the `user.model.js`, allowing for consistent identity management across the platform.
*   **Benefit for the User:** Ability to customize the experience, manage user data, and view profile details directly within the application.

#### 🚀 High-Efficiency State Management
The frontend utilizes a highly efficient, minimal state management pattern through **Zustand**. Dedicated stores (`useChatStore.js`, `useAuthStore.js`, `useThemeStore.js`) ensure that application state—from current theme settings to real-time chat data—is managed centrally and updated instantly, reducing unnecessary re-renders.
*   **Benefit for the User:** Enjoy an extremely fast and reactive interface where data updates occur instantly without performance degradation.

#### ⏳ Optimized Loading & User Feedback
To ensure a modern, professional user experience, Chatly incorporates sophisticated loading indicators. Specialized skeleton components (`MessageSkeleton.jsx`, `SidebarSkeleton.jsx`) provide immediate visual feedback while data loads, eliminating frustrating blank screens and perceived delays.
*   **Benefit for the User:** A smoother, more professional perceived performance, even during initial data fetching or heavy loads.

#### 🌐 Structured Backend Routing
The backend is structured with clear, RESTful route definitions (`auth.route.js`, `message.route.js`) and controllers. Although the current verified API shows a single catch-all endpoint (`GET *`), the framework is fully prepared for defining and handling complex routes for authentication, message delivery, and user actions.
*   **Benefit for the User:** Ensures that application logic is reliable and scalable, minimizing downtime and maximizing data integrity.

---

## 🛠️ Tech Stack & Architecture

Chatly is built using a modern, scalable MERN-adjacent stack focused on speed, efficiency, and component modularity. The choices reflect a commitment to high-performance, maintainable code.

| Technology | Category | Purpose | Why it was Chosen |
| :--- | :--- | :--- | :--- |
| **React (v19)** | Frontend Framework | Building the interactive user interface (UI) and component structure. | Superior performance via component-based architecture and widespread community support. |
| **Express.js** | Backend Framework | Handling server routing, middleware, and API request processing. | Minimalist, fast, and unopinionated Node.js framework, ideal for creating robust RESTful APIs. |
| **Zustand** | Frontend State Management | Managing global and component-specific state (chat data, theme, auth status). | Known for its simplicity, speed, and low boilerplate, minimizing complexity compared to traditional Flux patterns. |
| **Socket.io-client** | Real-Time Communication | Establishing persistent, bi-directional communication for instantaneous message delivery. | The industry standard for WebSocket-based real-time features, ensuring low latency. |
| **Axios** | HTTP Client | Handling API requests from the frontend to the Express backend. | Provides a robust, promise-based HTTP library for clean and reliable network operations. |
| **Tailwind CSS** | Styling Utility | Utility-first CSS framework used for rapid and consistent styling across all components. | Accelerates development of custom, responsive designs directly within components. |
| **Vite** | Frontend Build Tool | Bundling and serving the React application with incredibly fast hot module reloading. | Chosen for its performance and modern approach to frontend tooling, using native ES modules. |

---

## 📁 Project Structure

The codebase is organized into distinct frontend and backend repositories, reflecting the Component-based Architecture and REST API design. This structure facilitates independent development and deployment of both client and server components.

```
📂 Samanvi04-Chatly-79f5a3d/
├── 📂 backend/                      # Express.js Server Logic and API implementation
│   ├── 📄 package-lock.json         # Locked backend dependencies
│   ├── 📄 package.json              # Backend dependencies and scripts
│   ├── 📄 git.lock                  # Repository lock file
│   ├── 📂 .gitignore/
│   │   └── 📄 .env                  # Environment variable file ignored by Git
│   └── 📂 src/                      # Backend Source Code
│       ├── 📄 index.js              # Main server entry point
│       ├── 📂 middleware/
│       │   └── 📄 auth.middleware.js# Express middleware for user authentication and protection
│       ├── 📂 models/               # Data schema definitions
│       │   ├── 📄 user.model.js     # Schema for user data
│       │   └── 📄 message.model.js  # Schema for chat messages
│       ├── 📂 seeds/
│       │   └── 📄 user.seed.js      # Seed data for initial user population
│       ├── 📂 controllers/          # Business logic handlers for API routes
│       │   ├── 📄 message.controller.js # Logic for sending and retrieving messages
│       │   └── 📄 auth.controller.js  # Logic for user registration and login
│       ├── 📂 routes/               # API route definitions
│       │   ├── 📄 auth.route.js     # Routes for authentication (login, signup, etc.)
│       │   └── 📄 message.route.js  # Routes for chat message operations
│       └── 📂 lib/                  # Backend utility libraries
│           ├── 📄 uttils.js         # General utility functions
│           ├── 📄 db.js             # Database connection setup
│           ├── 📄 cloudinary.js     # External integration utility (Verified but service is not set up)
│           └── 📄 socket.js         # Real-time socket configuration
│
└── 📂 frontend/                     # React Application and User Interface
    ├── 📄 package-lock.json         # Locked frontend dependencies
    ├── 📄 package.json              # Frontend dependencies and scripts
    ├── 📄 vite.config.js            # Vite build configuration file
    ├── 📄 index.html                # Main entry point for the browser application
    ├── 📄 README.md                 # Frontend-specific documentation
    ├── 📄 .gitignore                # Git ignore rules for the frontend
    ├── 📄 eslint.config.js          # ESLint configuration for code quality
    ├── 📂 public/                   # Static assets
    │   ├── 📄 avatar.png            # Default avatar image
    │   ├── 📄 image.png             # Placeholder image
    │   └── 📄 vite.svg              # Vite logo asset
    └── 📂 src/                      # Frontend Source Code
        ├── 📄 App.css               # Global application styles
        ├── 📄 index.css             # Root styles
        ├── 📄 App.jsx               # Main application component
        ├── 📄 main.jsx              # Application entry point (ReactDOM rendering)
        ├── 📂 constants/
        │   └── 📄 index.js          # Global constants and configuration values
        ├── 📂 pages/                # Top-level application routes/views
        │   ├── 📄 LoginPage.jsx     # User login view
        │   ├── 📄 SignUpPage.jsx    # User registration view
        │   ├── 📄 SettingsPage.jsx  # User settings view
        │   ├── 📄 ProfilePage.jsx   # User profile view
        │   └── 📄 HomePage.jsx      # Main chat and application dashboard view
        ├── 📂 store/                # Zustand state management stores
        │   ├── 📄 useChatStore.js   # State management for chat interactions and data
        │   ├── 📄 useAuthStore.js   # State management for authentication status
        │   └── 📄 useThemeStore.js  # State management for theme and UI settings
        ├── 📂 lib/                  # Frontend utility libraries
        │   ├── 📄 axios.js          # Centralized configuration for Axios HTTP client
        │   └── 📄 utils.js          # General frontend utility functions
        └── 📂 components/           # Reusable UI components
            ├── 📄 ChatHeader.jsx    # Component displaying chat partner info
            ├── 📄 Sidebar.jsx       # Component for displaying user lists/contacts
            ├── 📄 Navbar.jsx        # Navigation bar component
            ├── 📄 AuthImagePattern.jsx # Pattern/design element for auth pages
            ├── 📄 NoChatSelected.jsx # Component displayed when no chat is active
            ├── 📄 MessageInput.jsx  # Input area for sending messages
            ├── 📄 ChatContainer.jsx # Main container displaying message history
            └── 📂 skeletons/        # Loading state components
                ├── 📄 MessageSkeleton.jsx # Placeholder for loading message threads
                └── 📄 SidebarSkeleton.jsx # Placeholder for loading sidebar contacts
```

---

## 🚀 Getting Started

This guide outlines the steps necessary to get Chatly running locally. Due to the distinct separation of the frontend and backend, the setup requires configuration in both directories.

### Prerequisites

To run this project, you will need a stable environment for Node.js and a package manager.

*   Node.js (LTS version recommended)
*   A package manager (npm, yarn, or pnpm)

### Installation

Since the project uses standard Node.js configurations (`package.json` in both directories), the installation follows typical procedures, starting with cloning the repository.

1.  **Clone the Repository**

    ```bash
    git clone https://github.com/Samanvi04/Chatly-79f5a3d.git
    cd Samanvi04-Chatly-79f5a3d
    ```

2.  **Install Backend Dependencies**

    Navigate to the `backend` directory and install the necessary Node modules for the Express server.

    ```bash
    cd backend
    npm install # or yarn install
    ```

3.  **Install Frontend Dependencies**

    Navigate to the `frontend` directory and install the dependencies required for the React application.

    ```bash
    cd ../frontend
    npm install # or yarn install
    ```
    
4.  **Configuration Note**

    No specific environment variables were detected in the analysis. However, a file named `.env` is ignored by git in the backend, suggesting that configuration (such as port numbers, database URLs, or secret keys) is typically managed here. Before launching, ensure you create this file based on typical application needs (e.g., `PORT=5000`, `MONGO_URI='...'`) to prevent runtime configuration errors.

### Launching the Application

As no verified scripts (`dev`, `start`) were provided in the analysis, we rely on standard community conventions to launch the dual-architecture application.

1.  **Start the Backend Server**
    The backend entry point is `src/index.js`. Standard Express applications typically run via a script defined in `package.json` (e.g., `node src/index.js`).

    ```bash
    # Execute the server entry file
    # Replace 'node' with the appropriate runner if using nodemon or similar tools
    node src/index.js
    ```
    The server should now be listening for connections.

2.  **Start the Frontend Client**
    The frontend uses Vite. Standard Vite projects use the `dev` script for local development.

    ```bash
    # Navigate back to the frontend directory if you left it
    # cd frontend
    
    # Run the development script detected in package.json
    npm run dev
    # OR
    yarn dev
    ```

The frontend application should automatically open in your browser, providing the interactive user interface.

---

## 🔧 Usage

Chatly operates as a **web application** (`web_app`) accessed through a standard web browser.

### Application Workflow

1.  **Access:** Once the frontend server is running (typically on `http://localhost:5173` if using Vite defaults), navigate to the application URL.
2.  **Authentication:** Users must navigate to the `SignUpPage.jsx` or `LoginPage.jsx` to establish an authenticated session. This interaction is handled by the `auth.controller.js` on the backend.
3.  **Core Messaging:** After logging in, the user is redirected to the `HomePage.jsx`, which loads the `Sidebar.jsx` (contact list) and the main `ChatContainer.jsx`.
4.  **Interaction:** Users select a chat partner from the Sidebar. The `MessageInput.jsx` allows text entry, and upon sending, messages are processed through the backend via the `message.controller.js`. The `useChatStore.js` ensures the UI updates instantly with new messages.

### API Interaction

The backend API is structured to handle requests crucial for the web application's operation.

#### Catch-All Endpoint (`GET *`)

The analysis detected a single catch-all endpoint: `GET *`. In Express applications, this is commonly used to:
1.  Serve static files (like the built frontend application).
2.  Provide a fallback for client-side routing, ensuring that all unhandled routes default to rendering the primary application shell (`index.html`), allowing React Router to manage the internal application routes (`LoginPage`, `ProfilePage`, etc.).

**How the User Interacts with the API:**
*   All user actions (login attempts, message sending, profile updates) trigger dedicated, internal RESTful API calls managed by the application's Axios configuration (`lib/axios.js`). These calls interact with the specific route definitions (`auth.route.js`, `message.route.js`) which are layered above the base `GET *` functionality.

---






<p align="center">
  <a href="#">⬆️ Back to Top</a>
</p>
