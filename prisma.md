## Prisma Type Definitions

When defining Prisma types in advance, use the `satisfies` operator instead of `Prisma.validator` for cleaner and more concise code.

```typescript
// Good
const userSelect = {
 select: {
   id: true,
   email: true,
   posts: true,
 }
} satisfies Prisma.UserDefaultArgs

type User = Prisma.UserGetPayload<typeof userSelect>

// Avoid
const userSelect = Prisma.validator<Prisma.UserDefaultArgs>()({
 select: { id: true, email: true, posts: true }
})
```
