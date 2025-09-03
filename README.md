# @azodik/ui

A modern, accessible React UI component library built with Radix UI, Tailwind CSS, and TypeScript.

## Features

- 🎨 **Modern Design**: Clean, accessible components built with Radix UI
- 🎯 **TypeScript**: Full TypeScript support with proper type definitions
- 🎨 **Tailwind CSS**: Utility-first CSS framework integration
- ♿ **Accessible**: Built on Radix UI primitives for excellent accessibility
- 📱 **Responsive**: Mobile-first responsive design
- 🚀 **Tree-shakable**: Only import what you need
- 🎭 **Customizable**: Easy to customize with CSS variables

## Installation

```bash
npm install @azodik/ui
# or
yarn add @azodik/ui
# or
pnpm add @azodik/ui
```

### Adding New shadcn Components

To add new shadcn components to this package, use the following command:

```bash
pnpm dlx shadcn@latest add <component-name>
```

For example, to add the chart component:

```bash
pnpm dlx shadcn@latest add chart
```

**Note**: After adding new components, you'll need to:
1. Build the package: `pnpm build`
2. Export the component from `src/index.ts`
3. Update the component list below if applicable

## Peer Dependencies

This package requires React 18+ and React DOM 18+ as peer dependencies:

```bash
npm install react react-dom
```

## Usage

### Basic Component Usage

```tsx
import { Button } from '@azodik/ui/components/button';
import { Card, CardContent, CardHeader, CardTitle } from '@azodik/ui/components/card';

function App() {
  return (
    <Card>
      <CardHeader>
        <CardTitle>Hello World</CardTitle>
      </CardHeader>
      <CardContent>
        <Button>Click me</Button>
      </CardContent>
    </Card>
  );
}
```

### Importing Utilities

```tsx
import { cn } from '@azodik/ui/lib/utils';

// Use the cn utility for conditional classes
const className = cn(
  'base-class',
  isActive && 'active-class',
  variant === 'primary' && 'primary-class'
);
```

### Importing Hooks

```tsx
import { useIsMobile } from '@azodik/ui/hooks/use-mobile';

function Component() {
  const isMobile = useIsMobile();
  
  return (
    <div>
      {isMobile ? 'Mobile View' : 'Desktop View'}
    </div>
  );
}
```

### Importing Styles

```tsx
// Import the global CSS for Tailwind utilities
import '@azodik/ui/globals.css';
```

### Theme Provider

```tsx
import { NextThemeProvider } from '@azodik/ui/providers/NextThemeProvider';

function App() {
  return (
    <NextThemeProvider>
      {/* Your app content */}
    </NextThemeProvider>
  );
}
```

## Available Components

- **Layout**: Card, Separator, AspectRatio
- **Navigation**: NavigationMenu, Breadcrumb, Sidebar
- **Forms**: Input, Textarea, Select, Checkbox, RadioGroup, Switch, Form
- **Data Display**: Table, Badge, Skeleton, Progress
- **Feedback**: Alert, AlertDialog, Dialog, Popover, Tooltip, Toast
- **Overlay**: Sheet, Drawer, Modal
- **Interactive**: Button, Toggle, ToggleGroup, Command
- **Charts**: Chart (Recharts integration)
- **Date**: Calendar, DatePicker
- **Media**: Avatar, AspectRatio

## Tailwind CSS Setup

This package uses Tailwind CSS. Make sure you have Tailwind CSS configured in your project:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Update your `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,ts,jsx,tsx}",
    "./node_modules/@azodik/ui/dist/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## CSS Variables

The package uses CSS variables for theming. Import the globals.css to get the default theme:

```css
@import '@azodik/ui/globals.css';
```

## TypeScript

This package is built with TypeScript and includes proper type definitions. No additional `@types` package is needed.

## Contributing

Contributions are welcome! Please read our contributing guidelines.

## License

MIT License - see the [LICENSE](LICENSE) file for details.
