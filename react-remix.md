## React/Remix Development Guidelines

### Routing Convention

### Folder-based Routes

Always use folder-based routing structure. Each route must be a folder containing:

- `route.tsx` - Main route module with loader/action/component
- Additional modules specific to that route

Example:

```
app/routes/
├── _index/
│   ├── route.tsx
│   └── hero-section.tsx
├── products/
│   ├── route.tsx
│   └── product-layout.tsx
├── products.$id/
│   ├── route.tsx
│   ├── product-details.tsx
│   └── add-to-cart-button.tsx
└── admin.products/
    ├── route.tsx
    ├── product-form.tsx
    └── delete-product-modal.tsx
```

#### Module Organization

Within each route folder:

- `route.tsx` - Route exports only (loader, action, meta, default component)
- Separate files for:
  - UI components
  - Server utilities (*.server.ts)
  - Client utilities (*.client.ts)
  - Types/interfaces
  - Hooks
  - Tests

Shared modules go outside `routes/` directory.
