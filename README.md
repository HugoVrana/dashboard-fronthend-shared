# dashboard-frontend-shared

Shared React components and TypeScript utilities for dashboard apps.

## Installation

Add to your Next.js app's `package.json`:

```bash
npm install github:HugoVrana/dashboard-fronthend-shared
```

## Usage

```typescript
// Import from main entry
import { MyComponent, MyUtil } from 'dashboard-frontend-shared';

// Or import from specific paths
import { Button } from 'dashboard-frontend-shared/components';
import { ApiClient } from 'dashboard-frontend-shared/utils';
```

## Updating

After changes are pushed to this repo, update in your consuming apps:

```bash
npm update dashboard-frontend-shared
```

Or for a clean reinstall:

```bash
npm uninstall dashboard-frontend-shared && npm install github:HugoVrana/dashboard-fronthend-shared
```

## Development

### Adding components

1. Create your component in `src/components/`
2. Export it from `src/components/index.ts`

```typescript
// src/components/Button.tsx
export function Button({ children }: { children: React.ReactNode }) {
  return <button>{children}</button>;
}

// src/components/index.ts
export { Button } from './Button';
```

### Adding utilities

1. Create your class/function in `src/utils/`
2. Export it from `src/utils/index.ts`

```typescript
// src/utils/ApiClient.ts
export class ApiClient {
  // ...
}

// src/utils/index.ts
export { ApiClient } from './ApiClient';
```

### Building

```bash
npm run build      # Build once
npm run dev        # Watch mode
```

### After making changes

1. Run `npm run build`
2. Commit and push to GitHub
3. Run `npm update dashboard-frontend-shared` in consuming apps
