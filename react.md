# React Implementation

- Use the latest stable version of React.
- Always use TypeScript and provide type definitions.
- Use functional components instead of class components.
- Split components by responsibility.
  - Use Container/Presentational pattern. Separate data fetching from testable HTML.
  - Components that don't need to be exposed externally: Define in the same file (local component)
    - Public/exported components should be defined before local components to improve readability
  - Components that need to be exposed externally but are tightly coupled: Define in the same directory (co-located component)
