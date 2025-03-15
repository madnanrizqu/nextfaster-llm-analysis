# Rendering Strategy in NextFaster

This codebase is using **Partial Prerendering (PPR)** as its primary rendering strategy. This is evident from several key indicators:

## Implementation Details

1. **Next.js Configuration:**

   ```js
   // next.config.mjs
   const nextConfig = {
     experimental: {
       ppr: true,
       inlineCss: true,
       reactCompiler: true,
     },
     // ...
   };
   ```

2. **README Documentation:**
   The project explicitly states:

   > "Partial Prerendering is used to precompute the shells of pages. When deployed, these are served statically from the edge. Dynamic data (such as cart information) is then streamed in."

3. **Component Architecture:**

   - Static shells are pre-rendered
   - Dynamic content is wrapped in `<Suspense>` boundaries
   - Example from order page:
     ```tsx
     <Suspense>
       <CartItems />
     </Suspense>
     <Suspense>
       <TotalCost />
     </Suspense>
     ```

4. **Server Components and Actions:**

   - Uses Next.js server components for data fetching
   - Implements server actions for mutations with `"use server"` directives

5. **Caching Strategy:**
   - Uses `unstable_cache` with specific revalidation times
   - Example: `revalidate: 60 * 60 * 2, // two hours`

This hybrid approach gives the benefits of static generation (fast initial load, SEO) while still allowing dynamic content to be streamed in after the initial page shell is delivered.
