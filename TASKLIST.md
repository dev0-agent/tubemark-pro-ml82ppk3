# Task List

This file shows the current progress of all tasks in this project.
It is automatically updated by dev0 as tasks are completed.

---

## Phase 1

- [ ] ⏳ **Project Configuration & Environment Setup**
  Initialize the project configuration. Create a `src/utils/env.ts` file using `@t3-oss/env-core` or similar to validate environment variables (DATABASE_URL). Configure Drizzle ORM with a basic `drizzle.config.ts`. Ensure the database connection is established.

- [ ] ⏳ **Define Database Schema**
  Create the Drizzle schema in `src/db/schema.ts`. Define tables for `bookmarks` (id, videoId, url, title, thumbnail, startTime, notes, createdAt) and `tags` (id, name, color). Create a join table `bookmark_tags` for the many-to-many relationship. Run migration generation.

- [ ] ⏳ **YouTube URL Parser Utility**
  Create a utility function `src/utils/youtube.ts` that accepts a string input. It should validate if it is a YouTube URL, extract the Video ID, and extract the timestamp (t= parameter) if present. It should convert the timestamp to seconds (integer). Write unit tests if possible or manual verification steps.

## Phase 2

- [ ] ⏳ **Server Function: Fetch Video Metadata**
  Create a TanStack Start Server Function that takes a YouTube Video ID. It should fetch the video title and thumbnail URL (using the YouTube oEmbed endpoint or public metadata scraping). Return a typed object with title and thumbnail.

- [ ] ⏳ **Create Bookmark Form Component**
  Build a UI component `CreateBookmarkForm`. It should accept a URL. On blur/paste, it uses the server function (task-4) to preview the video details. Include fields for 'Notes' and 'Start Time' (pre-filled from URL if available). Use shadcn/ui Input, Button, and Textarea.

- [ ] ⏳ **Server Function: Create & List Bookmarks**
  Implement Server Functions for `createBookmark` (insert into DB) and `getBookmarks` (select from DB, ordered by createdAt desc). Ensure `createBookmark` validates input using Zod.

- [ ] ⏳ **Dashboard Grid View**
  Create the main dashboard page. Use the `getBookmarks` server function to load data. Render a grid of BookmarkCards. Each card should show the thumbnail, title, timestamp badge, and a snippet of the notes.

## Phase 3

- [ ] ⏳ **Video Player Modal**
  Create a modal/dialog that opens when a bookmark is clicked. It should embed the YouTube video using an iframe or `react-player`, appending the `?start=` parameter based on the saved timestamp. Display the full notes below the video.

- [ ] ⏳ **Tag Management System**
  Implement the UI and backend logic to add tags to a bookmark. Update the `CreateBookmarkForm` to allow creating/selecting tags. Update the `getBookmarks` query to include associated tags.

- [ ] ⏳ **Delete and Edit Actions**
  Add a dropdown menu to the BookmarkCard (using shadcn DropdownMenu) with 'Edit' and 'Delete' options. Implement the corresponding Server Functions to update or delete the record in Drizzle.

## Phase 4

- [ ] ⏳ **Search and Filter Logic**
  Add a search bar and tag filter to the Dashboard. Implement the filtering logic (can be client-side if dataset is small, or update Server Function to accept search params).

- [ ] ⏳ **UI Polish & Empty States**
  Add empty states (e.g., 'No bookmarks found, add your first one!'). Improve loading skeletons using `Suspense`. Ensure responsive design for mobile views.

---

_Last updated by dev0 automation_
