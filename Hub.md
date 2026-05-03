# michaelrad.me

**Project:** [[Career/Career|Career]]
**Code & plans:** `~/Documents/claude/code/michaelrad.me/` — Astro codebase, deploy config, and all planning docs (`michaelrad.me — Astro Rebuild Plan.md`, `michaelrad.me — Home Page Refresh Plan.md`, `drafts/`)

*Vault hub for content authored in Obsidian and pulled into the Astro build at deploy time. The site code and planning docs live in `code/`; this folder is for the markdown the site renders.*

---

## Site sections authored here

- **`blog/`** — one .md per post. Astro reads from `content-vault/blog/` (a submodule pointing to this folder once Phase 4 is done).
- **`now.md`** — rolling "what I'm working on now" page, single file.

## How publishing works

1. Edit a post in `blog/` or update `now.md` here.
2. Commit + push (this folder will be its own private git repo, separate from the cowork vault).
3. The Astro repo bumps its submodule pointer; Railway rebuilds the site.

(For Phase 0 / pre-deploy: edit-in-place locally, no push step yet.)

---

## Recent notes

*(none yet — folder created 2026-05-03)*

---

## Tasks

- [ ] Confirm layout in [Astro Rebuild Plan](file:///Users/michaelradparvar/Documents/claude/code/michaelrad.me/michaelrad.me%20%E2%80%94%20Astro%20Rebuild%20Plan.md) #career
- [ ] Decide blog frontmatter schema before drafting first post #career
- [ ] Write first "now" entry once Phase 3 is wired #career
