## Code Modification Workflow

When modifying code in this project:

### 1. Development Commands

```bash
# Build the project
{コマンドを書く}

# Run tests
{コマンドを書く}

# Type checking
{コマンドを書く}

# Linting
{コマンドを書く}
```

### 2. Testing Strategy

- Run specific tests: `npm test -- path/to/test.ts`
- Run tests matching pattern: `npm test -- -t "pattern"`

### 3. Code Quality Checks

Before committing, always run:

1. `npm typecheck` - Ensure no TypeScript errors
2. `npm lint` - Check for linting issues
3. `npm test` - Verify all tests pass

### 4. Refactoring Guidelines

- Follow existing patterns in the codebase
