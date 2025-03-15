# Next.js Technologies Used in NextFaster

This codebase leverages several modern Next.js technologies and features:

## Core Next.js Features

- **App Router**: Uses the `/app` directory structure with nested routing
- **Server Components**: Default React Server Components throughout the application
- **Client Components**: Selective use of "use client" directive where needed
- **Server Actions**: Data mutations with "use server" directive for forms and state changes
- **Metadata API**: Both static and dynamic metadata for SEO optimization
- **Image Optimization**: Using the Next.js Image component with quality and loading optimizations
- **Dynamic Routes**: Route parameters with `[category]`, `[subcategory]`, `[product]` patterns
- **Route Groups**: With patterns like `(category-sidebar)` for shared layouts
- **API Routes**: Handler functions in the app directory
- **Edge Runtime**: For components like OpenGraph images

## Advanced Features

- **Partial Prerendering (PPR)**: Enabled in next.config.mjs with `experimental: { ppr: true }`
- **Static Generation**: Using `generateStaticParams` for prerendering static pages
- **OpenGraph Image Generation**: Dynamic OG images with `ImageResponse` from `next/og`
- **React Suspense**: For streaming UI components and handling loading states
- **Custom Link Component**: Enhanced Next.js Link with image prefetching
- **Caching Strategies**: Using `unstable_cache` and custom cache wrappers

## Experimental Features

- **React Compiler**: Using `reactCompiler: true` and `babel-plugin-react-compiler`
- **Inline CSS**: Enabled with `inlineCss: true`
- **React 19**: Using React 19 Release Candidate

## Integrations

- **Vercel Services**:
  - Vercel Postgres/Neon for database
  - Vercel Blob Storage for images
  - Vercel Analytics
- **TypeScript**: Full TypeScript support throughout the codebase
- **Drizzle ORM**: For database interactions

This codebase represents a cutting-edge implementation of Next.js, embracing the latest features and experimental capabilities to create a highly performant e-commerce platform.
