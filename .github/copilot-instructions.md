# Cautious Doodle - React Vite Application

A modern React 19 application built with Vite and Bun, featuring hot module replacement, dark/light mode support, and optimized production builds.

**ALWAYS reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.**

## Working Effectively

### Prerequisites and Setup
- **Bun 1.2.22+** is required and pre-installed in the environment
- No additional SDK downloads needed - Bun handles all JavaScript toolchain requirements
- Verify Bun installation: `bun --version`

### Essential Commands (Validated and Timed)
**Install dependencies:**
```bash
bun install
```
- **Time**: ~0.007s (when cached), up to 30s for fresh install
- **Timeout**: Set 60s timeout to be safe
- **Status**: Always works, dependencies are managed by Bun

**Start development server:**
```bash
bun run dev
```
- **Time**: ~193ms startup
- **Timeout**: Set 30s timeout
- **URL**: http://localhost:5173
- **Status**: Always works, includes HMR (Hot Module Replacement)
- **Note**: Server runs indefinitely until stopped with Ctrl+C

**Build for production:**
```bash
bun run build
```
- **Time**: ~1.68s 
- **Timeout**: Set 120s timeout (build time may vary with code size)
- **Output**: Creates optimized files in `dist/` directory
- **Status**: Always works, includes CSS/JS bundling and minification

**Preview production build:**
```bash
bun run preview
```
- **Time**: ~1s startup
- **Timeout**: Set 30s timeout  
- **URL**: http://localhost:4173
- **Requires**: Must run `bun run build` first
- **Status**: Always works for testing production builds locally

## Validation Requirements

### Manual Testing Scenarios
**CRITICAL**: Always run these validation steps after making code changes:

1. **Basic Functionality Test:**
   - Start dev server: `bun run dev`
   - Navigate to http://localhost:5173
   - Click the counter button multiple times
   - Verify count increments correctly
   - **Expected**: Button text changes from "count is 0" to "count is 1", "count is 2", etc.

2. **Hot Module Replacement Test:**
   - With dev server running, modify `src/App.jsx`
   - Change button text or add new elements
   - **Expected**: Changes appear immediately without page refresh

3. **Production Build Test:**
   - Run `bun run build`
   - Run `bun run preview`
   - Navigate to http://localhost:4173
   - Test same functionality as development mode
   - **Expected**: Application works identically to development mode

### Build Validation
- **Always run** `bun run build` before committing changes
- **Never skip** the production build test - builds may fail even when dev works
- **Check dist/ contents** after build to ensure proper asset generation

## Project Structure

```
cautious-doodle-2/
├── .github/
│   ├── workflows/copilot-setup-steps.yml  # CI setup for Copilot agent
│   └── copilot-instructions.md            # This file
├── src/
│   ├── App.jsx                            # Main React component with counter logic
│   ├── App.css                            # App-specific styles
│   ├── main.jsx                           # React application entry point
│   └── index.css                          # Global styles (dark/light mode)
├── public/                                # Static assets (favicon, etc.)
├── dist/                                  # Production build output (generated)
├── index.html                             # HTML template
├── vite.config.js                         # Vite bundler configuration
├── package.json                           # Dependencies and scripts
├── bun.lock                               # Bun lockfile
└── README.md                              # Project documentation
```

## Key Development Areas

### Primary Component (`src/App.jsx`)
- Contains main application logic
- Implements React state management with `useState` hook
- **Always test** counter functionality after modifications
- **File pattern**: Changes here require HMR validation

### Styling (`src/index.css`, `src/App.css`)
- `index.css`: Global styles with CSS custom properties for theming
- `App.css`: Component-specific styles
- **Supports**: Automatic dark/light mode via `prefers-color-scheme`
- **Validation**: Visual inspection in browser required after changes

### Configuration (`vite.config.js`)
- Minimal Vite configuration with React plugin
- **Rarely modified** - only change if adding new Vite plugins
- **Critical**: Always test both dev and build after config changes

## Common Tasks

### Adding New Components
1. Create new `.jsx` file in `src/`
2. Import and use in `App.jsx`
3. **Always validate** with development server
4. **Always test** production build works

### Modifying Styles
1. Edit `src/index.css` for global styles
2. Edit `src/App.css` for component styles  
3. **Test both** light and dark modes if possible
4. **Validate** in both development and production builds

### Debugging Issues
- **Development errors**: Check browser console and terminal output
- **Build errors**: Check terminal output from `bun run build`
- **Runtime errors**: Use browser developer tools
- **HMR issues**: Restart dev server with `bun run dev`

## Troubleshooting

### Common Issues and Solutions
- **Build fails**: Usually due to JavaScript/JSX syntax errors - check terminal output
- **Dev server won't start**: Port 5173 may be in use - kill existing processes
- **Changes not reflecting**: HMR may have failed - refresh browser or restart dev server
- **Production build different from dev**: Always test with `bun run preview`

### Environment Issues
- **Bun not found**: Should not occur in provided environment
- **Dependencies missing**: Run `bun install` 
- **Port conflicts**: Vite will automatically try alternative ports

## CI/CD Integration

### GitHub Actions
- **Setup workflow**: `.github/workflows/copilot-setup-steps.yml`
- **Installs**: Bun and project dependencies automatically
- **Validation**: Runs `bun install` during setup

### No Linting/Testing Scripts
- **Note**: This project does not include ESLint, Prettier, or test frameworks
- **Validation**: Relies on manual testing and build success
- **Future**: Linting tools can be added if needed

## Performance Notes

- **Development**: Vite provides instant hot reloading
- **Production**: Builds are optimized with tree-shaking and minification
- **Bundle size**: ~187KB JavaScript, ~1KB CSS (as of last build)
- **Build speed**: Very fast (~1.68s) due to Vite's efficient bundling

## Additional Context

### Technology Stack
- **React 19**: Latest React version with modern features
- **Vite 7.1.7**: Fast build tool and dev server
- **Bun 1.2.22**: JavaScript runtime and package manager
- **CSS**: Modern CSS with custom properties for theming

### Development Workflow
1. Make changes to source files
2. Verify in development server (auto-reloads)
3. Test production build before committing
4. Use browser dev tools for debugging
5. Always validate core functionality (counter button)

### File Patterns to Watch
- **Any changes to `src/App.jsx`**: Always test counter functionality
- **Any changes to CSS files**: Test visual appearance in browser
- **Any changes to `vite.config.js`**: Test both dev and build processes
- **Any changes to `package.json`**: Run `bun install` and test all commands