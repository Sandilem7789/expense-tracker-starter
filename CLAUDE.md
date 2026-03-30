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

Single-page React app (no backend). All application logic lives in `src/App.jsx` — one component managing all state via `useState`. There is no routing, no context, no external state library.

The app tracks financial transactions with these features:
- Add income/expense transactions with category and amount
- Filter transactions by type and category
- Calculate totals (income, expenses, balance)

**This is a course starter project** (codewithmosh.com) intentionally containing bugs and messy code for students to fix:
- Amounts are stored as strings, causing arithmetic bugs in total calculations
- Sample data has an incorrect transaction type on one entry
- A delete button is styled in CSS but never rendered
- All logic is in a single component with no separation of concerns
- No data persistence (state resets on refresh)

## Constraints

The `.claude/settings.local.json` restricts bash tool usage to only `npm install` and `npm run` commands.
