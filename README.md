# michaelrad.me — content vault

Markdown content for [michaelrad.me](https://michaelrad.me): blog posts and the rolling `/now` page. Authored in Obsidian as part of a larger personal vault, but this folder is its own git repo so it can be added as a submodule to the Astro site repo.

## Layout

```
.
├── blog/                 # one .md per post
├── now.md                # rolling "what I'm doing now" page
├── Hub.md                # Obsidian vault hub note (not rendered by the site)
└── README.md
```

## Frontmatter

**Blog posts** (`blog/<slug>.md`):

```yaml
---
title: "Post title"
date: 2026-05-03
description: "One-sentence summary, used in meta + RSS."
draft: false        # default true; set false to publish
tags: [meta, building-in-public]   # optional
---
```

**Now page** (`now.md`):

```yaml
---
title: Now
updated: 2026-05-03
---
```

## Obsidian-isms that get stripped on build

The Astro site runs a remark plugin that, for the published HTML:

- Replaces wikilinks `[[Some Note]]` (or `[[Note|alias]]`) with the plain text label
- Removes any list item that's an Obsidian Tasks-plugin checkbox (`- [ ]` or `- [x]`)
- Strips inline `#hashtags` from body text (frontmatter `tags` is the source of truth)

Author normally — those Obsidian conventions don't leak onto the site.

## Publishing flow

1. Edit a post in `blog/` or update `now.md`
2. Commit + push this repo
3. In the [Astro site repo](https://github.com/USER/REPO), bump the submodule pointer:
   ```
   git submodule update --remote content-vault
   git add content-vault && git commit -m "Update content" && git push
   ```
4. Railway rebuilds the site
