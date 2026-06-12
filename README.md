# ChatterFlow

A full-stack real-time chat application built with React, Vite, Tailwind CSS, Express, MongoDB, Socket.io, and Cloudinary.

## Features

- User authentication: sign up, log in, and log out
- Profile editing with avatar upload via Cloudinary
- Real-time messaging with Socket.io
- Online user presence indicator
- Themed chat UI with persistent theme selection
- Protected routes for authenticated access
- Backend API with JWT cookie authentication

## Project structure

- `backend/` - Express server, MongoDB models, authentication, message API, Socket.io
- `frontend/` - React + Vite chat UI, authentication pages, profile/settings flows
- `package.json` - root scripts for install, build, and start

## Setup

### 1. Install dependencies

Run the following from the repository root:

```bash
npm install --prefix backend
npm install --prefix frontend
```

### 2. Configure environment variables

Create a `.env` file in `backend/` with the following values:

```env
PORT=5001
MONGODB_URL=<your-mongodb-connection-string>
JWT_SECRET=<your-jwt-secret>
CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
CLOUDINARY_API_KEY=<your-cloudinary-api-key>
CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
FRONTEND_URL=http://localhost:5173
```

For the frontend, you can optionally create a `.env` file in `frontend/` if you need custom API/socket URLs:

```env
VITE_API_URL=http://localhost:5001/api
VITE_SOCKET_URL=http://localhost:5001
```

## Development

Start the backend and frontend servers in separate terminals:

```bash
cd backend
npm run dev
```

```bash
cd frontend
npm run dev
```

Then open the frontend URL shown by Vite (usually `http://localhost:5173`).

## Production build

Build the frontend and prepare the app for production from the project root:

```bash
npm run build
```

Then start the backend server:

```bash
npm run start
```

The backend server will serve the production build from `frontend/dist` when `NODE_ENV=production`.

## Useful scripts

- `npm run build` - installs backend/frontend dependencies and builds the frontend
- `npm run start` - starts the backend server
- `npm run dev` (backend only) - starts backend with `nodemon`
- `npm run build` (frontend only) - builds the frontend app
- `npm run dev` (frontend only) - starts the Vite development server

## Notes

- The backend uses HTTP-only cookies for JWT authentication.
- Socket.io is used for live messaging and online-user broadcasts.
- Cloudinary stores uploaded avatars and message images.

## License

This project is provided as-is.

