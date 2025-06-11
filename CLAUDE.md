# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

```bash
npm install           # Install dependencies
npm run dev          # Start development server 
npm run build        # Build for production
npm run preview      # Preview production build
npm run format       # Format code with Prettier
npm run check        # Run Astro checks
```

## Architecture Overview

This is a **DentCare landing page** built with Astro, using the Bigspring Light theme template. Key architectural points:

### Multi-language Support
- Configured for Thai (default) and English locales
- Default locale (th) doesn't use URL prefix
- English content uses `/en/` prefix
- Homepage content stored in `src/content/homepage/` with language-specific files

### Content Management
- **Astro Collections**: Defined in `src/content.config.ts` with Zod schemas
- **Homepage**: Dynamic sections (banner, features, services, FAQ, contact) via frontmatter
- **Blog**: Markdown/MDX files with metadata (authors, categories, tags, dates)
- **Pages**: Static pages (privacy, terms, 404, etc.)
- **Contact/FAQ**: Structured data collections

### Styling & Components
- **Tailwind CSS v4** with custom plugins (`src/tailwind-plugin/`)
- **React components** for interactive elements (shortcodes in `src/layouts/shortcodes/`)
- **Auto-imported shortcodes**: Button, Accordion, Notice, Video, Tabs via `astro-auto-import`

### File Structure Patterns
- `src/content/`: All markdown content organized by collection type
- `src/layouts/`: Base layouts, components, and partials
- `src/pages/`: Route definitions (Astro file-based routing)
- `src/config/`: Site configuration, menu, social links, theme settings

### Configuration
- **Site settings**: `src/config/config.json` (title, URLs, navigation)
- **Deployment**: Netlify-ready with security headers in `netlify.toml`
- **Content schemas**: Strict typing via Zod in `src/content.config.ts`