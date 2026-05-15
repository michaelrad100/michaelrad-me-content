---
title: "Runway Week 0: Setting up"
date: 2026-05-05
description: "The weekend the Sprint Plan came together, the 14 decisions that fell out, and the first refresh shipped via API."
draft: false
categories: [holstee, automation]
slug: runway-week-0-setting-up
---

Spent the weekend writing the Sprint Plan I introduced [last post](/blog/back-to-holstee/). Eight weeks, four 2-week sprints, hard ship deadline of June 30. I tried for a while to fit everything into a more flexible "we'll see how the first sprint goes" frame, but the moment I gave myself the actual capacity number (15 hours/week from me, two streams in parallel, never three) the plan basically wrote itself.

What fell out of that weekend was 14 governing decisions for the period. Most are tactical: no Klaviyo work until Kim is fully onboarded, product pages stay out of scope unless something breaks, no infrastructure unless it costs less than 10 minutes of my time to set up. A few set the spine of the work.

**The exit thread is on hold.** We had been keeping a soft option open on a possible acquirer conversation in November. I closed it for now. But the scorecard we'd be asked about *becomes* the benchmark for Sprint 2: score current state, identify movable levers, define what "demonstrable improvement" looks like. We earn back the optionality by improving on the things that mattered to that conversation.

**Monthly Health Report stays solo and manual for v0 and v0.5.** Every "what was painful this run" gets logged, and that pain log becomes the v1 automation backlog. I wanted to skip ahead and build the automation now. The decision to wait was about resisting building infrastructure for a process I haven't actually run end-to-end yet.

**Folder restructure.** Three weeks of "a few different names are being used to march toward the same goal" finally got reorganized. The Holstee Growth Engine subfolder flattened into Automation. Old reference docs moved to `_reference/`. Per-post subfolders created in Blog Content. Boring housekeeping work I'd been deferring. Couldn't have started Sprint 1 cleanly without it.

**The week's actual ship: Neurons That Fire Together, refreshed and live.**

[Neurons That Fire Together, Wire Together](https://www.holstee.com/blogs/mindful-matter/neurons-that-fire-together-wire-together) is a post Holstee published in 2017, a short reflection (originally written by my brother Dave) on the Hebbian principle and gratitude. About 200 words. It also turns out to be Holstee's #17-ranked URL by Google search impressions: 146,623 impressions over the trailing year, but only 712 clicks. CTR of 0.49%. The post sits at average position 5.94, top of page 1. So the lever isn't earning rank, it's converting the impressions we already have. At 0.49% CTR for an informational query at that rank, we're leaving roughly 2,000 to 5,000 clicks a year on the table. That's the kind of asset that justifies a refresh.

What "refresh" actually meant: ~720 words of new body (definition, attribution to Donald Hebb, neuroplasticity context, an FAQ block answering the actual queries people are typing, all woven around the original 200-word reflection which we kept intact as the voice anchor); a new SEO title and meta description rewritten to match the queries; FAQPage JSON-LD with 7 question-answer pairs; 5 new internal links and 3 new inbound links from sibling posts.

Every previous refresh I'd done was the same dance: write copy in a doc, paste into the Shopify admin, hand-edit the SEO fields, hand-add the FAQ schema HTML, hope nothing got mangled in the move. This time it shipped via a single API call from a new helper script (`shopify-refresh-article`). The whole publish step took about 20 seconds. Previously, ~45 minutes of clicking and double-checking.

That alone justifies the helper. The bigger payoff is what it unlocks. I can think of refreshes as "what's the manifest" instead of "do I have the patience to do this in the admin today." Lower friction means more refreshes ship.

**The published_at incident.**

While building the helper, I tried to "stage" the refresh by setting `published_at` to a future date, the idea being Shopify would hold the article until that date. Shopify silently rejected the future date AND reset the publish date to NOW (May 4, 2026). The 9-year SEO trust signal of the original 2017 publish date wiped in seconds.

I caught it. Manually restored the original date in admin, choosing 2017-11-26 to match the original month and day. Sanitized the script so it now refuses any manifest containing a `published_at` field. Going forward, the refresh script never touches publish state. If a refresh briefly goes live during a swap, that's fine.

The lesson I'm taking forward: when an API silently behaves differently from how its docs describe, assume the worst and test on a sacrificial article first.

**Pinterest API integration prepped, not yet wired**

Built `pinterest-create-pin` and an OAuth helper alongside the Shopify scripts, on the theory that every refresh wants a matching Pinterest pin and manual pinning is one of those "5 minutes that adds up to a workday over the year" tasks. Won't know whether the API plays nice until I do the OAuth dance in a fresh session next week.

**On deck for the Sprint 1 close week**

Social Comparison Theory refresh on Thursday (similar profile to Neurons, more on it next week). April Health Report v0 end-to-end manual run on Friday. Pinterest OAuth and a first API-driven pin upload, if I can wedge it in.

If you're following along, this format is the weekly Slack check-out I share with the Holstee team, lightly translated for outside readers. Mike-as-narrator. Not a survey of what the whole team did this week. New ones every Monday through the end of June.
