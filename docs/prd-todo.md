# Product Requirements Document (PRD) - Todo App Upgrade (Due Dates, Priorities, Filters)

## 1. Overview

We are upgrading the basic Todo app (currently just title + completed) to better support time-based planning and simple prioritization without adding backend complexity. The upgrade focuses on adding optional due dates, simple priority levels, and quick filters so users can see what’s urgent and act on it.

---

## 2. MVP Scope

- Data model
  - Add `dueDate` (optional) stored as ISO `YYYY-MM-DD`
  - Add `priority` enum: `P1 | P2 | P3` (default `P3`)
  - `title` remains required
- Validation
  - If `dueDate` is invalid, ignore it (treat as “no due date”)
- UI / interaction
  - Users can set or clear a task’s `dueDate`
  - Users can set a task’s `priority` (defaults to `P3` if not specified)
  - Provide filter tabs: **All**, **Today**, **Overdue**
    - **All** shows completed and incomplete tasks
    - **Today** shows only incomplete tasks due today
    - **Overdue** shows only incomplete tasks with a due date before today
- Persistence
  - Store tasks locally only (no backend / external storage changes)

---

## 3. Post-MVP Scope

- Visual styling enhancements
  - Visually highlight overdue tasks (e.g., red emphasis) so they stand out in lists
  - Show priority with color-coded badges:
    - `P1`: red
    - `P2`: orange
    - `P3`: gray
- Sorting
  - Apply enhanced sort order:
    - Overdue tasks first
    - Then by priority (`P1` → `P3`)
    - Then by due date ascending
    - Tasks without a due date last

---

## 4. Out of Scope

- Backend changes, APIs, or external storage (must remain local only)
- Notifications
- Recurring tasks
- Multi-user or collaboration features
- Keyboard navigation and special accessibility enhancements beyond defaults
