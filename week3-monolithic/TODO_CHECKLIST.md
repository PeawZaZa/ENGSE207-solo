# ✅ Week 3 Lab - TODO Checklist

Print this checklist and check off each item as you complete it!

---

## 🎯 BEFORE LAB

- [x] Read Timeline document (ENGSE207_Task_Board_Timeline.md)
- [x] Read Quick Reference guide
- [x] Laptop charged and ready
- [x] Internet connection available
- [x] VS Code installed

---

## 📦 SETUP (30 min)

### Environment Setup:
- [x] WSL2/Ubuntu installed (Windows users)
- [x] Node.js 20+ installed
- [x] npm installed
- [x] SQLite3 installed
- [x] Git installed
- [x] VS Code extensions installed:
  - [x] Remote - WSL
  - [x] ESLint
  - [x] SQLite Viewer
  - [x] Thunder Client

### Project Setup:
- [x] Created project folder: `week3-monolithic`
- [x] Extracted starter code to folder
- [x] Ran `npm install` successfully
- [x] Created database: `sqlite3 tasks.db < schema.sql`
- [x] Verified database has 4 sample tasks
- [x] Opened project in VS Code

---

## 💻 BACKEND IMPLEMENTATION (60 min)

### File: `server.js`

#### Basic Setup:
- [x] **Part 1:** Uncommented imports (express, sqlite3, path)
- [x] **Part 2:** Created app instance and defined PORT
- [x] **Part 3:** Added JSON and static file middleware
- [x] **Part 4:** Connected to database
- [x] **Test:** Ran `npm run dev` - server starts without errors

#### GET Endpoints:
- [x] **Part 5:** Implemented GET `/api/tasks` (all tasks)
  - [x] **Test:** Thunder Client shows all tasks
- [x] **Part 6:** Implemented GET `/api/tasks/:id` (single task)
  - [x] **Test:** Can get task by ID
  - [x] **Test:** Returns 404 for invalid ID

#### POST Endpoint:
- [x] **Part 7:** Implemented POST `/api/tasks` (create)
  - [x] Added title validation
  - [x] Returns created task with ID
  - [x] **Test:** Can create task with Thunder Client
  - [x] **Test:** Returns 400 if title is empty

#### PUT/PATCH Endpoints:
- [x] **Part 8:** Implemented PUT `/api/tasks/:id` (update)
  - [x] Builds dynamic SQL
  - [x] Returns updated task
  - [x] **Test:** Can update task fields
- [x] **Part 10:** Implemented PATCH `/api/tasks/:id/status`
  - [x] Validates status values
  - [x] **Test:** Can change status
  - [x] **Test:** Returns 400 for invalid status

#### DELETE Endpoint:
- [x] **Part 9:** Implemented DELETE `/api/tasks/:id`
  - [x] Returns appropriate messages
  - [x] **Test:** Can delete task
  - [x] **Test:** Returns 404 if task not found

#### Final Backend Setup:
- [x] **Part 11:** Added route to serve index.html
- [x] **Part 12:** Started server with listen()
- [x] **Part 13:** Added graceful shutdown (bonus)
- [x] **Test:** All API endpoints working correctly

### Backend Checkpoint ✓
- [x] Server runs without errors
- [x] All 6 API endpoints work
- [x] Thunder Client tests pass
- [x] No console errors

---

## 🎨 FRONTEND IMPLEMENTATION (60 min)

### File: `public/app.js`

#### State & DOM:
- [x] **Part 1:** Declared state variables (allTasks, currentFilter)
- [x] **Part 2:** Got all DOM element references
  - [x] Form element
  - [x] Filter select
  - [x] Task containers (todo, progress, done)
  - [x] Counter spans

#### Utility Functions:
- [x] **Part 11:** Implemented utility functions
  - [x] `escapeHtml()` - prevents XSS
  - [x] `formatDate()` - formats dates nicely
  - [x] `showLoading()` - shows overlay
  - [x] `hideLoading()` - hides overlay
  - [x] **Test:** Call functions in console

#### API Functions:
- [x] **Part 3:** Implemented `fetchTasks()`
  - [x] Fetches from `/api/tasks`
  - [x] Updates allTasks array
  - [x] Calls renderTasks()
  - [x] **Test:** Call in console - tasks load

