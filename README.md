# Toast

An animated, interactive toast notification component with a spring-physics pill UI — built with Next.js, React 19, Tailwind CSS, and Framer Motion. Originally generated with [v0.app](https://v0.app).

## What it does

A self-contained toast component that cycles through three states with smooth spring animations:

- **Unsaved changes** — dark pill with an info icon, plus `Reset` and `Save` buttons
- **Saving** — animated iOS-style spinner with a "Saving" label while the action simulates
- **Changes saved** — checkmark confirmation that auto-dismisses back to the initial state

The demo page (`app/page.tsx`) renders the component centered on screen and simulates a 1.5s save flow, showing each state transition.

## Features

- Spring-physics width animation (stiffness 500 / damping 30) via Framer Motion
- Morphing pill layout — the component widens/narrows as content changes
- Custom iOS spinner (`spinner.tsx`) built with pure CSS animations
- Dark, high-contrast design with subtle inset highlights and layered shadows
- Radix UI primitives included (`components/ui/`) — toast, dialog, tooltip, dropdown, accordion, and more — ready to compose further interfaces
- Geist Sans/Mono typography

## Tech stack

- **Next.js** 15.2.8 (App Router, static export)
- **React** 19 + TypeScript
- **Tailwind CSS** 3.4 + `tailwindcss-animate`
- **Framer Motion** — animations
- **Radix UI** primitives — accessible component primitives
- **lucide-react** — icons
- **next-themes** — theme support
- **Vercel Analytics**

## Quick start

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to see the toast demo.

## Project structure

```
app/
  page.tsx            # Demo page — state machine driving the toast
  layout.tsx          # Root layout (Geist fonts, analytics)
  globals.css         # Tailwind + global styles
components/
  ui/                 # Radix-based UI primitives (toast, dialog, button, card, ...)
  theme-provider.tsx  # next-themes provider
lib/
  utils.ts            # cn() class-name helper
toast.tsx             # Animated pill toast component (root)
spinner.tsx           # iOS spinner + CSS (spinner.css)
demo.tsx              # Standalone demo wrapper (dark background)
public/               # Placeholder images
```

## Env vars

None required.

## Deployment

The app is a pure client-side static app — no API routes, no server actions, no secrets.

- Static export is enabled (`output: 'export'` in `next.config.mjs`).
- `basePath: '/toast'` is set for GitHub Pages subpath hosting. **Remove `basePath`** when deploying to a root domain (e.g. Vercel).
- Deployed via GitHub Pages (`gh-pages` branch).

```bash
npm run build        # emits ./out
```

## Credits

Built by Girish Lade — [https://ladestack.in](https://ladestack.in)
