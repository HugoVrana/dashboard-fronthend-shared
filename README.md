# dashboard-frontend-shared

Shared React components and TypeScript utilities for dashboard apps.

## Setup in consuming apps

Your Next.js apps need Tailwind CSS configured. Add this library to your `tailwind.config.ts` content array:

```typescript
// tailwind.config.ts
const config = {
  content: [
    // ... your other paths
    './node_modules/dashboard-frontend-shared/dist/**/*.js',
  ],
  // ...
};
```

## Installation

Add to your Next.js app's `package.json`:

```bash
npm install github:HugoVrana/dashboard-frontend-shared
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
npm uninstall dashboard-frontend-shared && npm install github:HugoVrana/dashboard-frontend-shared
```

## Development

### Adding shadcn components

1. Copy the component code from [ui.shadcn.com](https://ui.shadcn.com)
2. Create the file in `src/components/ui/`
3. Update the import path for `cn` to `@/lib/utils` → `../../lib/utils`
4. Export from `src/components/ui/index.ts`

```typescript
// src/components/ui/button.tsx
import { cn } from '../../lib/utils';
// ... rest of shadcn component code

// src/components/ui/index.ts
export { Button } from './button';
```

### Adding custom components

1. Create your component in `src/components/`
2. Export it from `src/components/index.ts`

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
