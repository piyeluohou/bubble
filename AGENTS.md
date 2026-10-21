# Repository Guidelines

## Project Structure & Module Organization
This is a React Router Framework application with React, TypeScript, Vite, Tailwind CSS, and server-side rendering.
- `app/root.tsx`: document layout and root error boundary.
- `app/routes.ts`: route registration; route modules live in `app/routes/`.
- `app/welcome/`: starter UI and colocated SVG assets.
- `app/app.css`: Tailwind imports, theme settings, and global styles.
- `public/`: static files served directly, including the favicon.
- `.react-router/` and `build/`: generated types and build output; do not edit or commit them.

## Build, Test, and Development Commands
Use npm and update `package-lock.json` alongside dependency changes.
- `npm ci`: install dependencies from the lockfile.
- `npm run dev`: start development with hot reload, normally on port 5173.
- `npm run typecheck`: generate route types and run TypeScript checks.
- `npm run build`: create production client and server bundles.
- `npm start`: serve the production build; build first.
- `docker build -t bubble .` and `docker run -p 3000:3000 bubble`: build and run the container. The Dockerfile uses Node 24 Alpine.

## Coding Style & Naming Conventions
Follow existing files: two-space indentation, double quotes, semicolons, and ES module imports. Use TypeScript and functional React components. Name components in PascalCase and follow lowercase file names such as `home.tsx` and `welcome.tsx`. Use `import type` for type-only imports and generated `./+types/` definitions for route contracts. The `~/` alias resolves to `app/`. Prefer Tailwind utilities for component styling. No formatter or linter is configured; avoid unrelated formatting changes.

## Testing Guidelines
No test runner, test suite, or coverage threshold is configured. Before submitting changes, run `npm run typecheck` and `npm run build`, then manually check affected routes, responsive layouts, and light/dark styling. If introducing automated tests, document the runner, test naming convention, and execution command.

## Commit & Pull Request Guidelines
The repository has no commits yet, so no established commit convention exists. Use short, imperative subjects, such as `Add account route`, and keep commits focused. Pull requests should explain the change, link relevant issues, list validation performed, and include screenshots for UI changes. Keep secrets out of source control; `.env` is ignored.
