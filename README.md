# PPT Presentation Management Web Application

Full-stack PPT management system for a college with Email OTP authentication, role-based access, and secure PPT distribution.

## Tech Stack
- Frontend: React + Vite
- Backend: Node.js + Express
- Database: MongoDB
- Auth: Email OTP + JWT
- Storage: Local `server/uploads/`

## Project Structure
```
frontend (root)
  src/
    components/
    pages/
    services/
    App.jsx
    main.jsx
    index.css
backend
  server/
    routes/
    controllers/
    models/
    middleware/
    uploads/
    server.js
```

## Setup

### 1) Backend
```
cd server
npm install
```
Create `server/.env` from `server/.env.example` and update values.

Run:
```
npm run dev
```

### 2) Frontend
```
npm install
```
Create `.env` from `.env.example` and update values.

Run:
```
npm run dev
```

## Email OTP Setup
- Configure `ZEPTOMAIL_TOKEN` and `EMAIL_FROM` in `server/.env`.
- Optional: set `ZEPTOMAIL_API_URL` (default `https://api.zeptomail.in/v1.1/email`) and `EMAIL_FROM_NAME`.
- Use a verified sender email/domain in ZeptoMail for `EMAIL_FROM`.
- Set `JWT_SECRET` in `server/.env` for token signing.

## Roles & Permissions
- Admin: manage users, subjects, classes, assignments, PPTs.
- Faculty: upload PPTs only for assigned subjects, view students and PPTs.
- Student: view assigned subjects and download PPTs.

## Notes
- Roles are assigned automatically from email:
  - contains `admin` -> Admin
  - contains `faculty` -> Faculty
  - otherwise -> Student
- PPT/PPTX only.

## Scripts
- Frontend: `npm run dev`, `npm run build`
- Backend: `npm run dev`, `npm run start`
