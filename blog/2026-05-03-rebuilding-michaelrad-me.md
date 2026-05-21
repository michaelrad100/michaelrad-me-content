---
title: Rebuilding michaelrad.me
date: 2026-05-03
description: Why I rebuilt this site and powered by a note taking app. Here's the stack, how I did it, and what I'd do again.
draft: false
categories:
  - meta
  - building-in-public
slug: rebuilding-michaelrad-me
---

Until last week, michaelrad.me was built on [Gamma](https://gamma.app/). Gamma is incredibly fast way to get up a single page site, but as my personal page, I increasingly felt it was missing two things: space for my writing and for my past work. In the process I explored options like [framer](https://www.framer.com/ai/) and other ai site building platforms. There's many impressive options in this space now.

Ultimately, I wanted something that didn't lock the site or it's content into a platform and I wanted the backend to be as simple to manage as possible. 

As a regular note taker in Obsidian, I wondered if I could have a folder that basically acted like the CMS for the site? Where getting up a new blog post could be as simple as creating a note.

In the age of ai, I've learned to live by the mantra "ask and you will probably receive." (more on how Obsidian super charged my claude code experience here). Long story short, that exactly how this site was built.

The stack is [Astro](https://astro.build/) for the static site, [Railway](https://railway.com/) for hosting, and the blog and "now" page authored as plain markdown in my [Obsidian](https://obsidian.md/) vault. It took a bit of back and forth to get everything dialed in but it's honestly everything I imagined. Frictionless to edit or transition to different set up if needed, and nearly free to operate.

![[CleanShot 2026-05-15 at 09.21.05.png]]

Incase you are thinking to do the same, here are a a few decisions I made along the way that I think were right.

**Drafts default invisible.** Every new post starts with `draft: true` and won't appear until I explicitly flip it. I can push half-finished thoughts to git anytime without worrying about them showing up live.

**Static, not server-rendered.** Astro can do server-rendering. I deliberately stayed static. The entire site is just HTML files, and moving hosts is half an hour, not three days. Railway today, somewhere else tomorrow if the situation changes. The flexibility costs nothing if you build for it early.

**Two repos, not one.** The site code lives in one repo. The content (blog markdown plus the "now" page) lives in a second. The site repo pulls the content repo at build time. Sounds fussy, but it means I can rewrite the site framework without touching content, and if I ever want someone else to author a post they only get the content folder. (personal note: i think this happened more bc it was a pain to combine the folder due to how i initially structured the hierarchy, not sure id recommend this)

**Obsidian conventions stripped on build.** My drafts are full of `[[wikilinks]]`, Tasks-plugin checkboxes, and inline `#hashtags`. None of those belong on a public site. A small remark plugin strips them out at build time. I write how I write, and the published version comes out clean. Categories come from the frontmatter only. (see image above)

**Webhook automates the rebuild.** When I commit a post, a GitHub Action triggers Railway to rebuild. The post is live about 60 seconds later. I don't have to think about it.

What I'd do differently: I tried bridging the two repos with a git submodule, which is the textbook approach. It worked locally, but Railway's build container strips the `.git` directory before the build runs, so `git submodule update` had nothing to work against. After fighting it for a session, I switched to just `git clone` the content repo directly in the build command. Less elegant, and it works first time. The lesson is one I keep relearning: when the elegant approach fights the platform, switch to the dumb one.

It's been a fun one to build. What a time to be alive.
