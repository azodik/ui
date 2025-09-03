# @azodik/ui

A modern, accessible React UI component library built with Radix UI, Tailwind CSS, and TypeScript. This package is inspired by [shadcn/ui](https://ui.shadcn.com/) and provides a curated collection of high-quality, accessible components for building beautiful user interfaces.

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

## Tailwind CSS 4 Setup

This package uses Tailwind CSS 4. Make sure you have Tailwind CSS configured in your project:

```bash
npm install -D tailwindcss@next @tailwindcss/postcss
```

### CSS Setup

Create or update your main CSS file (e.g., `app.css` or `globals.css`):

```css
@import "tailwindcss";

/* Import the UI package styles */
@import "@azodik/ui/globals.css";
```

**Important**: Make sure you have Tailwind CSS 4 installed and configured in your project for the CSS import to work properly.

### PostCSS Configuration

Update your `postcss.config.mjs`:

```js
export default {
  plugins: {
    '@tailwindcss/postcss': {},
  },
}
```

### Content Scanning

Tailwind CSS 4 automatically scans your files for classes. Make sure your build process includes the UI package files:

```js
// If you need to manually configure content scanning
export default {
  content: [
    "./src/**/*.{js,ts,jsx,tsx}",
    "./node_modules/@azodik/ui/dist/**/*.{js,ts,jsx,tsx}"
  ],
}
```

## CSS Variables & Theming

The package uses CSS variables for theming. Import the globals.css to get the default theme and component styles:

```css
@import "tailwindcss";
@import '@azodik/ui/globals.css';
```

### Available CSS Variables

The package provides the following CSS custom properties for theming:

```css
:root {
  /* Colors */
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
  --card: 0 0% 100%;
  --card-foreground: 222.2 84% 4.9%;
  --popover: 0 0% 100%;
  --popover-foreground: 222.2 84% 4.9%;
  --primary: 222.2 47.4% 11.2%;
  --primary-foreground: 210 40% 98%;
  --secondary: 210 40% 96%;
  --secondary-foreground: 222.2 84% 4.9%;
  --muted: 210 40% 96%;
  --muted-foreground: 215.4 16.3% 46.9%;
  --accent: 210 40% 96%;
  --accent-foreground: 222.2 84% 4.9%;
  --destructive: 0 84.2% 60.2%;
  --destructive-foreground: 210 40% 98%;
  --border: 214.3 31.8% 91.4%;
  --input: 214.3 31.8% 91.4%;
  --ring: 222.2 84% 4.9%;
  --radius: 0.5rem;
}

.dark {
  --background: 222.2 84% 4.9%;
  --foreground: 210 40% 98%;
  --card: 222.2 84% 4.9%;
  --card-foreground: 210 40% 98%;
  --popover: 222.2 84% 4.9%;
  --popover-foreground: 210 40% 98%;
  --primary: 210 40% 98%;
  --primary-foreground: 222.2 47.4% 11.2%;
  --secondary: 217.2 32.6% 17.5%;
  --secondary-foreground: 210 40% 98%;
  --muted: 217.2 32.6% 17.5%;
  --muted-foreground: 215 20.2% 65.1%;
  --accent: 217.2 32.6% 17.5%;
  --accent-foreground: 210 40% 98%;
  --destructive: 0 62.8% 30.6%;
  --destructive-foreground: 210 40% 98%;
  --border: 217.2 32.6% 17.5%;
  --input: 217.2 32.6% 17.5%;
  --ring: 212.7 26.8% 83.9%;
}
```

## TypeScript

This package is built with TypeScript and includes proper type definitions. No additional `@types` package is needed.

## Contributing

Contributions are welcome! Please read our contributing guidelines.

## Acknowledgments

This UI package is built on top of amazing open-source projects:

- **[shadcn/ui](https://ui.shadcn.com/)** - Beautiful, accessible, and customizable components that inspired this library
- **[Radix UI](https://www.radix-ui.com/)** - Unstyled, accessible components for building high‑quality design systems
- **[Tailwind CSS](https://tailwindcss.com/)** - Utility-first CSS framework for rapid UI development
- **[Lucide React](https://lucide.dev/)** - Beautiful & consistent icon toolkit
- **[Recharts](https://recharts.org/)** - Composable charting library for React
- **[React Hook Form](https://react-hook-form.com/)** - Performant, flexible and extensible forms with easy validation
- **[Zod](https://zod.dev/)** - TypeScript-first schema validation with static type inference
- **[Next Themes](https://github.com/pacocoursey/next-themes)** - Perfect next.js dark mode in 30 seconds
- **[Class Variance Authority](https://cva.style/docs)** - A class variance authority for building component variants
- **[Tailwind Merge](https://github.com/dcastil/tailwind-merge)** - Utility to efficiently merge Tailwind CSS classes without style conflicts

## License

MIT License - see the [LICENSE](LICENSE) file for details.