- [x] **Part 4:** Implemented `createTask()`
  - [x] POSTs to `/api/tasks`
  - [x] Updates allTasks
  - [x] Resets form
  - [x] Shows success message
  - [x] **Test:** Create task manually

- [x] **Part 5:** Implemented `updateTaskStatus()`
  - [x] PATCHes to `/api/tasks/:id/status`
  - [x] Updates local state
  - [x] Re-renders
  - [x] **Test:** Change status manually

- [x] **Part 6:** Implemented `deleteTask()`
  - [x] Shows confirmation
  - [x] DELETEs from API
  - [x] Removes from local state
  - [x] **Test:** Delete manually

#### Render Functions:
- [x] **Part 7:** Implemented `renderTasks()`
  - [x] Clears all lists
  - [x] Filters tasks
  - [x] Separates by status
  - [x] Updates counters
  - [x] Calls renderTaskList()

- [x] **Part 8:** Implemented `renderTaskList()`
  - [x] Shows empty state if no tasks
  - [x] Loops through tasks
  - [x] Creates cards

- [x] **Part 9:** Implemented `createTaskCard()`
  - [x] Creates card element
  - [x] Sets correct HTML structure
  - [x] Includes all task data
  - [x] Has proper classes

- [x] **Part 10:** Implemented `createStatusButtons()`
  - [x] Shows appropriate buttons for status
  - [x] Includes onclick handlers

#### Event Listeners:
- [x] **Part 12:** Added form submit listener
  - [x] Prevents default
  - [x] Gets form data
  - [x] Validates title
  - [x] Calls createTask()

- [x] **Part 12:** Added filter change listener
  - [x] Updates currentFilter
  - [x] Calls renderTasks()

#### Initialization:
- [x] **Part 13:** Added DOMContentLoaded listener
  - [x] Logs startup message
  - [x] Calls fetchTasks()

- [x] **Part 14:** Exposed global functions
  - [x] window.updateTaskStatus
  - [x] window.deleteTask

### Frontend Checkpoint ✓
- [x] Page loads without errors
- [x] Tasks display correctly
- [x] Can create new task via form
- [x] Can move tasks between columns
- [x] Can delete tasks
- [x] Filter works
- [x] Counters update
- [x] No console errors

---

## 🧪 FULL APPLICATION TESTING (15 min)

### Functionality Tests:
- [x] Can view all tasks on page load
- [x] Tasks appear in correct columns
- [x] Can create task with only title
- [x] Can create task with description
- [x] Can create task with priority
- [x] Can move task: TODO → IN_PROGRESS
- [x] Can move task: IN_PROGRESS → DONE
- [x] Can move task backwards
- [x] Can delete task with confirmation
- [x] Filter "All Tasks" shows everything
- [x] Filter "To Do" shows only TODO
- [x] Filter "In Progress" shows only IN_PROGRESS
- [x] Filter "Done" shows only DONE
- [x] Counters update correctly
- [x] Priority badges show correct colors

### Error Handling:
- [x] Empty title shows error
- [x] Deleted task disappears immediately
- [x] Network errors show alert
- [x] Loading overlay appears/disappears

### UI/UX:
- [x] Buttons look good and work
- [x] Cards have hover effects
- [x] Page is responsive (try resizing)
- [x] Forms clear after submit
- [x] Confirmations show for delete

---

## 📝 DOCUMENTATION (15 min)

- [x] Wrote README.md with:
  - [x] Project overview
  - [x] Installation steps
  - [x] How to run
  - [x] Architecture description
  - [x] API endpoints list
  - [x] Screenshots (optional)

- [x] Answered REFLECTION.md questions:
  - [x] What did you learn?
  - [x] Main advantages of monolithic?
  - [x] Challenges encountered?
  - [x] Solutions found?
  - [x] When to use monolithic?
  - [x] What would you do differently?

- [x] Updated time tracking in reflection

---

## 🔄 GIT VERSION CONTROL (15 min)

- [x] Initialized git: `git init`
- [x] Created/verified .gitignore:
  - [x] node_modules/ excluded
  - [x] *.db excluded
  - [x] .env excluded

- [x] Added files: `git add .`
- [x] First commit with message:
  ```
  git commit -m "Week 3: Complete monolithic Task Board

  - Implement all CRUD operations
  - Create REST API with 6 endpoints
  - Build responsive frontend UI
  - Use SQLite for data persistence
  - All features working in single codebase"
  ```

