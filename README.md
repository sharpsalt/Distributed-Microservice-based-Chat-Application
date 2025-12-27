# Distributed Microservice based Chat Application

A real-time chat application with user authentication, profile management, and chat features. Built with Next.js (frontend), TypeScript, Express, and MongoDB (backend, microservices architecture).

---

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [Scripts](#scripts)
- [Tech Stack](#tech-stack)
- [License](#license)

---

## Features
- User authentication (JWT, registration, login)
- Profile management (edit display name, view profile)
- Real-time chat (WebSocket/socket.io)
- Modular backend (user, chat, mail microservices)
- Modern, responsive UI (Tailwind CSS)
- Toast notifications

---

## Project Structure
```
Chat-app/
├── backend/
│   ├── user/      # User service (auth, profile, user DB)
│   ├── chat/      # Chat service (messages, chat rooms)
│   └── mail/      # Mail service (email notifications)
├── frontend/      # Next.js frontend
└── learning.txt   # Setup notes and commands
```

---

## Setup Instructions

### Backend Setup
Each backend service (user, chat, mail) is a separate Node.js/TypeScript project. Repeat these steps for each service:

1. Go to the service folder (e.g. `cd backend/user`)
2. Install dependencies:
   ```bash
   npm install
   ```
3. Configure environment variables (`.env` file as needed)
4. Build TypeScript:
   ```bash
   npm run build
   ```
5. Start the service:
   ```bash
   npm start
   # For development (auto-reload):
   npm run dev
   ```

#### Example `backend/user` setup (from `learning.txt`):
- Initialize project: `npm init -y`
- Install TypeScript globally: `npm i -g typescript`
- Create tsconfig: `npx tsc --init`
- Edit `tsconfig.json` (set `target: es2020`, `rootDir: ./src`, `outDir: ./dist`)
- Create `src/` folder, add code
- In `package.json`, add:
  - `type: "module"` (for ES6)
  - Scripts:
    - `"build": "tsc"`
    - `"start": "node dist/index.js"`
    - `"dev": "concurrently \"tsc -w\" \"nodemon dist/index.js\""`
- Install dependencies:
  ```bash
  npm install express dotenv mongoose
  npm i -D @types/express @types/mongoose @types/dotenv nodemon concurrently
  ```

### Frontend Setup
1. Go to the frontend folder:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```
4. Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Scripts

### Backend (example for user service)
- `npm run build` — Compile TypeScript
- `npm start` — Run built server
- `npm run dev` — Watch & auto-reload (dev)

### Frontend
- `npm run dev` — Start Next.js dev server
- `npm run build` — Build for production
- `npm start` — Start production server

---

## Tech Stack
- **Frontend:** Next.js, React, TypeScript, Tailwind CSS
- **Backend:** Node.js, Express, TypeScript, MongoDB, Mongoose
- **Other:** Socket.io, JWT, dotenv, nodemon, concurrently

---

## License
MIT
