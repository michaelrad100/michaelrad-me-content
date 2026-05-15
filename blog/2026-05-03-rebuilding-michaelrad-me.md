---
title: "Rebuilding michaelrad.me"
date: 2026-05-03
description: "Why I moved off Gamma. The stack, the calls I made along the way, and what I'd do again."
draft: false
categories: [meta, building-in-public]
slug: rebuilding-michaelrad-me
---

Until last week, michaelrad.me lived on Gamma. Gamma was good for what I needed in 2024: a polished one-page narrative with no maintenance. But the page had no surface for the work I've been doing since. No blog. No "what I'm working on" page. No place to set ARC and Vibe Check next to the longer Holstee story. So I rebuilt it.

The stack is Astro for the static site, Railway for hosting, and the blog and "now" page authored as plain markdown in my Obsidian vault. That last piece is the one I care most about. I write almost everything in Obsidian, meeting notes, weekly recaps, half-formed ideas. Building the site so the blog lives there too means writing a post is the same motion as writing any other note. No separate CMS, no friction tax.

A few decisions I made along the way that I think were right.

**Static, not server-rendered.** Astro can do server-rendering. I deliberately stayed static. The entire site is just HTML files, and "moving hosts" is half an hour, not three days. Railway today, somewhere else tomorrow if Railway raises prices or breaks. Optionality is cheap when you build for it from the start.

**Two repos, not one.** The site code lives in one repo. The content (blog markdown plus the "now" page) lives in a second. The site repo pulls the content repo at build time. Sounds fussy, but it means I can rewrite the site framework without touching content, and if I ever want someone else to author a post they only get the content folder.

**Obsidian conventions stripped on build.** My drafts are full of `[[wikilinks]]`, Tasks-plugin checkboxes, and inline `#hashtags`. None of those belong on a public site. A small remark plugin strips them out at build time. I write naturally in Obsidian; the published version is clean. Tags only come from the frontmatter, which is the source of truth.

**Drafts default invisible.** Every new post starts with `draft: true` and won't appear until I explicitly flip it. I can push half-finished thoughts to git anytime without worrying about them showing up live.

**Webhook automates the rebuild.** When I commit a post, a GitHub Action triggers Railway to rebuild. The post is live about 60 seconds later. I don't have to think about it.

What I'd do differently: I tried bridging the two repos with a git submodule, which is the textbook approach. It worked locally, but Railway's build container strips the `.git` directory before the build runs, so `git submodule update` had nothing to work against. After fighting it for a session, I switched to just `git clone` the content repo directly in the build command. Less elegant. Works first time. The lesson is one I keep relearning. When the elegant approach fights the platform, switch to the dumb one.

The site is live at michaelrad.me. The first posts about Holstee Runway are up. More to come.
