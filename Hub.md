# michaelrad.me

**Project:** [[Career/Career|Career]]
**Code & plans:** `~/Documents/claude/code/michaelrad.me/site/` — Astro codebase + planning docs in `docs/`
**Status:** ⏳ Paused 2026-05-03 mid-Phase-4. Next action: create Railway project.
**Pick up here:** [Session Log](file:///Users/michaelradparvar/Documents/claude/code/michaelrad.me/site/docs/session-log.md) (engineering-side, has the pickup prompt)

*Vault hub for content authored in Obsidian and pulled into the Astro build at deploy time. The site code and planning docs live in `code/`; this folder is for the markdown the site renders, and is now its own private git repo connected to GitHub at [michaelrad-me-content](https://github.com/michaelrad100/michaelrad-me-content).*

---

## Site sections authored here

- **`blog/`** — one .md per post.
- **`now.md`** — rolling "what I'm working on now" page.
- **`about.md`** — the About section that renders on the home page.

## How publishing works

1. Edit a post in `blog/` or update `now.md` here. Set `draft: false` in frontmatter when ready to publish (omit or `true` keeps it private).
2. From this folder: `git add . && git commit -m "..." && git push`
3. Done. A GitHub Action on this repo (`.github/workflows/trigger-rebuild.yml`) auto-pushes an empty commit to the site repo, which triggers Railway to rebuild and re-clone this content. Live in ~60s.

Drafts (`draft: true`) can be pushed freely — the build filters them out, so they never appear on the site.

---

## Recent notes

- 2026-05-26 — [[about|About]] — extracted from `index.astro` so the home page bio is now editable from Obsidian alongside `/now` and blog posts.
- 2026-05-18 — [[blog/2026-05-18-runway-week-2-underneath|Runway Week 2: Underneath]] — third check-out (draft, publishes Mon): KPI sheet automation, AI Overview absorption, the $11K Amazon decision, #notify attribution rebuilt. Categorized `holstee`, `automation`.
- 2026-05-15 — [[Career/Dave site feedback - michaelrad.me - 2026-05-15|Dave's site feedback]] — call reviewing the new site: homepage, About copy, blog, voice. Voice rewrite is the priority.
- 2026-05-11 — [[blog/2026-05-11-runway-week-1-calibrate|Runway Week 1: Calibrate]] — second check-out: Social Comparison refresh, April Health Report v0, Pinterest API decision, strategic check-in. Categorized `holstee`, `automation`.
- 2026-05-05 — [[blog/2026-05-05-runway-week-0-setting-up|Runway Week 0: Setting up]] — first check-out: Sprint Plan locked, 14 governing decisions, Neurons refresh shipped via API, the published_at incident. Categorized `holstee`, `automation`.
- 2026-05-04 — [[blog/2026-05-04-back-to-holstee|Back to Holstee, for a sprint]] — series intro announcing the 8-week Runway period. Categorized `holstee`, `automation`.
- 2026-05-03 — [Session Log](file:///Users/michaelradparvar/Documents/claude/code/michaelrad.me/site/docs/session-log.md) — paused mid-Phase-4 just before Railway project creation. Phases 0–3 done, both repos on GitHub.

---

## Tasks

- [x] **Next:** Create Railway project from `michaelrad-me` repo, grant access to both repos, verify build #site ⏫ ✅ 2026-05-14
- [x] Apply Railway one-year free coupon #site ✅ 2026-05-14
- [ ] Set custom domain (`michaelrad.me` + `www.michaelrad.me`) in Railway #site
- [ ] Update DNS at registrar to point at Railway's CNAME target #site
- [ ] Verify all 4 routes load on the live domain, cancel Gamma #site
- [ ] Write real "How I work / What I'm looking for" copy (currently italic placeholder) #site
- [ ] Replace `now.md` placeholder with a real first entry #site
- [ ] Delete legacy empty file at `Career/Homepage Refresh/` #site
