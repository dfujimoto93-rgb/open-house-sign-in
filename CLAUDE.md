# Open House Sign-In Form

## What This Is

A self-contained HTML sign-in tool for capturing visitor leads at open houses. Used by Dylan Fujimoto on an iPad — he fills it in while talking to visitors (not a self-serve kiosk).

## Deployment

- **GitHub:** https://github.com/dfujimoto93-rgb/open-house-sign-in
- **Live URL:** https://open-house-sign-in-six.vercel.app
- **Hosting:** Vercel (auto-deploys from `main` branch)
- **Framework:** None — single static `index.html`, no build step

## Architecture

One file: `index.html`. No dependencies, no CDN, no build system. Works offline via localStorage.

### Three Screens
1. **Setup** — Property address, price, date, agents, admin PIN
2. **Lead Capture** — Main form loop. Submit → save → reset → next visitor
3. **Admin Panel** — PIN-protected. View entries, export CSV, delete, clear all

### Data Storage
- `oh_config` in localStorage — property setup + PIN
- `oh_entries` in localStorage — array of visitor objects with timestamps

### CSV Export
- UTF-8 BOM for Excel compatibility
- Filename: `Open-House-Leads_[Address]_[Date].csv`
- Columns match KW Command import format

## CRM Integration

**Current:** CSV export → manual import into KW Command via agent.kw.com Contacts applet.
**Future (Phase 2):** Zapier webhook for automatic lead import. Not built yet.

## Brand & Compliance

- **Colors:** Cream `#F5F0E8` background, white cards, gold `#C4A265` buttons, black `#1A1A1A` text
- **Fonts:** System fonts (`-apple-system, BlinkMacSystemFont`)
- **KW Compliance Footer:** MY Realty Group | KW Honolulu | 1347 Kapiolani Blvd #300 | RB-2303 | Each office independently owned

## iPad Optimization

- 56px touch targets, 16px+ font sizes (prevents iOS auto-zoom)
- `apple-mobile-web-app-capable` for home screen fullscreen mode
- Phone number auto-formatting
- Single-column layout, minimal scrolling

## How to Work on This

- Keep it as a single HTML file — no frameworks, no build tools
- Test in Safari (desktop then iPad)
- Push to `main` to auto-deploy via Vercel
- Brand colors and KW compliance footer are required on all screens
- Dylan is not a developer — keep the tool simple to use
