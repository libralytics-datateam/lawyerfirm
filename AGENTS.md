# AGENTS.md

## Test commands
npm test
npm run lint

There is no `package.json`. Those commands have nothing to run until a package is added. Do not add one only to satisfy this section.

## Cursor Cloud specific instructions
This repo is a static site: `index.html`, `styles.css`, `script.js`, and `liff/index.html`. No install step beyond confirming those files exist. Python 3 from `/usr/bin/python3` serves the site; Node is not required.

From the repo root:

```bash
python3 -m http.server 8080 --bind 0.0.0.0
```

- Marketing site: `http://127.0.0.1:8080/`
- LINE intake page: `http://127.0.0.1:8080/liff/`
- Language switch, the consultation form, and the LIFF intake form are client-side. Submitting the marketing form shows a toast and does not call a backend. Booking opens a Google Calendar URL. Outside the LINE app, LIFF intake shows a copyable summary.
- Tailwind, Google Fonts, and the LINE LIFF SDK load from public CDNs. No secrets are required for local development.

## Loop conventions
- Report-only week one (L1) before enabling auto-fix (L2)
- See LOOP.md for cadence and human gates
