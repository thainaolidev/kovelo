# KOVELO STUDIO

Kovelo Studio is a custom digital studio website focused on web development, UI/UX, performance and digital experiences.

## Features

- Portuguese and English localisation with route-aware language switching
- Responsive, mobile-first layout with a lightweight aurora visual system
- Portfolio linking only to the selected public Kovelo projects
- Accessible multi-step project enquiry form
- SEO-ready metadata, favicon and production SPA routing
- Vercel-ready deployment configuration

## Tech stack

- React
- TypeScript
- Vite
- CSS

## Project structure

- `src/main.tsx` — application, routes and UI components
- `src/locales.ts` — centralised Portuguese and English content
- `src/styles.css` — design system and responsive presentation
- `public/` — static assets, robots and sitemap

## Development

```bash
npm install
npm run dev
```

## Production build

```bash
npm run build
npm run preview
```

## Environment variables

Copy `.env.example` to `.env.local` for local values. All `VITE_` variables are public client-side configuration and must never contain secrets.

| Variable | Purpose |
| --- | --- |
| `VITE_CONTACT_FORM_ENDPOINT` | Optional public endpoint for processing the project form. |
| `VITE_CALENDLY_URL` | Optional public Calendly booking URL. |
| `VITE_SITE_URL` | Public production site URL, used for canonical and share metadata. |
| `VITE_INSTAGRAM_URL` | Optional public Instagram profile URL. |
| `VITE_LINKEDIN_URL` | Optional public LinkedIn profile URL. |

Set the same public variables in Vercel for Preview and Production as needed. A private email provider key must stay server-side and must not use the `VITE_` prefix.

## Deployment

The project is configured for Vercel. Connect the repository, use `npm run build` as the build command, and `dist` as the output directory. `vercel.json` rewrites requests to the SPA entry point so direct visits to localised routes work.

For a public GitHub repository, publish only the tracked source files. `.gitignore` intentionally excludes `node_modules`, `dist`, local environment files, Vercel project state and generated output archives. Dependabot configuration is included in `.github/dependabot.yml`.

Before connecting a custom domain, set `VITE_SITE_URL` and update the sitemap URLs in `public/sitemap.xml` to that final domain.

## License

No license is currently specified. This repository is publicly visible for portfolio and transparency purposes; unless otherwise stated, the source code, visual identity, original assets and content remain the property of KOVELO STUDIO and are not licensed for reuse.

## Security

Never commit credentials, tokens, private client data, or local environment files. `VITE_` variables are public browser configuration, not secrets. Any future form endpoint must validate input server-side, apply request rate limiting and abuse protection, and keep service credentials server-side. Please report vulnerabilities privately as described in [SECURITY.md](SECURITY.md).
