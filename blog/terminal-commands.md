---
title: "Terminal commands"
date: 2026-05-15
description: "Quick reference for pushing content to the site."
draft: true
---

## Push blog content to the site

Run this once in Terminal to activate the `push-blog` command (only needed after opening a new Terminal window for the first time, or once if it's not working):

```
source ~/.zshrc
```

Then any time you want to push new content or images:

```
push-blog
```

That's it. Commits everything in the content folder and pushes to GitHub, which triggers a Railway rebuild. Site updates in ~2 minutes.

---

## Full one-liner (if push-blog ever isn't working)

```
cd ~/Documents/claude/cowork/michaelrad.me && git add . && git commit -m "Update content" && git push
```
