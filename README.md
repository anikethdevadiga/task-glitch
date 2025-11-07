**Live App:** [https://task-glitch-ivory.vercel.app/](https://task-glitch-ivory.vercel.app/)

# 🧠 TaskGlitch – SDE Bug Fix Challenge

This project is a **Task Management Web App** originally containing hidden bugs affecting UI, logic, and performance.  
I debugged and fixed all **five major issues** to make the app stable, efficient, and user-friendly.

---

## 🚀 Project Overview

The app helps sales teams track, manage, and prioritize tasks based on **ROI (Return on Investment)**.

Each task includes:
- Revenue  
- Time Taken  
- ROI  
- Notes  
- Priority  
- Status  

---

## 🧩 Tech Stack

- **React (TypeScript + Vite)**
- **Material UI (MUI)**
- **Context API + Custom Hooks**
- **CSV Import/Export**
- **Recharts (Charts Dashboard)**
- **Deployment:** Vercel

---

## 🐞 Fixed Bugs Summary

### 🧷 1. Double Fetch Issue
**Problem:** The app fetched tasks twice on load because of React.StrictMode and duplicated effects.  
**Fix:** Added a `useRef` guard to ensure the fetch runs only once.

✅ **Result:** Only one fetch occurs; no duplicate tasks or console logs.

---

### 🧷 2. Undo Snackbar Bug
**Problem:** Undo sometimes restored an old task because `lastDeleted` wasn’t reset.  
**Fix:** Reset `lastDeleted` and `isDeleted` when snackbar closes.

✅ **Result:** Undo restores only the most recent deletion.

---

### 🧷 3. Unstable Sorting (ROI ties)
**Problem:** Tasks with same ROI and priority flickered due to random tie-breaker.  
**Fix:** Added a stable tiebreaker using **alphabetical title**.

✅ **Result:** Consistent ordering across reloads.

---

### 🧷 4. Double Dialog Opening
**Problem:** Clicking Edit/Delete opened both Edit/View dialogs due to event bubbling and nested Tooltips.  
**Fix:** Used `e.stopPropagation()` and simplified Tooltip structure.

✅ **Result:** Each button now opens only its intended dialog.

---

### 🧷 5. ROI Calculation & Validation
**Problem:** ROI showed `NaN` or `Infinity` when timeTaken = 0 or invalid.  
**Fix:** Implemented validation — if timeTaken ≤ 0 → ROI = 0 (or “—”), and formatted to two decimals.

✅ **Result:** ROI values are always valid and neatly formatted.

---

## ⚙️ Local Setup

```bash
# 1. Clone the repository
git clone https://github.com/anikethdevadiga/task-glitch.git
cd task-glitch

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev

# 4. Build for production
npm run build

# 5. Preview production build
npm run preview
