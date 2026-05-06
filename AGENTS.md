# AGENTS.md

This document provides an overview of the project architecture for developers and AI agents working in future sessions.

## Project Overview

A professional cybersecurity portfolio and resume site for **Sagar Dhar**. Built with TanStack Start (React 19 + Vite 7) and deployed on Netlify. Features a dark neon-green cybersecurity aesthetic.

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | TanStack Start |
| Frontend | React 19, TanStack Router v1 |
| Build | Vite 7 |
| Styling | Tailwind CSS 4 + inline styles (see conventions) |
| Content | Content Collections (type-safe markdown) |
| AI | TanStack AI / Netlify Functions |
| Language | TypeScript 5.7 (strict mode) |
| Deployment | Netlify |

## Directory Structure

```
content/
  jobs/              # Work experience (cybersecurity-intern, software-engineer-intern, freelance-creator)
  education/         # Education (amity-university)
  projects/          # Projects (dabi-ai, portfolio-site)
  blog/              # Blog posts (dfir, kali-linux, owasp)
src/
  components/
    Header.tsx       # Fixed top nav — logo + desktop/mobile nav links
    ui/              # Radix UI primitives (badge, card, etc.)
  lib/
    resume-tools.ts  # AI tools for resume assistant
    resume-ai-hook.ts
    utils.ts
  routes/
    __root.tsx       # Root layout: Header + scan-line + footer
    index.tsx        # Hero landing page (home)
    resume.tsx       # Full resume with experience, education, certs
    projects.tsx     # Projects grid
    contact.tsx      # Contact form (Netlify Forms)
    blog/
      index.tsx      # Blog listing (/blog/)
      $slug.tsx      # Blog post detail (/blog/:slug)
    api.resume-chat.ts  # POST endpoint for AI resume assistant
  styles.css         # Tailwind + cybersecurity dark theme CSS variables
content-collections.ts  # Zod schemas for all content types
```

## Design System

The site uses a **cybersecurity dark theme** defined entirely in `src/styles.css`:

- `--neon: #00ffcc` — primary accent, used for headings, icons, borders
- `--bg-deep: #050a0f` — page background
- `--bg-card: rgba(0,20,30,0.8)` — card/panel background
- `--text-muted: rgba(0,255,204,0.55)` — secondary text

### CSS Utility Classes (defined in styles.css)

| Class | Purpose |
|-------|---------|
| `.cyber-card` | Dark glassmorphism card with neon border + hover lift |
| `.cyber-btn` | Outlined neon button |
| `.cyber-btn-solid` | Filled neon button variant |
| `.cyber-badge` | Small pill badge (for skill tags, etc.) |
| `.skill-bar` / `.skill-fill` | Animated skill progress bar |
| `.timeline-line` / `.timeline-dot` | Timeline styling for experience sections |
| `.prose` | Styled markdown content (neon headings, code blocks) |
| `.scan-line` | Animated vertical scan line (applied in root layout) |
| `.neon-text` | Glowing neon text effect |

### Styling Convention

**Important:** Most components use **inline styles + CSS classes** rather than Tailwind utility classes. This is because the dark cybersecurity theme requires precise CSS variable usage that mixes poorly with Tailwind's light defaults. When adding new UI:
- Use `style={{ ... }}` for colours, spacing, layout
- Use `className="cyber-card"` etc. for reusable component styles
- Avoid Tailwind colour/background utilities (`bg-gray-*`, `text-gray-*`) — they will conflict with the dark theme

## Content Collections Schema

- **jobs**: `jobTitle`, `company`, `location`, `startDate`, `endDate?`, `summary`, `tags`, `content`
- **education**: `school`, `summary`, `startDate`, `endDate?`, `tags`, `content`
- **projects**: `title`, `description`, `tags`, `github?`, `liveUrl?`, `image?`, `content`
- **blog**: `title`, `date`, `summary`, `tags`, `author`, `content`

## Key Conventions

- Components: PascalCase files in `src/components/`
- Routes: file-based routing in `src/routes/`
- API routes: `api.*.ts` naming → `/api/*` endpoints
- TypeScript strict mode; `@/` alias maps to `src/`
- Zod for runtime validation (in content-collections.ts)
- `marked` for rendering markdown content in JSX

## Environment Variables

- `ANTHROPIC_API_KEY` — For AI resume assistant (or OPENAI/GEMINI)

## Owner

**Sagar Dhar** — Cybersecurity Engineer, BCA student at Amity University (graduating 2027). Specialises in ethical hacking, DFIR, and penetration testing.
