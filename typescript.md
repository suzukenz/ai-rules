## TypeScript Implementation Guidelines

### TypeScript Implementation

- Enable strict mode
- Follow verbatimModuleSyntax
- Use type guards to safely handle potential undefined or null values
- Use generics appropriately
- Use the unknown type appropriately
- Leverage TypeScript utility types (Partial, Pick, Omit) for cleaner and more reusable code
- Use mapped types to dynamically create variants of existing types
- Do not use TypeScript-specific syntaxes such as enum
- Never use enums; use types instead
- Prefer functions over classes

### ES Modules

- When importing Node.js APIs, use the node: prefix (e.g., "node:fs")
- Use named exports
