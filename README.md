
-----

# CorpoVinculo 🌐

This repository holds the entire application stack for **CorpoVinculo**, also branded as **IndustryConnect**. This platform is a centralized, role-based system designed to streamline sponsorship management and industry outreach for IEEE student branches and sub-clubs.

-----

## 1\. Project Overview

### The Problem

IEEE student branches face major inefficiencies, relying on fragmented tools (Google Sheets, Excel), leading to **duplicate outreach**, **poor coordination**, time-consuming manual communication, and a **lack of volunteer accountability**.

### The Solution

IndustryConnect provides a single source of truth for all outreach activities.

### Core System Features (MVP)

  * **Centralized Company Tracker:** A unified database of company contacts accessible across all sub-clubs.
  * **Role-Based Access Control (RBAC):** Secure access based on roles (Chairperson, IO Lead, Volunteer, etc.).
  * **AI-Powered Generator:** Creates standardized, professional proposals and outreach emails.
  * **Automated Reminders:** System to track follow-ups and pending company responses.
  * **Volunteer Dashboard:** Tracks and monitors individual contributions and activity.

-----

## 2\. Architecture and Technical Stack

The application follows a **Layered Architecture** with distinct Frontend and Backend components.

### Frontend 💻 (Client-Side)

| Category | Technology | Role |
| :--- | :--- | :--- |
| **Framework** | **React Web** / **React Native** | User Interface and Interaction. |
| **Styling** | *[Insert CSS/UI Framework here, e.g., Tailwind CSS]* | Consistent and responsive design. |
| **State Management** | *[Insert State Management here, e.g., Redux, Context]* | Managing complex UI state. |

### Backend ⚙️ (Server-Side & Data)

| Category | Technology | Role |
| :--- | :--- | :--- |
| **Runtime** | **Node.js** | Executes server-side code. |
| **Framework** | **Express.js** | API Gateway/Router and handling HTTP requests. |
| **Database** | **MongoDB / Atlas** | Persistent data storage (NoSQL). |
| **ORM/ODM** | **Mongoose** | Provides data modeling for MongoDB. |

-----

## 3\. Getting Started

### Prerequisites

  * **Node.js** (LTS version recommended)
  * **npm** or **yarn**
  * Access to a **MongoDB instance** (local or Atlas)

### Installation and Setup

1.  **Clone the repository:**

    ```bash
    git clone [Your Repository URL]
    cd [repository-folder-name]
    ```

2.  **Install dependencies for all components:**
    *(Assuming a common package manager command for a monorepo setup or running `npm install` in both directories.)*

    ```bash
    npm install # or yarn install (Run in root, then in 'frontend' and 'backend' directories if not a true monorepo)
    ```

3.  **Configure Environment Variables (Backend):**
    Create a `.env` file in the **`./backend`** directory.

    ```
    # .env for Backend
    PORT=3001
    MONGO_URI=mongodb+srv://<user>:<password>@<cluster-url>/corpo-vinculo-db?retryWrites=true&w=majority
    JWT_SECRET=your_jwt_secret_key
    ```

4.  **Configure Environment Variables (Frontend):**
    Create a `.env` file (e.g., `.env.local` or `.env`) in the **`./frontend`** directory.

    ```
    # .env for Frontend
    REACT_APP_API_BASE_URL=http://localhost:3001 # Must point to the backend server
    ```

5.  **Run the application:**
    Start the backend server first:

    ```bash
    # In the ./backend directory
    npm start 
    ```

    Then, start the frontend application:

    ```bash
    # In the ./frontend directory
    npm start 
    ```

    The frontend should be accessible at `http://localhost:3000` (default) and communicate with the backend on port `3001`.

-----

## 4\. API Endpoint Overview

The backend exposes a RESTful API. All endpoints are protected by **Role-Based Access Control** (RBAC) and require a valid JWT token, except for the initial company inquiry endpoint.

| Module | Method | Endpoint | Description | Auth Required |
| :--- | :--- | :--- | :--- | :--- |
| **Users** | `GET`/`POST` | `/users` | Authentication and user profile management. | Yes |
| **Permissions** | `POST` | `/user-permissions` | Configure access rights (R/W/U/D/A) for roles. | Yes |
| **Companies** | `GET`/`POST` | `/companies` | CRUD operations for the Centralized Company Tracker. | Yes |
| **Inquiries** | `POST` | `/inquiries` | **Create Inquiry** for new company contact submissions. | **No** |
| **Events** | `POST` | `/events` | Create and manage IEEE events. | Yes |
| **Proposals** | `POST` | `/proposals` | Upload and approval flow for proposals. | Yes |
| **SaaS Payments**| `GET` | `/saas-payments` | Track subscription status for reporting. | Yes |

-----

## 5\. Contact

Team Name: **CorpoVinculo**

Team Members: Delaksan Sritharan
