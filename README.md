# CoderHouse: Voice-Based Social Networking App

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Actions](#actions)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
CoderHouse is a voice-based social networking application that facilitates real-time audio interactions among users. The app leverages WebRTC technology to ensure low-latency communication, creating an engaging platform for users to connect and share experiences.

## Features
- **User Authentication**: Secure login and registration process with OTP verification.
- **Real-Time Audio Communication**: Low-latency audio streaming using WebRTC for seamless interactions.
- **Scalable Architecture**: Built with Docker for containerization and deployed on AWS for enhanced scalability and reliability.
- **User Engagement**: High-quality audio communication leading to increased participation and user satisfaction.

## Tech Stack
- **Frontend**: React.js, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Real-Time Communication**: WebRTC, Socket.IO
- **Containerization**: Docker
- **Cloud Hosting**: AWS

## Project Structure

### Directory Descriptions:
- **frontend/**: This folder contains the frontend code, built using React.js and Tailwind CSS, handling the user interface and client-side logic.
- **backend/**: The main backend server, built using Node.js and Express.js, managing API requests and real-time communication.
- **actions/**: This folder defines the actions used for managing real-time interactions:
    - `JOIN`: Join a voice channel.
    - `LEAVE`: Leave a voice channel.
    - `ADD_PEER`: Add a new peer to the communication session.
    - `REMOVE_PEER`: Remove a peer from the session.
    - `RELAY_ICE`: Relay ICE candidates between peers.
    - `RELAY_SDP`: Relay session descriptions between peers.
    - `SESSION_DESCRIPTION`: Handle session descriptions.
    - `ICE_CANDIDATE`: Handle ICE candidates.
    - `MUTE`: Mute a user.
    - `UNMUTE`: Unmute a user.
    - `MUTE_INFO`: Information regarding mute status.

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/athsb009/coderhouse.git
    ```

2. **Navigate to the project directory**:
    ```bash
    cd coderhouse
    ```

3. **Install dependencies for both frontend and backend**:
    ```bash
    cd frontend && npm install
    cd ../backend && npm install
    ```

4. **Set up environment variables**:
   Create a `.env` file in both the `frontend` and `backend` directories and add the necessary keys (e.g., `DB_URL`, `JWT_SECRET`, etc.).

5. **Run Docker containers for backend services**:
    ```bash
    docker-compose up
    ```

6. **Start the development servers**:
    - For frontend:
    ```bash
    cd frontend && npm run dev
    ```
    - For backend:
    ```bash
    cd backend && npm run dev
    ```

## Usage
Once the development servers are running:
1. Access the app at `http://localhost:3000` (frontend).
2. Sign up or log in.
3. Join a voice channel and start communicating with other users in real-time.

## API Endpoints
### Authentication Endpoints
- `POST /api/send-otp`: Send an OTP to the user's email/phone for verification.
- `POST /api/verify-otp`: Verify the OTP entered by the user.
- `POST /api/activate`: Activate the user account (requires authentication).
- `GET /api/refresh`: Refresh the user authentication token.
- `POST /api/logout`: Log out the user (requires authentication).

### Room Management Endpoints
- `POST /api/rooms`: Create a new room (requires authentication).
- `GET /api/rooms`: Fetch all rooms (requires authentication).
- `GET /api/rooms/:roomId`: Fetch details of a specific room by ID (requires authentication).

### Test Endpoint
- `GET /api/test`: Simple endpoint to test API connectivity.

### WebSocket Events
- **WebSocket Events for Real-Time Communication**:
  - `join`: User joins a voice channel.
  - `leave`: User leaves a voice channel.
  - `add-peer`: Adds a new peer to the session.
  - `remove-peer`: Removes a peer from the session.
  - `relay-ice`: For relaying ICE candidates.
  - `relay-sdp`: For relaying session descriptions.
  - `session-description`: Handles session descriptions.
  - `ice-candidate`: Handles ICE candidates.
  - `mute`: Mute a user.
  - `unmute`: Unmute a user.
  - `mute-info`: Information about mute status.

## Contributing
We welcome contributions! To contribute:
1. Fork the repository.
2. Create a new branch:
    ```bash
    git checkout -b feature-name
    ```
3. Make your changes and commit:
    ```bash
    git commit -m "Add new feature"
    ```
4. Push to your branch:
    ```bash
    git push origin feature-name
    ```
5. Submit a pull request, and we will review it.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

