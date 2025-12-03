# Repository Guidelines

## Project Structure & Module Organization

```
├── config.yaml          # Monitor configuration and settings
├── index.js             # Worker entry point
├── pages/               # Flareact pages (React components)
│   ├── index.js         # Main status page
│   └── api/             # API routes
├── src/
│   ├── components/      # React UI components (monitorCard, themeSwitcher, etc.)
│   ├── functions/       # Worker functions (cronTrigger, helpers)
│   └── cli/             # CLI utilities (gcMonitors.js)
├── public/              # Static assets (favicon, logo, CSS)
├── wrangler.toml        # Cloudflare Workers configuration
└── tailwind.config.js   # Tailwind CSS configuration
```

## Build, Test, and Development Commands

| Command           | Description                                |
| ----------------- | ------------------------------------------ |
| `yarn install`    | Install dependencies                       |
| `yarn run css`    | Compile Tailwind CSS to `public/style.css` |
| `yarn run build`  | Build CSS and Flareact project             |
| `yarn run dev`    | Start local development server             |
| `yarn run deploy` | Build and publish to Cloudflare Workers    |
| `yarn run format` | Format code with Prettier                  |
| `yarn run kv-gc`  | Run KV garbage collection utility          |

**Prerequisites:** Node 14+, Yarn, Wrangler CLI (`npm i -g wrangler`), and a Cloudflare account.

## Coding Style & Naming Conventions

- **Formatter:** Prettier (configured in `.prettierrc`)
- **Indentation:** 2 spaces
- **Quotes:** Single quotes
- **Semicolons:** None
- **Trailing commas:** All (ES5+)
- **Line width:** 80 characters

Run `yarn run format` before committing. Component files use camelCase (e.g., `monitorCard.js`).

## Testing Guidelines

This project does not include a formal test framework. Validate changes by:

1. Running `yarn run dev` and testing at `localhost:8787`
2. Checking browser console for JavaScript errors
3. Verifying monitor status updates correctly from KV storage
4. Testing dark/light theme switching
5. Validating `config.yaml` changes render properly

## Commit & Pull Request Guidelines

- Use concise, descriptive commit messages
- Reference issues when applicable
- Include screenshots for UI changes
- Ensure code is formatted with Prettier before submitting
