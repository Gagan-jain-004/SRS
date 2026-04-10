# SRS - Student Registration & Attendance System

A Next.js application for managing placement/recruitment student registration and QR-based attendance tracking.

## Overview

SRS helps a placement cell team:

- Register students for events/recruitments
- Generate a unique QR scan link for each student
- Mark attendance from an admin scanner flow
- View student and admin dashboards
- Send registration/invitation related emails

## Core Features

- Student registration pages and forms
- QR-based attendance workflow (`/scan/[userId]`)
- Admin authentication with JWT cookie
- Admin scanner/review pages for attendance handling
- Student dashboard views
- Recruiter invitation email flow
- MongoDB persistence with Mongoose models

## Tech Stack

- Next.js 13 (App Router)
- React 18 + TypeScript
- Tailwind CSS + shadcn/ui components
- MongoDB + Mongoose
- JWT authentication
- Nodemailer (Gmail transport)

## Project Structure

- `app/` - Routes, pages, API route, and server actions
- `components/` - Reusable UI and feature components
- `hooks/` - Client hooks (scanner, toast)
- `lib/` - Auth, DB, email, utility modules
- `mail/` - HTML email templates
- `models/` - Mongoose schemas/models
- `public/` - Static assets

## Prerequisites

- Node.js 18+
- npm
- MongoDB (local or cloud)
- A Gmail account/app password (for email sending)

## Getting Started

1. Install dependencies:

   npm install

2. Create an environment file in project root:

   File: `.env.local`

   Required variables:

   - `MONGODB_URI=mongodb://localhost:27017/ptp`
   - `JWT_SECRET=replace-with-a-secure-random-secret`
   - `ADMIN_USERNAME=admin@rtu`
   - `ADMIN_PASSWORD=rtu@superadmin@2025`
   - `NEXT_PUBLIC_APP_URL=http://localhost:3000`
   - `EMAIL_USER=your-email@gmail.com`
   - `EMAIL_PASS=your-gmail-app-password`

3. Run development server:

   npm run dev

4. Open in browser:

   http://localhost:3000

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Create production build
- `npm run start` - Run production server
- `npm run lint` - Run Next.js lint checks

## Key Routes

- `/` - Landing page
- `/student-register` - Student registration
- `/student-dashboard` - Student dashboard
- `/dashboard` - Core dashboard
- `/login` - Admin login
- `/admin/scanner` - Admin scanner
- `/admin/scanner/review` - Scanner review
- `/scan/[userId]` - Attendance scan endpoint page
- `/send-mail` - Recruiter invitation flow

## Authentication Notes

- Admin sessions use a cookie named `auth-token`.
- Middleware protects `/admin/*` routes.
- JWT token role check is used for admin authorization.

## Deployment Notes

For deployment platforms (for example Vercel):

- Configure all environment variables in platform settings.
- Set `NEXT_PUBLIC_APP_URL` to the deployed domain.
- Ensure MongoDB network access allows your deployment.
- If using Gmail SMTP, use an app password and allow SMTP access.

## Troubleshooting

- If MongoDB connection fails, verify `MONGODB_URI` and database access.
- If login fails, verify `ADMIN_USERNAME` and `ADMIN_PASSWORD` values.
- If emails fail, verify Gmail credentials and app password configuration.
- If scan links are wrong, verify `NEXT_PUBLIC_APP_URL`.

## License

This project currently has no explicit license file. Add one if you plan to distribute it publicly.
