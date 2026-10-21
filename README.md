# HOTEL-MANAGEMENT-SYSTEM
A modern, full-stack Hotel Management System built with React, TypeScript, and Tailwind CSS. Features role-based access, room management, booking &amp; reservation tracking, guest management, and billing/invoicing.
# Grand Horizon Resort — Hotel Management System

A full-featured hotel management web application for a single property. Staff sign in to manage rooms, reservations, guests, and billing, while guests use a public booking page to submit booking requests.

Built with **React + TypeScript + Vite**, styled with **Tailwind CSS**, and powered by **Bolt Database** (Postgres database, authentication, and row-level security).

---

## 🌟 Features

### 👤 Staff Dashboard (Sign-in required)
* **Dashboard** — Overview of the resort with key metrics and quick navigation.
* **Room Management** — Manage rooms, room types (Standard / Deluxe / Suite), pricing, capacity, amenities, and live status (available, occupied, cleaning, maintenance).
* **Reservations** — Create and track bookings, check-ins, and check-outs with guest and room details.
* **Guests** — Guest profiles with contact info, ID details, and stay history.
* **Billing & Invoices** — Generate invoices with room charges, taxes, service charges, and line items; mark invoices as paid.

### 🌐 Public Access
* View available room types and submit a booking request without signing in. Staff can later approve or reject these requests.

### ⚙️ Platform & Infrastructure
* **Authentication** — Email/password staff login via Bolt Database Auth.
* **Row-Level Security (RLS)** — Every table is RLS-protected; public data is read-only, staff data is authenticated-only.
* **Dark / Light Theme** — Toggle persisted across sessions.
* **Responsive Design** — Works seamlessly from mobile to desktop with a collapsible sidebar.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React 18, TypeScript, Vite |
| **Styling** | Tailwind CSS (Custom color system, Dark mode) |
| **Icons** | Lucide React (`lucide-react`) |
| **Backend** | Bolt Database (Postgres, Auth, RLS) |
| **Fonts** | Inter (sans), Playfair Display (serif) |

---

## 📁 Project Structure

```text
.
├── src/
│   ├── App.tsx                  # Root app, routing, layout
│   ├── main.tsx                 # Entry point
│   ├── index.css                # Tailwind directives + base styles
│   ├── context/
│   │   ├── AuthContext.tsx      # Bolt Database session provider
│   │   └── ThemeContext.tsx     # Dark/light theme provider
│   ├── lib/
│   │   ├── supabase.ts          # Bolt Database client
│   │   └── utils.ts             # Shared helpers
│   ├── pages/
│   │   ├── LoginPage.tsx
│   │   ├── DashboardPage.tsx
│   │   ├── RoomsPage.tsx
│   │   ├── ReservationsPage.tsx
│   │   ├── GuestsPage.tsx
│   │   ├── BillingPage.tsx
│   │   └── PublicBookingPage.tsx
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Sidebar.tsx
│   │   │   └── Topbar.tsx
│   │   └── ui/
│   │       ├── Modal.tsx
│   │       ├── StatusBadges.tsx
│   │       ├── Toast.tsx
│   │       └── ToastProvider.tsx
│   └── types/
│       └── index.ts             # Shared TypeScript types
├── supabase/
│   └── migrations/
│       ├── 20261021074830_hotel_management_schema.sql   # Tables + RLS
│       ├── 20261021075002_seed_hotel_data.sql           # Seed data
│       └── 20261021075055_create_demo_auth_users_v2.sql # Demo logins
├── tailwind.config.js
├── vite.config.ts
└── package.json
