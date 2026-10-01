# Marketly — E-Commerce Web Application

Full-stack internship demo built with React + Vite, Node.js + Express, and MySQL.

## Features
- Product catalogue, category filters, and search
- Shopping bag and quantity controls
- User registration and login (bcrypt password hashing, JWT sessions)
- User/admin roles
- Admin product add, edit, and delete
- Checkout demo using cash on delivery (no real payment processing)
- Order history, order status updates, and stock tracking
- Responsive layout for desktop and mobile

## Requirements
Node.js 18+, npm, and MySQL 8+ (or compatible).

## Run locally
1. Create the database in MySQL:
   ```sql
   CREATE DATABASE marketly_db;
   ```
2. In this folder, install dependencies:
   ```bash
   npm install
   ```
3. Copy `.env.example` to `.env` and enter your MySQL password and a private JWT secret.
   - Windows CMD: `copy .env.example .env`
   - macOS/Linux: `cp .env.example .env`
4. Configure `ADMIN_EMAIL` and `ADMIN_PASSWORD` in `.env` for the initial admin account. Change the example password before use.
5. Start the backend in one terminal:
   ```bash
   npm run server
   ```
   Tables and sample products are created automatically.
6. Start the frontend in a second terminal:
   ```bash
   npm run dev
   ```
7. Open the Vite URL, normally http://localhost:5173.

## Production
Run `npm run build`, then `npm start`. Configure the database variables, `JWT_SECRET`, and `PORT` in the hosting provider. The Express server serves the built frontend and API from one origin.

## API routes
- `GET /api/health`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/products`
- `POST /api/products` (admin)
- `PUT /api/products/:id` (admin)
- `DELETE /api/products/:id` (admin)
- `POST /api/orders` (authenticated)
- `GET /api/orders` (authenticated; admins see all)
- `PATCH /api/orders/:id/status` (admin)

Do not commit `.env`. The checkout is a demo only and does not collect payment details.
