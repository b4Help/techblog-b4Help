---
layout: post
title: "Fourteen Years on One Virtualization Platform"
date: 2026-11-23
description: "Lessons from running the same Proxmox test environment since around 2012, and what a permanent place to test has taught me about deploying anything new."
image: "/images/24_fourteen_years_one_platform.png"
categories: [Infrastructure, Technology Strategy]
tags: [Proxmox, virtualization, testing, infrastructure, fractional CTO]
---

Thanksgiving week slows the office down, and I use the quiet to take stock. This year I kept coming back to one machine, or to be precise, to the platform that has moved across a series of machines since around 2012.

I have run Proxmox, an open-source virtualization platform, for about fourteen years. It started as a place to try things without breaking anything that mattered, and it still serves that purpose.

## A platform that outlived its hardware

The server under it has changed several times. Parts aged out, I replaced them, and the platform moved to the new hardware. Today it runs on an Intel i7-7700K with 32GB of RAM, a machine that wouldn't impress anyone shopping for a server in 2026.

The hardware turned out to matter least. The value came from having the same place to test for fourteen years, with habits built around it.

## What runs on it

The environment serves as a test bed. It holds Linux distributions, Windows installations, and server software I want to evaluate before it goes anywhere near a real deployment. If a client runs a particular version of Windows, I can stand that version up and try the change there first.

That sounds basic, and it is. If your firm has no equivalent, your test environment is the production system on a Tuesday afternoon.

Virtual machines make the habit cheap. You can copy a system, break the copy on purpose, and delete it when you've learned what you needed. The real system keeps running for the people who depend on it, and the people at your front desk carry on without noticing you tried something.

## Lessons I carried out of the lab

### Test on the system you'll deploy to

Software that works on my laptop tells me little about how it behaves on a client's Windows machine with their security software and their settings. A virtual copy of the target system catches the problems that documentation and vendor promises don't mention. You learn more from twenty minutes on the real target than from a day of reading about it. Your own office works the same way. A change that runs fine on a partner's new laptop can still break the five-year-old desktop at the front desk, and you want to find that out before the Monday rush.

### Keep the platform and replace the parts

I've swapped hardware several times and kept the platform. The skills, the procedures and the knowledge of how the system behaves carried over each time. Firms that change their core tools every few years start that learning from zero with every change. Before you replace a system your staff know well, price the relearning along with the license.

### Choose tools you can run for a decade

A tool you'll depend on for years has to survive vendor changes, price increases and the departure of the person who set it up. Fourteen years on one platform showed me the value of picking software with a long track record and an open format underneath. It also taught me to write down how things are set up, because the person who remembers will leave one day.

## Something for your firm to try

You don't need a server to borrow this habit. Pick the next change you plan to make, whether a software update, a new tool or a settings change, and try it on one machine that doesn't hold anything critical before it touches the rest of the office. Keep a short written note of what you tested and what happened.

A spare machine and a notebook catch the expensive mistakes before your staff run into them.

## Thank you

This is the week I think about the people who have trusted me with their networks, their systems and their questions over more than twenty-five years in this work. Thank you. That trust is the reason I'm building this practice.

I'm taking on three founding clients at $6,000 a month instead of my standard $8,500, month to month, in exchange for a testimonial and permission to write up the results as a case study. If your firm could use a senior technology leader who tests before he deploys, [book a free 30-minute call](https://cal.com/brianfranzen/first30min) after the holiday. Details and pricing are at [b4help.com](https://b4help.com).
