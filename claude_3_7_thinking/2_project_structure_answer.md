# NextFaster Codebase Structure

This project uses a modern Next.js 15 application structure with the App Router pattern. Here's an overview of the project organization:

## Core Structure

- app - Next.js App Router routes and pages

  - Uses route groups like `(category-sidebar)`
  - Special files: layout.tsx, page.tsx
  - Server components with `.server.tsx` extensions
  - Dynamic routes with bracket notation (e.g., `[category]`)

- components - Reusable React components

  - UI components like `product-card`, `search-dropdown`, etc.

- db - Database related code

  - Schema definitions using Drizzle ORM
  - Database client setup

- lib - Utility functions and shared logic

  - Database queries in `queries.ts`

- scripts - Helper scripts
  - Data generation scripts (e.g., genProducts.ts, generate.ts)
  - Image handling utilities

## Key Technologies

Based on the file structure and code snippets:

- Next.js 15 with App Router
- TypeScript throughout
- Drizzle ORM with PostgreSQL (Neon)
- React Server Components
- Tailwind CSS for styling
- Vercel deployment infrastructure

The project follows modern Next.js conventions with server components, file-system based routing, and colocation of related functionality.
