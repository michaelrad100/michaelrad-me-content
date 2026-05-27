---
title: "Holstee Sprint Week One"
date: 2026-05-05
description: "First sprint kicked off: one post refreshed by hand, and the Shopify automation set up to take over from here."
draft: false
categories: [holstee, automation]
slug: holstee-sprint-week-one
---

I kicked off my first sprint this week. The focus is automating Holstee content updates. There's a healthy backlog of older posts that still pull search traffic but were written before anyone was optimizing for how people actually search today. The plan: refresh the first one or two by hand to find the friction, then automate each step as I go.

The first refresh was [Neurons That Fire Together, Wire Together](https://www.holstee.com/blogs/mindful-matter/neurons-that-fire-together-wire-together), a 2017 post originally written by my brother Dave. Small in word count, top performer for us by search impressions, and a conversion rate that's left a lot on the table. Did they first one manually to make sure i understood any of the quirks needing additional guardrails (I found three).

Once complete, I set up up the Shopify API connection and built a helper script (`shopify-refresh-article`) that takes a manifest file (new copy, SEO fields, FAQ schema, internal links) and ships the whole update in a single 20-second call. The same work used to take about 30 minutes of clicking through the admin. Each refresh from here on peels off another piece of the manual work and bakes it into the script.

Also I got a Pinterest helper (`pinterest-create-pin`) and its OAuth flow set up on the side. Every refresh should get a matching pin, and pinning by hand is one of those five-minute tasks with a painful transition cost. Whether the API actually plays nice is a next-week question. Till next week!
