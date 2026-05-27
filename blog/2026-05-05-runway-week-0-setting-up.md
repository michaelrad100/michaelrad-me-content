---
title: "Runway Week 0: Setting up"
date: 2026-05-05
description: "The weekend the Sprint Plan came together, the 14 decisions that fell out, and the first refresh shipped via API."
draft: false
categories: [holstee, automation]
slug: runway-week-0-setting-up
---

I spent the weekend writing the Sprint Plan I introduced [last post](/blog/back-to-holstee/). Eight weeks, four 2-week sprints, hard deadline of June 30. I tried to fit everything into a looser "we'll see how the first sprint goes" frame, but the moment I wrote down the actual capacity number (15 hours a week from me, two streams in parallel, never three) the plan basically wrote itself.

Fourteen decisions came out of that weekend. Most are tactical: no Klaviyo work until email has a dedicated owner, product pages stay out of scope unless something breaks, no infrastructure unless it costs less than ten minutes to set up. A few set the spine of the work.

**The exit thread is on hold.** We had been keeping a soft option open on a possible acquirer conversation in November. I closed it for now. But the scorecard we'd be asked about becomes the benchmark for Sprint 2: where are we today, which numbers can actually move, what would "meaningfully better" look like by November. We earn back the conversation by improving on the things that mattered to it.

**The monthly health report runs by hand first.** Every "what was painful this run" gets logged, and that log becomes the automation backlog. I wanted to skip ahead and build the automation first. The reason I didn't: I hadn't run the process end-to-end even once, and it's hard to automate something you don't yet understand.

**Folder restructure.** Three weeks of overlapping folder names and duplicate docs finally got cleaned up. The Holstee Growth Engine subfolder flattened into Automation, old reference docs moved to `_reference/`, per-post subfolders created in Blog Content. Tedious work I'd been putting off, but Sprint 1 wouldn't have started cleanly without it.

**The week's actual ship: Neurons That Fire Together, refreshed and live.**

[Neurons That Fire Together, Wire Together](https://www.holstee.com/blogs/mindful-matter/neurons-that-fire-together-wire-together) is a post Holstee published in 2017, a short reflection (originally written by my brother Dave) on the Hebbian principle and gratitude. About 200 words. It also turns out to be Holstee's #17 post by Google impressions, with 146,623 over the trailing year and only 712 clicks. CTR of 0.49%, from an average position of 5.94.

The rank is fine. The conversion isn't. At 0.49% CTR for a query at position six, there are roughly 2,000 to 5,000 clicks a year sitting uncollected. Worth fixing.

In practice, a refresh meant expanding the body from around 200 words to 720: a definition, attribution to Donald Hebb, neuroplasticity context, and an FAQ block matching the actual queries people type, all wrapped around the original reflection, which we kept intact. New SEO title and meta description. FAQPage schema with 7 Q&A pairs. Five internal links added and three inbound links from related posts.

Every previous refresh was the same dance: write the copy in a doc, paste it into the Shopify admin, hand-edit the SEO fields, hand-add the FAQ schema HTML, and hope nothing got mangled in the move. This one shipped via a single API call from a new helper script (`shopify-refresh-article`), taking about 20 seconds. The same work used to run closer to 45 minutes.

The script is worth it on time alone. But the bigger shift is what the question becomes. Instead of "do I have the patience to do this in the admin today?" the question is "what's the manifest?" One leads to shipping more often.

**The published_at incident.**

While building the helper, I tried to stage the refresh by setting `published_at` to a future date, thinking Shopify would hold the article until then. Shopify silently rejected the future date and reset the publish date to right now, May 4, 2026. Nine years of original publish date, gone in seconds.

I caught it and manually restored the original date. The script now refuses any manifest that includes a `published_at` field. If a refresh briefly goes live during a swap, that's fine. It just never changes publish dates.

The lesson I'm taking forward: when an API silently behaves differently from how its docs describe, assume the worst and test on a sacrificial article first.

**Pinterest API integration prepped, not yet wired.**

Built `pinterest-create-pin` and an OAuth helper alongside the Shopify scripts. The theory: every refresh should get a matching Pinterest pin, and manual pinning is one of those five-minute tasks with a painful transition cost. Whether the API plays nice is a next-week question.

**On deck for the Sprint 1 close week**

Social Comparison Theory refresh on Thursday (similar profile to Neurons, more on it next week). April Health Report v0 end-to-end manual run on Friday. Pinterest OAuth and a first API-driven pin upload, if I can wedge it in.

If you're following along, this format is the weekly Slack check-out I share with the Holstee team, lightly translated for outside readers. Mike-as-narrator. Not a survey of what the whole team did this week. New ones every Monday through the end of June.
