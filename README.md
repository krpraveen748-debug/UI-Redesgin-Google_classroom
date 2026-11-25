# UI-Redesgin-Google_classroom

## Abstract
**UI-Redesgin-Google_classroom** is a modern, responsive web application that reimagines the Google Classroom learning management system (LMS). Built with React, TypeScript, Vite, Tailwind CSS, and `shadcn/ui`, the platform streamlines course management, assignment tracking, classroom streams, and student-educator collaboration into a fast, accessible, and distraction-free interface.

---

## Problem Statement
Conventional learning management interfaces often suffer from visual clutter, fragmented navigation, and multi-step workflows that make it difficult for students and instructors to track upcoming deadlines, announcements, and course materials across multiple subjects. This project addresses those usability bottlenecks by consolidating daily academic tasks into a clean, modular, card-based single-page application (SPA).

---

## Objectives
- **Unified Course Dashboard:** Present all enrolled and taught courses in a clean, scannable grid with immediate visibility into pending work.
- **Streamlined Classroom Workflows:** Organize announcements, classwork, grades, and participant rosters into intuitive, single-click tabs.
- **Modern Design System:** Implement consistent typography, accessible color contrast, and responsive layouts using Tailwind CSS and `shadcn/ui`.
- **High-Speed Client Performance:** Deliver instant page transitions and hot-module replacement (HMR) using Vite and TypeScript.
- **Modular & Maintainable Codebase:** Enforce strict TypeScript typing, automated linting (ESLint), code formatting (Prettier), and unit testing (Vitest).

---

## Existing System vs. Proposed System

| Feature | Existing System | Proposed System |
| :--- | :--- | :--- |
| **Navigation** | Multi-page reloads and nested menus to reach assignments | Instant client-side routing with persistent sidebar drawer |
| **Visual Hierarchy** | Dense text feeds where urgent deadlines get buried | Card-based course layout with clear status badges and due dates |
| **Component Architecture** | Monolithic templates with rigid styling | Reusable, accessible UI primitives (`shadcn/ui` + Radix UI) |
| **Responsiveness** | Desktop-first layout with cramped mobile views | Fluid mobile-first grid adapting seamlessly across devices |
| **Developer Tooling** | Manual formatting and limited type safety | Strict TypeScript, ESLint, Prettier, and Vitest test runner |

---

## System Architecture
```text
Browser (Client SPA)
   │
   ├── Routing Layer (Client-Side Views & Layouts)
   ├── UI Component Layer (shadcn/ui + Radix Primitives + Tailwind CSS)
   ├── State & Hook Layer (Custom React Hooks & Local/Mock Data Stores)
   └── Build & Dev Pipeline (Vite + TypeScript + Vitest)
```
All interface rendering, filtering, and navigation occur on the client side for zero-latency user interactions, backed by structured TypeScript models for courses, announcements, assignments, and participants.

---

## Technology Stack
- **Core Framework:** React, TypeScript
- **Build Tool & Dev Server:** Vite (`v8.x`)
- **Styling & Design System:** Tailwind CSS, `shadcn/ui`, Radix UI, Lucide Icons
- **Package Management:** npm / Bun (`bun.lock`, `bunfig.toml`)
- **Testing & Code Quality:** Vitest, ESLint, Prettier

---

## Directory Structure
```text
UI-Redesgin-Google_classroom/
├── .lovable/               # Project configuration metadata
├── public/                 # Static assets, favicons, and public media
├── src/
│   ├── components/         # Reusable UI primitives, navigation bars, and course cards
│   ├── pages/              # Top-level route views (Dashboard, Classroom, Stream, Classwork)
│   ├── hooks/              # Custom React hooks for responsive UI and state logic
│   ├── lib/                # Utility functions, class-name mergers, and formatters
│   └── main.tsx            # Application root and DOM mount entry point
├── .gitignore              # Git exclusion rules (node_modules, dist, logs)
├── .prettierignore         # Files excluded from Prettier formatting
├── .prettierrc             # Prettier code style configuration
├── AGENTS.md               # Workspace architecture and agent guidelines
├── bun.lock                # Bun dependency lockfile
├── bunfig.toml             # Bun runtime configuration
├── components.json         # shadcn/ui component registry configuration
├── eslint.config.js        # ESLint rules and TypeScript linting setup
├── package.json            # Project metadata, dependencies, and npm scripts
├── package-lock.json       # npm dependency lockfile
├── tsconfig.json           # TypeScript compiler options and path aliases
├── vite.config.ts          # Vite bundler, dev server (port 8080), and path plugins
└── vitest.config.ts        # Vitest unit and component test configuration
```

