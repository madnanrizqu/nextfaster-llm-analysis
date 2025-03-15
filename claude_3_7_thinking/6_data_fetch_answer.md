# Data Fetching Approach in NextFaster

This codebase primarily uses **React Server Components with Next.js App Router** for data fetching, with several key patterns:

## Server-Side Fetching

The primary data fetching approach uses:

- **React Server Components** with `async` functions that directly fetch data
- **Centralized query functions** in queries.ts
- **DrizzleORM** for database access with Postgres

## Caching Strategy

The codebase implements sophisticated caching:

- **`unstable_cache`** wrapper around database queries with 2-hour revalidation periods
- **Cache-Control headers** on API responses
- **Partial Prerendering** to serve static shells from the edge while streaming dynamic data

## Server Actions for Mutations

Data mutations are handled through:

- **Server Actions** (`"use server"` directive) for cart operations
- Functions like `addToCart` and `removeFromCart` in actions.ts

## Additional Patterns

Other notable data patterns:

- **React Suspense** for loading states and component-level streaming
- **Strategic client-side fetching** for interactive elements like search
- **Image optimization** with various loading strategies
- **Cookie-based state** for cart management

The README confirms this design, noting that "All mutations are done via Server Actions" and the site uses "Partial Prerendering" to optimize delivery of static content while dynamically loading personalized data.
