# Copilot Instructions for Cautious Doodle

## Project Overview
This is a modern React application built with Vite and managed with Bun. It's a basic React project demonstrating modern web development practices with fast build tools and runtime.

## Technology Stack
- **Frontend Framework**: React 19
- **Build Tool**: Vite 7.x
- **Package Manager**: Bun 1.2+
- **Language**: JavaScript (ES modules)
- **Styling**: CSS with dark/light mode support

## Project Structure
```
cautious-doodle/
├── .github/
│   ├── workflows/
│   │   └── copilot-setup-steps.yml    # GitHub Actions workflow
│   └── copilot-instructions.md        # This file
├── public/                            # Static assets
├── src/
│   ├── App.jsx                        # Main App component
│   ├── App.css                        # App-specific styles
│   ├── main.jsx                       # Entry point
│   └── index.css                      # Global styles with theme support
├── index.html                         # HTML template
├── vite.config.js                     # Vite configuration
├── package.json                       # Project dependencies and scripts
└── bun.lock                          # Bun lockfile
```

## Development Workflow

### Setup Requirements
- Bun 1.0+ (project tested with Bun 1.2.22)

### Common Commands
```bash
# Install dependencies
bun install

# Start development server (runs on http://localhost:5173)
bun run dev

# Build for production
bun run build

# Preview production build
bun run preview
```

## Coding Standards and Guidelines

### React Development
- Use functional components with hooks
- Follow React 19 patterns and best practices
- Use JSX for component templates
- Implement proper state management with useState
- Maintain component modularity and reusability

### File Organization
- Place React components in `/src` directory
- Use `.jsx` extension for React components
- Use `.css` files for styling (component-specific and global)
- Keep static assets in `/public` directory

### Styling Guidelines
- The project supports both dark and light mode themes
- Global styles are defined in `src/index.css`
- Component-specific styles go in corresponding `.css` files
- Use CSS custom properties (variables) for theming
- Follow mobile-first responsive design principles

### JavaScript/React Patterns
- Use ES modules (import/export)
- Prefer const/let over var
- Use arrow functions for concise syntax
- Implement proper error boundaries where needed
- Follow React hooks rules and best practices

## Build and Deployment

### Build Process
- Uses Vite for fast builds and hot module replacement
- Development server includes HMR for instant updates
- Production builds are optimized and minified
- Assets are automatically hashed for cache-busting

### GitHub Actions
- Automated workflow in `.github/workflows/copilot-setup-steps.yml`
- Runs on push/PR changes to workflow file
- Uses official Bun setup action for consistent environment
- Includes dependency installation step

## Key Features to Maintain
- ⚡️ Fast development with Vite HMR
- ⚛️ React 19 with modern patterns
- 🎨 Dark/light mode CSS theme support
- 📦 Optimized production builds
- 🔄 Hot Module Replacement in development

## Common Tasks and Solutions

### Adding New Components
1. Create `.jsx` file in `/src` directory
2. Import necessary dependencies (React, styles)
3. Export component as default
4. Import and use in parent components

### Styling Changes
- Global theme changes: modify `src/index.css`
- Component styles: create/modify corresponding `.css` file
- Use CSS custom properties for consistent theming
- Test both light and dark mode appearances

### Dependencies Management
- Use `bun add <package>` to add new dependencies
- Use `bun add -d <package>` for development dependencies
- Keep `bun.lock` file committed for reproducible builds

### Performance Considerations
- Leverage Vite's tree-shaking and code splitting
- Use React.lazy() for dynamic imports when needed
- Optimize bundle size with proper import statements
- Monitor build output for size analysis

## Debugging and Development
- Use browser dev tools for React debugging
- Vite provides detailed error messages and stack traces
- HMR enables instant feedback during development
- Console warnings should be addressed promptly

## Best Practices for AI Assistance
- When modifying components, maintain existing patterns and structure
- Preserve the dark/light theme support in styling changes
- Keep build configuration minimal and focused
- Test changes in both development and production builds
- Maintain component reusability and modularity
- Follow React 19 best practices and patterns