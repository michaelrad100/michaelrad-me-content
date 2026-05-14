# michaelrad.me

**Project:** [[Career/Career|Career]]
**Code & plans:** `~/Documents/claude/code/michaelrad.me/site/` — Astro codebase + planning docs in `docs/`
**Status:** ⏳ Paused 2026-05-03 mid-Phase-4. Next action: create Railway project.
**Pick up here:** [Session Log](file:///Users/michaelradparvar/Documents/claude/code/michaelrad.me/site/docs/session-log.md) (engineering-side, has the pickup prompt)

*Vault hub for content authored in Obsidian and pulled into the Astro build at deploy time. The site code and planning docs live in `code/`; this folder is for the markdown the site renders, and is now its own private git repo connected to GitHub at [michaelrad-me-content](https://github.com/michaelrad100/michaelrad-me-content).*

---

## Site sections authored here

- **`blog/`** — one .md per post. Currently has the smoke-test post `2026-05-03-rebuilding-michaelrad-me.md`.
- **`now.md`** — rolling "what I'm working on now" page (placeholder content, replace pre-launch).

## How publishing works (post-launch)

1. Edit a post in `blog/` or update `now.md` here.
2. From this folder: `git add . && git commit -m "..." && git push`
3. From the site repo: `git submodule update --remote content-vault && git add content-vault && git commit -m "Update content" && git push`
4. Railway auto-rebuilds (~30–60s).

---

## Recent notes

- 2026-05-11 — [[blog/2026-05-11-runway-week-1-calibrate|Runway Week 1: Calibrate]] — first weekly recap of the Holstee Runway sprints. Tagged `holstee`, `automation`.
- 2026-05-04 — [[blog/2026-05-04-back-to-holstee|Back to Holstee, for a sprint]] — intro post announcing the 8-week Runway series. Tagged `holstee`, `automation`.
- 2026-05-03 — [Session Log](file:///Users/michaelradparvar/Documents/claude/code/michaelrad.me/site/docs/session-log.md) — paused mid-Phase-4 just before Railway project creation. Phases 0–3 done, both repos on GitHub.

---

## Tasks

- [ ] **Next:** Create Railway project from `michaelrad-me` repo, grant access to both repos, verify build #site ⏫
- [ ] Apply Railway one-year free coupon #site
- [ ] Set custom domain (`michaelrad.me` + `www.michaelrad.me`) in Railway #site
- [ ] Update DNS at registrar to point at Railway's CNAME target #site
- [ ] Verify all 4 routes load on the live domain, cancel Gamma #site
- [ ] Write real "How I work / What I'm looking for" copy (currently italic placeholder) #site
- [ ] Replace `now.md` placeholder with a real first entry #site
- [ ] Delete legacy empty file at `Career/Homepage Refresh/` #site
