# Recipe Explorer (Astro)

A modern, responsive recipe browsing UI using the Ocean Professional theme.

## Features
- Home with Popular and New sections
- Search and filter (by category and ingredients)
- Recipe detail page with ingredients, steps, time, and servings
- Favorites management (persisted in localStorage)
- API fallback: Uses `PUBLIC_API_BASE` if available, else local mock data
- Responsive layout and accessible components
- Basic loading/error states

## Getting started
Install and run (from this container root):
- `npm install`
- `npm run dev` (dev server on port 3000 per astro.config.mjs)
- `npm run build` then `npm run preview` to preview a production build

## Data source behavior
- If `PUBLIC_API_BASE` is set (e.g. `https://your-api.example.com`), frontend fetches `GET {PUBLIC_API_BASE}/recipes` and `GET {PUBLIC_API_BASE}/recipes/:id`.
- If not set or fetch fails, it falls back to bundled mock data at `src/data/recipes.json`.

Note: Do not hardcode secrets; all config is read from `import.meta.env`. Other `PUBLIC_*` envs are available but not required.

## Project structure (highlights)
- `src/styles/theme.css` — Ocean Professional theme styles
- `src/lib/api.ts` — Data layer with API/mock fallback
- `src/lib/favorites.ts` — Favorites storage in localStorage
- `src/components/*` — UI components (SearchBar, FiltersSidebar, RecipeCard, etc.)
- `src/pages/index.astro` — Home page
- `src/pages/recipes/[id].astro` — Recipe detail
- `src/pages/favorites.astro` — Favorites list

## Accessibility
- Semantic roles and aria attributes for search, nav, regions
- Keyboard-friendly favorites toggle and links
- Reduced motion-friendly transitions

## Notes
- No changes to scripts were made; `dev/build/preview` remain standard.
- Styling is implemented with scoped CSS and a global theme without Tailwind.