---

## Prerequisites
Verify that **Node.js** and **npm** are installed on your system:
```bash
node -v
npm -v
```
- **Node.js:** `v18.0.0` or higher (tested on `v22.x`)
- **npm:** `v9.0.0` or higher

---

## Installation & Configuration

### 1. Clone the Repository
```bash
git clone https://github.com
cd UI-Redesgin-Google_classroom
```

### 2. Install Dependencies
Use the `--legacy-peer-deps` flag to resolve React peer dependency versions cleanly:
```bash
npm install --legacy-peer-deps
```

### 3. Configuration Defaults
- **Development Server Port:** `8080` (configured in `vite.config.ts`)
- **Path Aliases:** `@/` maps directly to `./src/` via `tsconfig.json` and `vite.config.ts`
- **UI Theme Tokens:** Configured via Tailwind CSS and `components.json`

---

## Running the Application

### Start Development Server
```bash
npm run dev
```
Open **`http://localhost:8080`** in your web browser.

### Available Scripts
- **Build for Production:**
  ```bash
  npm run build
  ```
- **Preview Production Build:**
  ```bash
  npm run preview
  ```
- **Run Unit & Component Tests:**
  ```bash
  npm test
  ```
- **Run ESLint Checks:**
  ```bash
  npm run lint
  ```

---

## Core Modules & Features
1. **Course Overview Grid:** Displays subject cards with instructor details, theme banners, and quick-action shortcuts for assignments and folders.
2. **Interactive Class Stream:** Centralized feed for instructor announcements, class discussions, and material attachments.
3. **Classwork & Topic Organizer:** Structured breakdown of assignments, quizzes, and reference materials grouped by module or topic with clear due-date indicators.
4. **To-Do & Deadline Tracker:** Consolidated view of upcoming, missing, and completed tasks across all enrolled courses.
5. **People & Roster Management:** Clean directory separating teachers/instructors from enrolled students.
6. **Collapsible Navigation Drawer:** Quick switching between Home, Calendar, To-Do, Enrolled Classes, and Archived Courses.

---

## User Workflows

### Student Workflow
1. **Dashboard:** Review all enrolled classes and check upcoming assignment deadlines on course cards.
2. **Enter Classroom:** Select a course card to view the latest announcements in the **Stream** tab.
3. **Complete Classwork:** Switch to the **Classwork** tab, open an assignment, review instructions/rubrics, and track submission status.
4. **Global To-Do:** Use the sidebar drawer to filter pending work across every subject in one place.

### Educator / Instructor Workflow
1. **Course Management:** Access taught courses from the main dashboard grid.
2. **Post Updates:** Publish announcements or schedule posts directly within the course stream.
3. **Organize Materials:** Group assignments and study resources under structured topics in **Classwork**.
4. **Roster Overview:** View and manage enrolled students and co-teachers under the **People** tab.

---

## Deployment
This application compiles into static HTML, CSS, and JavaScript assets inside the `dist/` directory when running `npm run build`. It can be deployed directly to:
- **Vercel:** Import the GitHub repository, set the install command to `npm install --legacy-peer-deps`, and deploy automatically.
- **Netlify:** Connect the repository with build command `npm run build` and publish directory `dist`.

---

## Troubleshooting
- **`npm install` peer dependency conflict (`ERESOLVE`):** Always install packages using `npm install --legacy-peer-deps` or `rm -rf node_modules package-lock.json && npm install --legacy-peer-deps`.
- **`vite: not found` when running `npm run dev`:** Ensure dependencies finished installing completely without interruption (`Ctrl + C`) and verify sufficient free disk space (`df -h`).
- **Port `8080` already in use:** Stop any running terminal processes using `Ctrl + C` or specify a custom port with `npm run dev -- --port 3000`.
