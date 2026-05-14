# Asetio Landing and Documentation

Single Nuxt project for Asetio's public web experience.

## Structure

- `/` is the commercial landing page, implemented as a custom Nuxt page with Vue components and Tailwind/Preline-style UI.
- `/docs` is the product documentation, powered by Docus/Nuxt Content and Markdown.
- `/en/docs` contains the English documentation.

## Development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Nuxt Content uses `better-sqlite3` internally to index Markdown. If Node changes, rebuild that native dependency:

```bash
npm rebuild better-sqlite3
```
