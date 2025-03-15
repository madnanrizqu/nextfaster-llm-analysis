# Input Validation Strategy in NextFaster

This codebase uses a **schema-based validation strategy with Zod** combined with Next.js Server Actions. The approach provides type safety and consistent error handling across the application.

## Key Components of the Validation Strategy

1. **Zod Schema Validation**

   - Schemas define expected data shapes and constraints
   - Used for form inputs, API responses, and data processing

2. **Custom `validatedAction` Middleware**

   - Found in middleware.ts
   - Acts as a wrapper for Next.js Server Actions
   - Validates incoming FormData against Zod schemas
   - Returns standardized error responses

3. **Server-Side Validation**

   - All form validations happen on the server via Server Actions
   - Example from actions.ts:

   ```ts
   const authSchema = z.object({
     username: z.string().min(1),
     password: z.string().min(1),
   });

   export const signUp = validatedAction(authSchema, async (data) => {
     // Process validated data
   });
   ```

4. **Client-Side Error Handling**

   - Uses React's `useActionState` hook to manage validation states
   - Displays validation errors from server responses

5. **Rate Limiting**
   - Additional security layer implemented with Upstash Ratelimit
   - Prevents brute force attacks on authentication endpoints

This approach creates a consistent validation pattern throughout the application while keeping validation logic on the server for security.
