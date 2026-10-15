# CodeNid (BuildLog Social) 🚀

CodeNid is a full-stack, community-driven social platform for student developers, builders, and college campuses. Built with **React Native / Expo** (Web & Mobile), a **Node.js Express** backend, and **Supabase** for database, auth, storage, and realtime communication.

---

## 🌟 Key Features

- **Project Feed & Dev News**: Share proof-of-work build logs, track day streaks, and read curated tech news.
- **Campus Tavern (Real-time Hub)**: Live department chat rooms (CS, IT, Mech, Civil, etc.) with real-time presence indicators, member directories, and room creation.
- **Campus Leaderboard ("Rank")**: Real-time rankings for builders across campus communities.
- **Challenges & Streaks**: Challenge manager, daily build streaks, and milestone achievements.
- **Interactive Problem Solver**: AI-assisted programming problem explorer and guidance.
- **Admin Dashboard**: Dedicated Vite + React administration panel to manage reports, users, and campus hubs.

---

## 🏗️ Architecture & Monorepo Structure

```text
buildlog_social/
├── app/                  # Expo Router file-based pages (tabs, auth, stack routes)
├── components/           # Reusable UI components, skeletons, navigation sidebar
├── services/             # Client-side API and backend integration services
├── store/                # Zustand global state (user profile, auth sync)
├── lib/                  # Supabase client, notifications, analytics helpers
├── server/               # Node.js + Express backend (Cron jobs, Web Push, Chat socket)
├── admin-panel/          # Vite + React Admin Dashboard
├── supabase/             # Schema definitions and database migrations
└── .env.example          # Environment variable templates
```

---

## ⚙️ Getting Started

### 1. Prerequisites
- [Node.js](https://nodejs.org/) (v18 or v20 recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- A [Supabase](https://supabase.com/) project

### 2. Environment Setup

#### Client App (Root)
Create a `.env` file in the root directory:
```env
EXPO_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
EXPO_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
EXPO_PUBLIC_BACKEND_URL=http://localhost:5000
```

#### Backend Server (`/server`)
Create `server/.env`:
```env
PORT=5000
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-service-role-key
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
VAPID_PUBLIC_KEY=your_vapid_public_key
VAPID_PRIVATE_KEY=your_vapid_private_key
```

#### Admin Panel (`/admin-panel`)
Create `admin-panel/.env`:
```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
VITE_SUPABASE_SERVICE_KEY=your-service-role-key
```

---

### 3. Installation & Running

#### Start the Client App (Expo Web / Mobile)
```bash
npm install
npm run start
# Press 'w' to open in browser (http://localhost:8081)
```

#### Start the Backend Server
```bash
cd server
npm install
npm run start   # runs on port 5000
```

#### Start the Admin Panel
```bash
cd admin-panel
npm install
npm run dev     # runs Vite dev server
```

---

## 🧪 Quality Checks

- **TypeScript Compilation**: `npx tsc --noEmit`
- **Linting**: `npm run lint`

---

## 🔒 Security Note

All `.env` files and private credentials (`vapid.json`) are strictly excluded by `.gitignore` and must never be committed to source control.
