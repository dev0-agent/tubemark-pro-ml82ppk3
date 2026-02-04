# TubeMark Pro

> Curate, annotate, and master your YouTube learning journey.

TubeMark Pro is a dedicated bookmark manager for YouTube videos. It solves the problem of cluttered "Watch Later" lists by allowing you to save videos with specific timestamps, custom context notes, and organizational tags. Built for learners and researchers who need to recall exactly *why* they saved a video.

## Tech Stack

- **Framework:** [TanStack Start](https://tanstack.com/start) (React + SSR)
- **Database:** Drizzle ORM
- **Styling:** Tailwind CSS + shadcn/ui
- **Runtime:** Node.js

## Features

- 🔗 **Smart Parsing:** Auto-extracts video IDs and timestamps from pasted URLs.
- 📝 **Contextual Notes:** Add rich comments to remind yourself why a video is important.
- ⏱️ **Timestamp Support:** Start watching exactly where you left off.
- 🏷️ **Tagging:** Organize content by topic, project, or priority.
- 🔎 **Search:** Instantly filter your library by tags or text.

## Getting Started

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd tubemark-pro
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Setup Environment**
   Copy `.env.example` to `.env` and configure your database URL.
   ```bash
   cp .env.example .env
   ```

4. **Initialize Database**
   Push the Drizzle schema to your database.
   ```bash
   npx drizzle-kit push
   ```

5. **Run Development Server**
   ```bash
   npm run dev
   ```

## Project Documentation

- [Task List](./TASKLIST.md) - Tracking project progress.
- [Learnings](./LEARNINGS.md) - Technical decisions and lessons learned.
- [Development Rules](./.dev0/RULES.md) - Coding standards and guidelines.