---
title: "Runway Week 1: Calibrate"
date: 2026-05-11
description: "Two blog refreshes shipped, the first monthly health report, and a Pinterest decision."
draft: false
tags: [holstee, automation]
slug: runway-week-1-calibrate
---

First week of [Runway](/blog/back-to-holstee/). Felt like a turning-the-corner kind of week. A few things I'd been chipping away at for a while actually shipped, and a couple of decisions I'd been sitting on got made.

**What shipped**

Two blog refreshes. Neurons That Fire Together went up Monday, the first refresh ever published via API instead of pasting into the Shopify admin. Social Comparison Theory followed Wednesday, a day ahead of target.

April Monthly Health Report v0. First end-to-end manual run of a 12-section read on the company. Built a Connections Registry alongside it as the single source of truth for the data sources. Six of twelve are now programmatic. The rest are manual CSV by choice for now.

Caught a real error mid-run. The original "active+trialing membership, 346 this April vs 522 last April" looked like a 34% drop. Turned out April 2025 had a one-off promo that put 186 trialers in the count. Apples-to-apples, paying-only, the year was essentially flat. Fixed the script, re-ran, updated the TL;DR. Trusting a gut feel on a number that "felt off" is worth more than I tend to credit.

**Decisions I made**

Paused the Pinterest API pursuit. OAuth landed (81 boards readable), but the Trial tier is sandbox-only despite docs saying otherwise, and the Standard upgrade requires a video demo plus indefinite review. Time already sunk had overrun the cost of doing pins manually for a year. Going manual through August, UTM-tagging every pin so we can measure whether Pinterest is worth continuing to invest in.

**What I'm thinking about**

Top-of-funnel is the explicit priority for Holstee right now. The blog refreshes are one investment in that. Thinking about what the next one or two should be. Roel scorecard work this week should sharpen the picture.

**On deck**

Help Scout assessment. Roel benchmark scorecard polish. Amazon data-room readiness. Slack `#notify` referrer audit.
