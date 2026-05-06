# Sagar Dhar — Cybersecurity Portfolio

A professional portfolio and resume site for **Sagar Dhar**, a BCA student at Amity University specialising in Cybersecurity & Digital Forensics. Built with TanStack Start and deployed on Netlify.

## Features

- **Hero landing page** with animated typing effect, skill bars, stats, and certifications
- **Resume page** with work experience timeline, education, certifications, and achievements
- **Projects showcase** powered by Content Collections (type-safe markdown)
- **Blog** with cybersecurity articles and tutorials
- **Contact form** with Netlify Forms integration
- **Cybersecurity dark theme** — neon cyan on deep black with animated scan line
- **AI-powered resume assistant** via `/api/resume-chat`

## Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | TanStack Start (React 19 + Vite 7) |
| Routing | TanStack Router v1 (file-based) |
| Styling | Tailwind CSS 4 + custom CSS variables |
| Content | Content Collections (type-safe markdown) |
| Forms | Netlify Forms |
| Deployment | Netlify |
| Language | TypeScript 5.7 (strict mode) |

## Getting Started

```bash
# Install dependencies
npm install

# Start development server (with Netlify features)
netlify dev

# Or start Vite directly
npm run dev

# Build for production
npm run build
```

The dev server runs at `http://localhost:8888`.

## Environment Variables

For the AI resume assistant, set one of:
- `ANTHROPIC_API_KEY`
- `OPENAI_API_KEY`
- `GEMINI_API_KEY`

## Content

All content lives in `content/` as markdown files with YAML frontmatter:

- `content/jobs/` — Work experience entries
- `content/education/` — Education entries
- `content/projects/` — Project showcases
- `content/blog/` — Blog articles

Edit the markdown files to update content without touching any code.
