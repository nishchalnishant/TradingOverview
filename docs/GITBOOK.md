# GitBook setup

This repo is set up so that **all pages appear in the GitBook sidebar** when you sync with GitBook (GitBook.com or GitBook CLI).

## What’s in place

- **`SUMMARY.md`** (repo root) — Defines the table of contents. Every page that should appear in the GitBook sidebar is listed here with the correct path. GitBook uses this file to build the left-hand navigation.
- **`.gitbook.yaml`** (repo root) — Tells GitBook to use `README.md` as the intro and `SUMMARY.md` as the structure. Used by GitBook CLI and some integrations.

## Making sure pages are visible on GitBook.com

1. **Connect the repo** to your GitBook space (GitHub integration).
2. **Content source:** Set the content source to the **root** of the repository (e.g. `/` or `.`). Do not point it at a subfolder unless you intend only that folder as the book root.
3. **Use SUMMARY.md:** In the GitBook space settings (or Git sync settings), ensure the table of contents is driven by **SUMMARY.md**. On GitBook.com this is often automatic when `SUMMARY.md` exists in the root.
4. **Sync / rebuild:** After pushing changes to `SUMMARY.md`, trigger a sync or rebuild so the sidebar updates.

## What appears in the sidebar

The sidebar is built from `SUMMARY.md` and includes:

- **Stock market analysis** (root README)
- **Three pillars overview** — `stock-market-analysis/README.md`
- **Summary** — Overview of TA, FA, Options (Master + TA/FA/Options summaries)
- **Tips and Tricks** — All four tips files
- **Technical analysis** — Handbook, book summaries, Revision
- **Revision** — Cheat sheets and formula sheet
- **Fundamental analysis** — README and book notes
- **Options trading** — README and book notes

If a page is missing from the sidebar, add it to `SUMMARY.md` with the correct relative path (e.g. `Summary/Master_Summary.md`) and push. Then sync the book again.
