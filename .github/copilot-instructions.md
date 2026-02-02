# AI Coding Instructions for Project ""

## Architecture Overview

This project is a simple web application built with Node.js and Express, serving static files and handling basic API routes. Key components include:

- `server.js`: Main entry point, sets up Express server, middleware, and routes.
- `public/`: Static assets (HTML, CSS, JS) served directly.
- Data flows from client-side JS (e.g., `public/app.js`) to server routes (e.g., `/api/data`), with no database—data is stored in-memory or via external APIs.

Structural decisions prioritize simplicity: single-threaded server for lightweight use, no frameworks beyond Express to avoid overhead.

## Developer Workflows

- **Build & Run**: Use `npm start` to launch the server on port 3000. No build step; code is interpreted directly.
- **Testing**: Run `npm test` for Jest unit tests in `tests/`. Debug with `node --inspect server.js` and attach VS Code debugger.
- **Deployment**: Push to Heroku; environment variables handled via `.env` (ignore in commits).

## Conventions and Patterns

- **Error Handling**: Use try-catch in async routes, log to console with `console.error()`. Example: In `server.js`, route `/api/fetch` wraps external API calls.
- **Code Style**: 2-space indentation, camelCase variables. Import modules at top of files, e.g., `const express = require('express');`.
- **File Naming**: Routes in `routes/` directory, e.g., `routes/api.js` for API endpoints. Static files in `public/` with flat structure.
- **Dependencies**: Core: Express, Jest. External: Axios for HTTP requests (e.g., in `utils/fetcher.js`).

## Integration Points

- External API integration via Axios in `utils/fetcher.js`, e.g., fetching data from a public API endpoint.
- No cross-component communication beyond direct function calls; keep modules small and focused.

Reference: `server.js` for server setup, `public/index.html` for client entry, `tests/server.test.js` for test patterns.
