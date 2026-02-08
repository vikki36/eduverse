# EduVerse — 3D Interactive Learning Platform

A futuristic full-stack 3D learning platform where knowledge exists as floating interactive portals.

## Features

- **Authentication** — Login, Register with roles (Student, Teacher, Admin)
- **3D Dashboard** — Floating particle background, glass UI, subject portals
- **Subject/Module System** — Explore subjects, complete modules, track progress
- **Quiz System** — Multiple choice quizzes, scores stored in Firestore
- **Analytics** — Progress tracking, quiz averages, learning activity
- **Theme Toggle** — Dark/Light mode
- **Mobile Optimized** — 3D disabled on mobile for performance

## Tech Stack

- React (Vite)
- Tailwind CSS
- Three.js + React Three Fiber
- Framer Motion
- Firebase (Auth, Firestore, Storage)

## Setup

1. **Install dependencies**
   ```bash
   cd eduverse && npm install
   ```

2. **Configure Firebase**
   - Copy `.env.example` to `.env`
   - Add your Firebase project credentials
   - Enable Email/Password auth in Firebase Console
   - Create Firestore database
   - (Optional) Add composite index for `quizzes` collection: `userId` + `submittedAt`

3. **Run**
   ```bash
   npm run dev
   ```

## Project Structure

```
eduverse/
├── src/
│   ├── components/     # Reusable UI (GlassCard, SubjectPortal)
│   ├── pages/          # Login, Register, Dashboard, etc.
│   ├── three/          # Three.js scene, particles, camera
│   ├── firebase/       # Config, Auth, Firestore, Storage
│   ├── hooks/          # useTheme, useIsMobile
│   ├── data/           # Sample subjects, quizzes
│   └── utils/          # Constants
├── public/
└── package.json
```

## Firestore Structure

- `users/{userId}` — email, role, progress, quizzes[]
- `quizzes/{quizId}` — userId, moduleId, score, answers, submittedAt

## Future Ready

Architecture supports: AI tutor, VR mode, multiplayer learning rooms.
