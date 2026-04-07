You are the world's best full-stack prompt engineer and vanilla web developer. Build a complete, beautiful, single-file Note-Taking Web Application called "MemoVault" using ONLY HTML, Tailwind CSS (via CDN), and vanilla JavaScript. The entire app must be in ONE self-contained .html file.

Follow every requirement STRICTLY. Pay special attention to correct data persistence and CRUD operations.

EXACT REQUIREMENTS:

1. Layout & UI
   - Fixed left sidebar (280px)
   - Main canvas area
   - Top header with logo, search bar (title & description only), language switcher, theme switcher, user info

2. Sidebar
   - Logo "MemoVault" with gradient
   - Mode Selector (visible only when logged in): "Normal Notes" and "Kanban Board"
   - "Create Note" button (only in Normal Notes mode)
   - "Manage Categories" button
   - Language Switcher: English | ខ្មែរ
   - Theme Switcher: Light / Dark mode
   - Login / Logout section

3. Full Language Support
   - Entire UI must be fully translated to Khmer when selected (all text, buttons, modals, column titles, alerts).
   - Use accurate Khmer Unicode.
   - Persist language in localStorage.

4. Theme
   - Full Light and Dark mode using Tailwind dark: prefix.
   - Persist choice in localStorage.

5. Login System
   - Modal with username and password.
   - New username = automatically create account.
   - Store users in localStorage as: { users: { "username": { password, notes: [], kanbanTasks: [], customCategories: [] } }, currentUser: "username" }

6. Data Structure (CRITICAL)
   - Each note and kanban task must have a unique `id` (use Date.now()).
   - When logged in, ALL notes and kanban tasks MUST be saved under the user's account (`user.notes[]` and `user.kanbanTasks[]`).
   - Guest mode (not logged in): Use separate in-memory arrays (`guestNotes[]` and `guestKanbanTasks[]`). These are lost on refresh.
   - When user logs in:
     - Load the user's own notes and kanban tasks from localStorage.
     - Do NOT automatically merge guest data unless explicitly designed (but make sure previously created guest items are not lost visually during session).

7. Normal Notes - Full CRUD
   - Create: Modal with Title, Category (pre-defined + custom), Description
   - Read: Click card → view modal
   - Update: Edit title, category, description in view modal + Save Changes
   - Delete: Delete button with confirmation
   - Notes are saved to user.notes[] when logged in.

8. Kanban Board - Full CRUD
   - 3 columns: Todo, Doing, Done (Khmer: ត្រូវធ្វើ, កំពុងធ្វើ, បានធ្វើ)
   - Create: "Add Task" button in each column → modal pre-filled with that status
   - Read: Click task card → view/edit modal
   - Update: Edit title, description, category, AND change status (dropdown)
   - Delete: Delete button with confirmation
   - Drag & drop between columns (updates status)
   - All tasks saved to user.kanbanTasks[] with `status` field ("todo", "doing", "done")

9. Categories
   - Pre-defined: Personal/ផ្ទាល់ខ្លួន, Work/ការងារ, Study/ការសិក្សា, Ideas/គំនិត, Health/សុខភាព, Finance/ហិរញ្ញវត្ថុ, Other/ផ្សេងៗ
   - "Manage Categories" in sidebar → modal to add custom categories (saved per user)

10. Search
    - Searches only by title and description (no category filter)

11. Important Fixes & Behavior
    - When user logs in, their own saved notes and kanban tasks must load and render correctly.
    - Guest-created notes/tasks should remain visible during the session until refresh (but not saved).
    - After login, the correct user data must be displayed immediately (no blank page).
    - All CRUD operations must work reliably for both logged-in users and guests.
    - Switching between Normal Notes and Kanban modes must show the correct data without blank screens.

12. Technical
    - Use Tailwind CSS via CDN
    - Vanilla JavaScript only (clean, commented)
    - Native HTML5 drag & drop for Kanban
    - Fully responsive, modern UI, smooth animations, good empty states

Output ONLY the complete ready-to-run HTML code from <!DOCTYPE html> to </html>. 
Do not add explanations or markdown outside the code.
