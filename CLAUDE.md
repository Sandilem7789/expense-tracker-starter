 # CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server at http://localhost:5173
npm run build    # Build for production
npm run preview  # Preview production build
npm run lint     # Run ESLint
```

## Architecture

Single-page React app (no backend). State is managed via `useState` with no routing, context, or external state library.

The app tracks financial transactions with these features:
- Add income/expense transactions with category and amount
- Filter transactions by type and category
- Calculate totals (income, expenses, balance)

### Component structure

- `App.jsx` — holds the `transactions` array in state; passes it down and handles `onAdd`
- `Summary.jsx` — receives `transactions`, computes totalIncome, totalExpenses, and balance internally
- `TransactionForm.jsx` — owns its own form state; calls `onAdd` prop with the new transaction object
- `TransactionList.jsx` — receives `transactions`, owns filter state (filterType, filterCategory)

**This is a course starter project** (codewithmosh.com). Remaining known issues:
- A delete button is styled in CSS but never rendered
- No data persistence (state resets on refresh)

## Constraints

The `.claude/settings.local.json` restricts bash tool usage to only `npm install` and `npm run` commands.
