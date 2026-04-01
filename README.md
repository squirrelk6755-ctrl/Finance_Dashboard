# FinFlow — Finance Dashboard

A clean, interactive finance dashboard built as part of the Zorvyn Frontend Developer Intern screening assignment.

---

## Live Preview

Open `finance-dashboard.html` directly in any modern browser — no server or build step required.

---
## Live Demo
https://squirrelk6755-ctrl.github.io/Finance_Dashboard/

---

## Features Implemented

### 1. Dashboard Overview
- **Summary Cards** — Total Balance, Monthly Income, Monthly Expenses, Savings Rate
- **Balance Trend Chart** — Line chart showing balance, income, and expenses across 6 months (Chart.js)
- **Spending Breakdown** — Doughnut chart visualising expense categories
- **Recent Transactions** — Quick-view of the latest 5 entries

### 2. Transactions Section
- Full transaction table with: Date, Description, Category, Type, Amount
- **Search** — Real-time text search across name and category
- **Filtering** — Filter by category and by type (income/expense)
- **Sorting** — Sort by date, amount, name, or category (ascending/descending)
- **Pagination** — 10 transactions per page
- **CSV Export** — Download filtered transactions as a `.csv` file

### 3. Role-Based UI (Simulated)
- **Admin** — Can add, edit, and delete transactions via the top-right role selector
- **Viewer** — Read-only; add/edit/delete controls are hidden
- Role switch persists throughout the session with a toast confirmation

### 4. Insights Section
- Highest spending category with amount and percentage
- Average daily spend
- Monthly savings amount
- Top income source
- Highest expense month
- Expense-to-income ratio
- **Monthly Comparison Chart** — Grouped bar chart (Income vs Expenses vs Savings)
- **Category Breakdown** — Progress bars for each spending category with percentages

### 5. State Management
- All state managed via plain JavaScript (no framework dependency needed)
- `transactions` array is the single source of truth
- Filters, sort order, pagination, and role are all reactive
- **Data persistence** via `localStorage` — transactions survive page refresh

### 6. UI/UX
- Fully responsive — sidebar collapses on mobile with a hamburger menu
- **Dark mode** toggle in the top bar
- Smooth animations on cards, modals, and toasts
- Empty state handling when no transactions match filters
- Toast notifications for all user actions

---

## Optional Enhancements Included

| Feature | Status |
|---|---|
| Dark mode | ✅ |
| Data persistence (localStorage) | ✅ |
| Export to CSV | ✅ |
| Animations & transitions | ✅ |
| Advanced filtering + sorting | ✅ |

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Plain HTML/CSS/JS | No build step, instant load |
| Chart.js 4.4 (CDN) | Balance trend + spending charts |
| Google Fonts (DM Sans, DM Mono) | Typography |
| CSS Custom Properties | Theming + dark mode |
| localStorage | Data persistence |

---

## Setup Instructions

```bash
# No installation required.
# Simply open the file in a browser:

open finance-dashboard.html        # macOS
start finance-dashboard.html       # Windows
xdg-open finance-dashboard.html    # Linux
```

Or drag `finance-dashboard.html` into any modern browser window.

---

## Approach & Design Decisions

### Why vanilla JS?
The assignment explicitly allows plain JavaScript, and keeping this dependency-free means zero setup, instant load, and no build tooling. State is managed through a simple reactive pattern: a central `transactions` array, with all views re-rendering on change.

### Role-Based UI
Roles are simulated client-side using a dropdown. Admin unlocks the "Add Transaction" button and edit/delete controls on each row. Viewer sees a clean, read-only dashboard. This approach is clearly labelled as a frontend simulation (no backend auth), which matches the assignment scope.

### Component Structure (within a single file)
Even within one HTML file, the code is logically modular:
- **Data layer** — `transactions` array + `getStats()` / `getFiltered()`
- **Render functions** — `renderTable()`, `renderRecentTx()`, `renderCategoryBreakdown()`
- **Event handlers** — `filterTx()`, `sortBy()`, `saveTransaction()`, `deleteTransaction()`
- **Chart initializers** — `initBalanceChart()`, `initSpendChart()`, `renderInsightChart()`

### Responsive Design
CSS Grid with `minmax(0, 1fr)` columns ensures cards reflow correctly at every breakpoint. The sidebar uses a fixed-position drawer on mobile, toggled by a hamburger button.

---

## Assumptions Made

- Mock data is seeded with 20 realistic transactions for April 2026
- "Total Balance" is a fixed starting value (as there is no backend) and is for display purposes
- Savings Rate is derived from: `(Income - Expenses) / Income * 100`
- The insights section uses the seeded data; adding new transactions via the Admin role updates the category breakdown dynamically

---

## Screenshots

| Section | Description |
|---|---|
| Dashboard | Summary cards + trend chart + spending donut |
| Transactions | Filterable table with admin actions |
| Insights | 6 insight cards + comparison chart + category bars |

---

*Built by Muskan*
