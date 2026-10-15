# ORBIT | مساحة عمل للإنتاجية

ORBIT is a browser-based workspace for organizing projects and tasks. It runs as a static website; each visitor's workspace is stored in that visitor's browser.

## Run locally / التشغيل المحلي

```sh
npm install
npm run dev
```

Build for production with `npm run build`, then preview with `npm run preview`. The deployable site is generated in `dist/`.

## Deploy / النشر

- **Vercel:** import the project folder/repository, use `npm run build`, and set the output directory to `dist`. `vercel.json` adds browser security headers.
- **Netlify:** use `npm run build`, set the publish directory to `dist`. `public/_headers` is copied into `dist` and adds browser security headers.
- Use HTTPS on the production domain. Confirm the deployed response includes the configured headers. Do not expose a development server as a public production server.

## What ORBIT does / ماذا يقدم ORBIT

- Dashboard with tasks due today, active/completed/overdue counts, weekly completions, deadlines, project progress, and recent actions.
- Projects with descriptions, colors, target dates, and completion metrics.
- Tasks with descriptions, status, priority, due date, project, and tags. Search, filtering, and sorting are available.
- Project list and Kanban board with drag and drop. Use the drag handle; keyboard sensors are enabled.
- Profile display name, compact mode, accent color, JSON export, and sample data restore.
- Responsive mobile navigation, iPhone safe-area support, larger touch targets, Safari-friendly form sizing, and reduced-motion support.
- Keyboard shortcuts: `Ctrl+K` / `⌘K` for search; `Ctrl+N` / `⌘N` for a new task; `Esc` closes overlays.

## Privacy and security / الخصوصية والأمان

- This is a frontend-only static app. It has no accounts, backend, sync, or server-side firewall. It cannot share one person's tasks with other visitors.
- Workspace data is stored in the current browser's local storage. Anyone with access to that browser profile may be able to access that local workspace. Export a JSON backup before clearing browser data.
- The app does not ask for passwords or secrets. The Google Fonts network import was removed so the app has no required third-party runtime requests.
- Vercel and Netlify header configurations include a Content Security Policy, anti-framing, MIME sniffing protection, referrer policy, and restricted browser permissions. The policy allows inline style attributes used for dynamic charts and layout; it disallows inline scripts and third-party script origins.
- A static web app has no inbound service port to open on your computer. The hosting platform/CDN is responsible for edge firewall, TLS, DDoS controls, and any WAF. Keep the deployment on HTTPS and enable the host's built-in protections; do not open your computer's firewall for public access.

## Project structure

- `src/App.jsx`: workspace screens and interactions.
- `src/styles.css`: visual system and responsive layouts.
- `src/main.jsx`: React entry point.
- `public/_headers`, `vercel.json`: production response security headers for Netlify and Vercel.

## Known limits

Data is local to each browser and does not sync or collaborate. Browser storage can be cleared by the user or browser. This project does not include a backend, authentication, cloud backup, or a managed firewall. A production publish still needs a domain and a hosting account.