- [ ] Additional commits for improvements (if any)
- [ ] Pushed to GitHub (optional):
  ```bash
  git remote add origin <your-repo-url>
  git branch -M main
  git push -u origin main
  ```

---

## 📤 SUBMISSION PREPARATION (10 min)

### Pre-submission Checklist:
- [ ] All features work correctly
- [ ] No console errors in DevTools
- [ ] No errors when starting server
- [ ] README.md is complete
- [ ] REFLECTION.md is complete
- [ ] Git commits are meaningful
- [ ] Code has comments where needed
- [ ] No node_modules in submission
- [ ] No database files in submission (.db)

### Create Submission:

**Option A: GitHub**
- [ ] Repository is public (or shared with instructor)
- [ ] README visible on GitHub
- [ ] Copy GitHub URL
- [ ] Submit URL in LMS

**Option B: ZIP File**
- [ ] Created ZIP excluding:
  - [ ] node_modules/
  - [ ] *.db files
  - [ ] .git/ (optional)
- [ ] Tested extraction and running
- [ ] Upload to LMS

---

## 🎓 SELF-ASSESSMENT

Rate yourself (1-5):

| Criteria | Rating | Notes |
|----------|--------|-------|
| Understanding of Monolithic | __/5 | |
| Backend API implementation | __/5 | |
| Frontend implementation | __/5 | |
| Git usage | __/5 | |
| Documentation quality | __/5 | |
| Code cleanliness | __/5 | |
| Problem-solving | __/5 | |
| **Total** | __/35 | |

**Strengths:**
- What did you do well?

**Areas for Improvement:**
- What could be better?

**Questions for Instructor:**
- What are you still confused about?

---

## 🎯 GRADING EXPECTATIONS

| Criteria | Points | Your Notes |
|----------|--------|------------|
| **Functionality** (4 pts) | | |
| - All CRUD operations work | | |
| - API endpoints correct | | |
| - Frontend interactive | | |
| **Code Quality** (2 pts) | | |
| - Clean, readable code | | |
| - Good practices used | | |
| - Comments where needed | | |
| **Documentation** (2 pts) | | |
| - Complete README | | |
| - Reflection answers | | |
| **Git Usage** (1 pt) | | |
| - Meaningful commits | | |
| **Creativity** (1 pt) | | |
| - Extra features | | |
| - Improved UI | | |
| **TOTAL** | __/10 | |

---

## 🚀 BONUS CHALLENGES (Optional)

Completed any of these?

- [ ] Added search functionality
- [ ] Added due dates for tasks
- [ ] Added task categories/tags
- [ ] Implemented dark mode
- [ ] Added drag-and-drop
- [ ] Added export/import JSON
- [ ] Added pagination
- [ ] Improved UI design significantly
- [ ] Added unit tests
- [ ] Added API documentation (Swagger)

---

## 📅 TIME MANAGEMENT

Actual time spent:

| Activity | Planned | Actual | Notes |
|----------|---------|--------|-------|
| Setup | 30 min | ____ min | |
| Backend | 60 min | ____ min | |
| Frontend | 60 min | ____ min | |
| Testing | 15 min | ____ min | |
| Documentation | 15 min | ____ min | |
| Git & Submission | 10 min | ____ min | |
| **Total** | 180 min | ____ min | |

---

## ✅ FINAL CHECKLIST

Before submitting, confirm:

- [ ] ✅ I can run the application without errors
- [ ] ✅ I tested all features thoroughly
- [ ] ✅ I understand what monolithic architecture is
- [ ] ✅ I can explain my code to someone else
- [ ] ✅ My README helps someone else run my code
- [ ] ✅ My reflection answers are thoughtful
- [ ] ✅ My Git history shows my progress
- [ ] ✅ I'm proud of what I built! 🎉

---

## 🎉 CONGRATULATIONS!

You've completed Week 3 Lab!

**Key Achievements:**
- ✅ Built a full-stack application
- ✅ Implemented REST API
- ✅ Used SQLite database
- ✅ Created interactive UI
- ✅ Practiced Git workflow
- ✅ Understood Monolithic Architecture

**Keep this code!** We'll refactor it to Layered Architecture in Week 4!

---

*TODO Checklist v1.0*  
*ENGSE207 Software Architecture - Week 3*  
*Print and check off as you go! ✓*
