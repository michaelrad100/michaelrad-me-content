---
title: "Holstee Sprint Week Two"
date: 2026-05-11
description: "Two refreshes shipped, the April health report ran, and the Pinterest API saga ended in a clean decision."
draft: false
categories: [holstee, automation]
slug: holstee-sprint-week-two
---

Felt like a turning-the-corner kind of week. A few things I'd been chipping away at for a while actually shipped, a couple of decisions I'd been sitting on got made, and a mid-week check-in clarified the priority for the rest of Runway in a way that made everything a lot cleaner.

Sprint 1 is essentially closed, and chunks of Sprint 2 got pulled forward into next week.

**The second refresh: Social Comparison Theory**

Last week's check-out covered the [Neurons refresh](/blog/holstee-sprint-week-one/) and the new API-driven publish flow. This week, [Social Comparison Theory](https://www.holstee.com/blogs/mindful-matter/social-comparison-theory) shipped Wednesday, a day ahead of schedule.

243,366 impressions a year, 106 clicks. CTR of 0.04%, the lowest of any post in the refresh backlog. Average position 10.74, right at the page 1 / page 2 boundary.

The title was `How do you compare? – Holstee`. A clever line, but it contains none of the words people are actually searching. The phrase "social comparison theory," which pulls 79K impressions a year on its own, only appeared in the URL slug. Google matched the URL and body content well enough to rank it at position 10 to 12, but every reader scanning the search results saw a title that didn't answer their question, and clicked SimplyPsychology or Wikipedia instead.

So the fix was simple: put the phrase people are searching into the title. Same structure as the Neurons refresh, same API publish path, one API call. Conservative estimate from the title change alone: 34x more clicks. We'll know in 30 to 90 days whether that holds.

Both refreshes have automated checks at 14, 30, 60, and 90 days. By August we'll know whether the format is actually working.

**April Monthly Health Report v0**

The sprint's main deliverable was the first end-to-end manual run of a 12-section read on the company: a summary, a per-section narrative, and a "what was painful" log.

The report draws from 12 data sources. Until this week, most of that data came in by hand. Once a month someone walked a loop: Stripe, Shopify, GA, Search Console, Klaviyo, Circle, QuickBooks, Pinterest, Meta Ads, Faire wholesale, exporting CSVs and copying numbers into the master spreadsheet. Most of a day of careful, repetitive work before any actual reading of the business could happen.

We're partway out of that loop. I built a Connections Registry alongside the Health Report, a single place that tracks every programmatic data connection. Six of the 12 sources are now scripted end-to-end: Shopify (orders and inventory), Stripe (monthly on a launchd schedule), GA4 (OAuth flow, new this week), Google Search Console, Pinterest analytics, and Klaviyo. Circle is mostly scripted, plus a custom script for event attendance. Slack is connected as a qualitative layer for context the numbers alone can't give. The other six stay manual by choice: the ones we pull infrequently cost more to automate than to just export by hand.

What changes is where the time goes. Instead of a day spent gathering, the first hour goes to reading: looking at the numbers, asking why, writing the narrative, capturing the "what was painful" entries that become next month's backlog. That's where the report starts earning its keep.

I think more small companies will move in this direction as these tools get cheaper and easier. A few years ago, composing a real monthly health report from a dozen separate sources was a data engineering project. Now it's a weekend of setup per source. For a five-person company that wants an honest read on its own business, that's a meaningful shift. Less time keeping the lights on, more time actually looking at what they show.

The most useful thing that happened during the run itself was an error I caught.

The original read showed active and trialing membership at 346 in April 2026 versus 522 in April 2025, a 34% year-over-year drop. The number felt off. We'd have noticed losing a third of our base. Dug in: April 2025 had a one-off promo that put 186 trialers in the count that month. Apples-to-apples on paying members only, the year was essentially flat, 336 to 329. Reran the script with the corrected definition and updated the summary.

The gut-check on a number that felt wrong is more reliable than I give it credit for, and worth slowing down for. The report only earns its keep when the comparisons it surfaces are honest. Getting there means defining "trialing" and "paying" and "active" precisely and using those definitions consistently. That's at least half the work.

**Pinterest API: the saga ends**

Got OAuth working this week. 81 boards readable. Then ran into Pinterest's documentation being misleading about Trial-tier access. The Trial tier is sandbox-only despite what the docs say, and moving to Standard requires a video demo and an open-ended review queue. The time already spent had passed the break-even point for just pinning manually through August.

Pulled the plug. Going manual through August, UTM-tagging every pin URL so we can measure pin-to-site traffic at the August review and decide then whether Pinterest is worth investing in further. The decision was easier to make than expected once I named the actual cost and benefit side by side.

**Mid-week strategic check-in**

A mid-week call to align on priorities for the Runway window. Three things came out of it.

Top-of-funnel is the explicit priority. The phrase that stuck: "we have a top-of-funnel problem." Everything else I'm doing, the refreshes, the Health Report, the Help Scout work, is in service of that or in service of making the work more legible to the team.

My role frame got clearer: contributor and builder. The face-of-the-community piece stays with the team. Useful to have that named explicitly, since "founder coming back" carries a default expectation I didn't want to inherit.

Kindreds (a community structure we've been iterating on) is pivoting to a time-zone-driven, member-led pilot. Different shape than where we'd been heading. Felt right.

**Sprints 2A and 2B pulled forward**

Help Scout assessment and the benchmark scorecard were both originally Sprint 2 work for the week of May 19. Both ended up substantially started this week. The scorecard has 5 of 7 sub-tasks done, with 15 levers across 7 categories captured. The Help Scout 90-day data pull surfaced that the Productivity sub-report isn't on our plan tier, so we're pivoting to the Conversations CSV. When work runs ahead of schedule, the right call is to pull more in.

**On deck**

Close out the April Health Report (final pass on the summary plus the "what was painful" log). Help Scout assessment full workflow Monday to Friday. Benchmark scorecard polish with April numbers and projected November targets. Amazon data-room readiness, which is acquisition packaging done pre-emptively. Slack `#notify` referrer-tracking audit.

Six items on the slate. Not light. Everything compounds toward the same priority.
