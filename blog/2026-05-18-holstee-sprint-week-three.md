---
title: "Holstee Sprint Week Three"
date: 2026-05-18
description: "Kim's 14-year KPI sheet started filling itself in, QuickBooks came off manual export, and Google's AI Overview showed up in the search numbers."
draft: false
categories: [holstee, automation]
slug: holstee-sprint-week-three
---

Some weeks the work shows up on the website. This wasn't one of them. No refresh went live, no new post.

Back in [Week One](/blog/holstee-sprint-week-one/) I wrote about wanting to skip ahead and build the reporting automation, and making myself wait until I'd run the process by hand first. This was the week the wait ended. The whole thing happened underneath, and it was the most satisfying week of Runway so far.

**The KPI sheet fills itself in now**

Holstee has kept a KPI sheet since 2012. Every month a new row goes in: web traffic, Shopify sales and conversion rate, wholesale, membership, the accounting numbers. Fourteen years of the business sitting in one spreadsheet, every cell of it typed in by hand from a dozen separate dashboards.

That row assembles itself now. Five scripts pull the numbers, an orchestrator drops a draft row into the sheet, and it gets reviewed instead of built from scratch. The accounting figures alone used to mean a manual QuickBooks export every month, and those come through an API now too.

We checked it against the hand-entered April numbers before trusting it with anything. Shopify revenue matched to the cent. Conversion rate matched. Wholesale matched across five straight months. Web traffic came in within half a percent. There's a particular kind of confidence that only arrives when a script reproduces a number a person built by hand. That was this week.

One thing surfaced while building it. The membership numbers were supposed to come from Circle, the platform our community runs on. Circle, it turns out, exposes no billing data through its API at all. So we pulled membership straight from Stripe, which sits below Circle and is where the money actually moves.

Stripe was also more honest. It counted five membership cancellations in April. The number the team had been tracking by hand said two. The reporting only earns its place if the numbers in it are honest, and both weeks of this build so far have turned up one that wasn't.

**The AI Overview showed up in the numbers**

Two refreshed posts hit their 14-day check this week, Enjoying the Little Things and Best Journaling Apps. Both showed the same strange shape: impressions up sharply, clicks down, click-through rate down with them.

The cause is Google's AI Overview, the answer box that now sits at the top of a lot of search results. Google is reading our refreshed posts, answering the reader's question inside that box, and citing Holstee while it does. The reader gets the answer and never has a reason to click.

So the posts are working. They ranked, they got crawled, they're good enough that Google is quoting them directly. Enjoying the Little Things is now the number one organic result for "enjoy the little things." The click numbers barely moved.

I don't have a tidy answer for this yet. We refreshed these posts to turn impressions into clicks, and now the impression often resolves inside Google before a click can happen. The brand still gets seen and the reader still gets helped, so whether that counts as the post working depends on what we were really after. I'm still sitting with it. The 30-day checks at the end of May are the next real read.

**The $11,000 Amazon question**

An agency pitched us four months and eleven thousand dollars to optimize Holstee's Amazon channel. It's real work, and they would probably do it well.

Before committing to it, the team scoped what a first pass could cover in-house: a listing audit for each product, a keyword and search-term review, a look at how the ad campaigns are built, pricing and reviews, and a ranked list of what to fix over the next couple of months. Most of that is within reach. The real gaps are product photography and A+ content design, the parts that need a designer.

So the audit goes into a June sprint instead of a check going out now. If the in-house pass shows the channel needs more than we can do ourselves, the agency conversation is still there, and we'll walk into it with a sharper question. A sharper question is a cheaper one to hand an agency.

**#notify can see again**

Holstee has a Slack channel called #notify. Every paid order and every new membership lands there, so the team watches sales arrive in real time. For a while now, the line that says where each sale came from had been blank. The orders showed up. The source didn't.

I traced it to a broken Zapier setup and rebuilt both notifications. Orders now arrive with their source, campaign, and landing page, and whether the buyer is new or returning. Membership signups carry their source too, plus a flag for whether the person paid full price or came in on a promo.

[Last week's check-in](/blog/holstee-sprint-week-two/) named top-of-funnel as the priority for the rest of Runway. You can't put attention on top-of-funnel if you can't see which funnel a customer came through. This week, #notify can see again.

**On deck**

The KPI sheet gets its first live run with the May close. That's the real test, the auto-built row next to the one built by hand. The 30-day checks on Enjoying the Little Things and Best Journaling Apps land at the end of the month and should tell us whether the AI Overview pattern holds. Amazon API credentials are still working their way through. And the next refresh candidate gets pulled from the backlog.

Back to work that's visible from the outside next week.
