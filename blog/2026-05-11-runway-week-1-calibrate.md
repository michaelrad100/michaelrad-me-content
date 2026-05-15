---
title: "Runway Week 1: Calibrate"
date: 2026-05-11
description: "Two refreshes shipped, the April health report ran, and the Pinterest API saga ended in a clean decision."
draft: false
categories: [holstee, automation]
slug: runway-week-1-calibrate
---

Felt like a turning-the-corner kind of week. A few things I'd been chipping away at for a while actually shipped, a couple of decisions I'd been sitting on got made, and a mid-week strategic check-in clarified the priority for the rest of Runway in a way that made everything downstream simpler.

Sprint 1 is essentially closed. Chunks of Sprint 2 got pulled forward into next week.

**The second refresh: Social Comparison Theory**

Last week's check-out covered the [Neurons refresh](/blog/runway-week-0-setting-up/) and the new API-driven publish flow. This week, [Social Comparison Theory](https://www.holstee.com/blogs/mindful-matter/social-comparison-theory) shipped Wednesday, a day ahead of schedule.

If Neurons was an asset converting poorly, Social Comparison Theory is closer to an asset *invisible*. 243,366 impressions a year, 106 clicks. CTR of 0.04% — the lowest of any candidate in our refresh backlog. Average position 10.74, straddling the page 1 / page 2 boundary.

The diagnosis was sharper than usual. The current SEO title was `How do you compare? – Holstee`. A clever Holstee-voice headline, but one that contains zero of the search terms readers are actually typing. The verbatim head query (`social comparison theory`, 79K impressions a year) was in the URL slug only. Google was matching the URL plus body content strongly enough to rank pos 10–12, but every reader scanning a SERP saw a title that didn't answer their question and clicked SimplyPsychology or Wikipedia instead.

So the highest-leverage move was the simplest one: rewrite the title to actually contain the head query. Same body shape as Neurons (definition, attribution, FAQ, original Holstee voice in the middle), same publish path (one API call). Conservative scenario, just from the title fix and structure: a 34× lift in clicks. We'll know within 30 to 90 days whether the model holds.

Both refreshes have 14/30/60/90-day Search Console checks scheduled to fire automatically. By August we'll know whether the format is moving the needle or just feels good.

**April Monthly Health Report v0**

This was Sprint 1's banner deliverable: the first end-to-end manual run of a 12-section read on the company. TL;DR plus per-section narrative plus a 12-entry "what was painful" log.

The report draws from 12 data sources. Up until this point, much of that data was manually gathered. Once a month someone walked a recurring loop, Stripe → Shopify → GA → Search Console → Klaviyo → Circle → QuickBooks → Pinterest → Meta Ads → Faire wholesale → and so on, exporting CSVs and copying KPIs into the KPI sheet, the master spreadsheet that fed the report. That work took most of a day. Meticulous, low-creativity, and only the first step before any actual interpretation could begin.

We're partway out of that loop. I built a Connections Registry alongside the Health Report as the single source of truth for every programmatic connection. Six of the 12 sources are now scripted end-to-end: Shopify (orders + inventory), Stripe (auto-pulled monthly on a launchd schedule), GA4 (OAuth flow, newly added this week), Google Search Console, Pinterest analytics, and Klaviyo. Circle for community is partially scripted (most things, plus a custom script for event attendance). Slack is wired in too, as a qualitative gap-filler for the moments where the numbers don't tell the whole story. The remaining six stay manual CSV by choice. The cost to automate the ones we touch infrequently (Meta Ads, Faire wholesale payouts) is higher than the cost to keep exporting them by hand.

What that shift actually unlocks is the time previously spent on the gathering. We can spend it instead on the part of the work that creates value: looking at the numbers, asking why, writing the narrative, capturing the "what was painful" entries that become next month's automation backlog. The qualitative layer on top of the quantitative pull is where the report starts earning its keep.

I think more small companies will move in this direction as these tools become readily available. A few years ago, the data engineering work to compose a real monthly health report from a dozen disparate sources sat outside the budget of a 5-person company. Now it's a weekend's setup per source. For resource-tight teams that still want a real read on their own business, the unlock is significant. It moves the work from maintenance mode (keeping the lights on with manual refreshes) toward the activities that actually create value, for customers and for the business.

The most useful thing that happened during the run itself was an error I caught.

The original "active+trialing membership: 346 in April 2026 versus 522 in April 2025" looked like a brutal year-over-year drop, around 34%. My gut said the number felt off. We'd have noticed losing a third of our base. Dug in: April 2025 had a one-off promo that put 186 trialers in the count that month. Apples-to-apples on paying members only, the year was essentially flat: 336 → 329. Re-ran the script with the corrected definition, updated the TL;DR, captured the lesson.

The fact-checking instinct on a number that "felt off" is more reliable than I tend to credit, and worth slowing down for. The Health Report also only really earns its keep when the comparisons it surfaces are honest, which means defining "trialing" and "paying" and "active" precisely and consistently is half the work.

**Pinterest API: the saga ends**

Got OAuth working this week. 81 boards readable. Then ran into Pinterest's documentation being misleading about Trial-tier capabilities. The Trial tier turns out to be sandbox-only despite what the docs say, and the Standard upgrade requires a video demo plus indefinite review. Time I'd already sunk had overrun the cost of doing pins manually for the rest of the year.

Pulled the plug. Going manual through August, UTM-tagging every pin URL so we can measure pin to site traffic at the August review and decide then whether Pinterest is worth investing in further. Decision was easier to make than expected once I named the actual cost and benefit side by side.

**Strategic check-in with Amy + Dave**

Mid-week call to align on priorities for the Runway window. Three things came out of it.

Top-of-funnel is the explicit priority. The phrase Amy used: "we have a top-of-funnel problem." Everything else I'm doing, the refreshes, the Health Report, the Help Scout work, is in service of that or in service of making the work more legible to the team.

My role frame got clearer: contributor and builder. The face-of-the-community piece stays with the team. Useful to have that named explicitly, since "founder coming back" carries a default expectation I didn't want to inherit.

Kindreds (a community structure we've been iterating on) is pivoting to a time-zone-driven, member-led pilot. Different shape than where we'd been heading. Felt right.

**Sprints 2A and 2B pulled forward**

Help Scout assessment and the benchmark scorecard were both originally Sprint 2 work for the week of May 19. Both ended up substantially started this week. The scorecard is 5 of 7 sub-tasks done, with 15 levers across 7 categories captured. The Help Scout 90-day data pull surfaced that the Productivity sub-report isn't on our plan tier, so we're pivoting to the Conversations CSV. When sprint work runs ahead of schedule, the right move is usually to pull more in, not slow down.

**On deck**

Close out the April Health Report (final pass on the TL;DR plus the "what was painful" log). Help Scout assessment full workflow Mon to Fri. Benchmark scorecard polish with April numbers and projected November targets. Amazon data-room readiness, which is acquisition packaging done pre-emptively. Slack `#notify` referrer-tracking audit.

Six items on the slate. Not light. Everything compounds toward the same priority.
