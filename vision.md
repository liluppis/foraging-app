# Foraging App: Product Vision

> **Status:** Draft v0.1 · **Last updated:** 2026-09-28 · **Owner:** Lisa Upperud
>
> This is a living document. It describes *why* the app exists and *what* it should achieve, not *how* it is built. Technical decisions are recorded as ADRs in `docs/adr/`, and features are broken down into user stories in the backlog.

## Vision statement

For foragers in the Stockholm region who want to find mushrooms and berries more reliably, the Foraging App is a mobile map companion that **remembers where you have found things** and **helps you read the landscape**. It is different from general map apps in three ways: it combines your personal finds with information about forest type, soil and terrain; it keeps your spots private; and it works without reception.

## Background and problem

Finding mushrooms and berries is largely about reading nature: tree species, forest age, soil, moisture and terrain. This knowledge takes years to build, and personal experience is easily lost:

- Last season's chanterelle spot is hard to find again.
- Photos from the forest end up in the camera roll without context and cannot easily be compared year to year.
- It is hard to know which parts of a forest you have already explored.
- Reception in the forest is often poor, so apps that depend on a connection fail exactly when they are needed.

## Target user

**Primary:** Me. I am a hobby forager in the Stockholm area who goes out several times per season, on foot, often with one hand busy and the phone in a pocket.

**Secondary (future, out of scope for now):** Other foragers who might want to use the app for their own finds.

## Goals

1. **Understand the landscape.** See forest type, soil and terrain on the map. Search for a habitat (e.g. "lime-rich soil" or "old-growth spruce forest") and have matching areas highlighted.
2. **Remember finds.** Pin a find with a species icon, a photo and a date, and compare the same spot across seasons.
3. **Plan outings.** Plan a route past pinned spots and into unexplored areas, and see where I have been before.
4. **Stay present in the forest.** Get a notification when approaching a pinned spot, so I can slow down and look around.
5. **Learn.** Use a small built-in encyclopedia that links species to the habitats where they grow.
6. **Work offline.** Everything needed for an outing works without reception, and finds logged offline are synced when the connection returns.

## A day with the app (key scenario)

**The evening before.** I want chanterelles. I search for mossy spruce and mixed forest near home, and the map highlights matching areas. I see my chanterelle icons from last year and draw a route past three of them and through an area I have never explored. The app downloads the map and data I need for the area.

**In the forest.** I have no reception, but the map, my pins and the route all work. My phone buzzes as I approach a pinned spot, so I slow down. I find chanterelles, pick the chanterelle icon, take a photo and save. It takes a few seconds.

**Back home.** The phone reconnects and my new finds sync. I compare today's photo with last year's from the same spot, and I can see which parts of the forest I have now covered.

## Non-goals

- **No species identification or edibility advice.** The encyclopedia is educational only and must never be presented as a way to determine whether something is safe to eat.
- **Not a social network.** Finds are private. Sharing is not part of the current scope.
- **Not nationwide from the start.** The initial focus is the Stockholm region.
- **Not a turn-by-turn navigation app.**

## Guiding principles

- **Private by default.** Foraging spots are personal and sensitive data.
- **Offline-first.** The app should assume there is no connection and treat a connection as a bonus.
- **Safety over convenience.** Species information is always accompanied by clear limitations.
- **Battery-conscious.** A day in the forest should not drain the phone.
- **Fast in the field.** The core actions work with one hand in a few seconds.

## Success criteria

- The app is used on real outings during the next foraging season.
- A find can be logged in under 30 seconds, one-handed, without reception.
- Next season, I can find my way back to the spots I pinned.
- No logged finds are lost because of missing reception.

## Open questions

- **Nature data:** Where do forest type, soil and terrain data come from? Candidates to investigate include open data from SGU (soil and bedrock), Naturvårdsverket (land cover), Skogsstyrelsen (forest data) and Lantmäteriet (maps). For each, check the license, the format and whether it can be used offline.
- **Habitat to species mapping:** How is "lingonberries grow in this type of nature" defined, and from which sources?
- **Backend or local-only?** Is a server needed in the MVP, or is on-device storage enough? A server brings accounts, security and hosting costs.
- **Encyclopedia content:** Who writes it, which sources is it based on, and how is copyright handled?
- **Route planning:** Should routes be drawn manually or suggested automatically?
- **"Where I've been":** Should this be based on recorded GPS tracks? If so, what does that cost in battery?
- **Proximity notifications:** What do background location and geofencing limits look like on iOS and Android?
- **Offline maps:** How large an area should be downloaded, and how much storage does it need?
