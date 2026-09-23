# Vue + Express + TypeScript Simple Starter

A minimal full-stack project with:
- **Frontend**: Vue 3 + TypeScript + Vite
- **Backend**: Express.js + TypeScript

## Project Structure

```
vue-express-ts-simple/
├── client/          # Vue frontend
├── server/          # Express API
└── package.json     # Root scripts
```

## Getting Started

### 1. Install dependencies

```bash
# Root (optional, for concurrent scripts)
npm install

# Frontend
cd client && npm install

# Backend
cd ../server && npm install
```

### 2. Run the backend

```bash
cd server
npm run dev
```

API runs at: http://localhost:3000

### 3. Run the frontend

```bash
cd client
npm run dev
```

App runs at: http://localhost:5173

## API Endpoints

| Method | Endpoint     | Description          |
|--------|--------------|----------------------|
| GET    | /api/health  | Health check         |
| GET    | /api/hello   | Simple hello message |

## Scripts

### Root
- `npm run dev` — runs both client and server concurrently (if configured)

### Client
- `npm run dev` — start Vite dev server
- `npm run build` — build for production

### Server
- `npm run dev` — start with ts-node-dev
- `npm run build` — compile TypeScript
- `npm start` — run compiled JS
