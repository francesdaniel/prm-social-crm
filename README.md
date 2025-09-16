# Social PRM — Local-first Social Contact Manager

This repository contains a **single-file, local-first Social PRM web app** designed as a starting point for managing contacts from social platforms (LinkedIn, Instagram, WhatsApp). It's intentionally minimal, runs in the browser without a backend, and stores data in **IndexedDB**. It's suitable for local use and for importing into Obsidian.

## What this delivers
- `index.html` — A single-file web app that:
- Stores contacts locally in the browser (IndexedDB).
- Has built-in fields: `name`, `headline`, `url`, `handle`, `email`, `phone`, `website`, `platform`, `tags`, and `country`.
- Supports custom/malleable fields (add/remove schema fields via the UI). Custom fields are saved per-contact under `extra`.
- Search, tag-based filtering, and basic deduplication guidance.
- Export contacts as an Obsidian-compatible markdown bundle (`prm_contacts_bundle.txt`) — split and paste into your vault or process with a script.
- `README.md` — this file.
- `LICENSE` — MIT.

## Why IndexedDB?
IndexedDB is built into the browser and lets the app be fully local-first (no hosting costs). The schema design uses flexible `extra` fields so you can add or abate delineations (custom fields) without a rigid database migration.

## How to use
1. Download `index.html` and open it in a modern Chromium-based browser (Chrome, Edge, Brave).
2. Use **New Contact** to create or **Import** CSV/JSON/vCard to batch import.
3. Add custom fields via **Add field** or the Custom fields UI — these are persisted as part of the schema and rendered into the contact form.
4. Use **Export Markdown Bundle** to produce a text file with contact markdowns (one chunk per file) that you can split into individual `.md` files and drop into your Obsidian vault (or use shell scripts to split automatically).

## Next steps (suggested)
- Add a small backend for OAuth and server-side sync (required for production LinkedIn/WhatsApp/Instagram connectors).
- Implement a real ZIP exporter (JSZip) or provide a small CLI to split the bundle into proper `.md` files.
- Add optional GitHub Actions to automatically publish to Pages on commit.
- Add worker/agent scaffolding (if you plan to add autonomous outreach — be sure to follow platform policies and include opt-ins).

## Compliance note
Do not use automation for unsolicited bulk messages. WhatsApp and LinkedIn have strict policies about outreach. Respect opt-in and privacy laws.

## License
MIT — see `LICENSE` file.
