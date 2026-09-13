---
layout: post
title: "The Day the Website Disappeared"
date: 2026-12-14
description: "A client who runs a law firm deleted her entire website by accident, and I had it restored within hours. What that teaches a firm without an IT department, plus a restore drill you can run this month."
image: "/images/27_the_day_the_website_disappeared.png"
categories: [Technology Strategy, Business Continuity]
tags: [backups, incident response, disaster recovery, small business, website]
---

I helped a client launch her law firm from the ground up, including logo design, full website development, automation systems and marketing campaigns. While she was editing the site, she deleted the entire website by accident.

Within hours, I had everything restored.

Picture the same moment at your firm. Your website, your shared drive or your client database vanishes because someone with a valid login clicked the wrong thing. Ask yourself two questions: who would you call, and could that person put it back?

The second question carries more weight than it looks, because a yes depends on two things you can check this month: a backup that someone has tested with a real restore, and a named person who knows how to run that restore under pressure.

## The outage you don't plan for

The IT disasters that make the news involve ransomware and hacked accounts. Those risks deserve a plan. The outage in my client's case came from a person doing an ordinary task with the access her job required.

You can't train that risk away. Staff will keep editing web pages and deleting files, because their work depends on that access. You manage the risk by making sure a known person can restore what gets lost.

## My own backups had damage I couldn't see

I hold my own infrastructure to the same test, and it failed part of it.

I run nightly backups with a tool called restic. A full read check reads back every piece of stored data instead of trusting the summary, and when I ran one, it found 8 damaged blobs across 1,718 packs. I traced the damage to a bad stick of RAM.

I moved everything to a new backup repository, verified that repository clean, and restored files to confirm they came back byte-identical to the originals.

That part ended well. The uncomfortable part remains: I also built a bare-metal recovery image, meant to rebuild the whole server from nothing, and I haven't test-booted it. Until I do, that recovery path counts as a hope rather than a plan. I'm telling you so you don't accept "we have backups" at face value from anyone, including yourself.

## A restore drill for firms without IT staff

Block two hours this month. Bring the person who manages your website and your IT provider, if you have one.

**Write down where everything lives.** List your website host, your domain registrar, your email provider and each system that holds client files. Next to each, note who holds the admin login and where it's stored. A registrar account tied to a former employee's email address can stall a recovery for days.

**Ask for a restore, then watch it happen.** Pick one real item: a deleted folder from last week, or a copy of your website on a test address. Time it from request to finish. A backup you haven't restored is a backup you believe in without evidence.

**Check how far back you can go.** A backup that keeps yesterday's copy and nothing older can't help if no one spots a deleted folder for two weeks. Ask each provider how many days of history they keep.

**Keep one copy out of reach of everyday logins.** If the same account that can delete your files can also delete your backups, one mistake or one stolen password takes out both. Ask your provider whether a separate account, or a copy stored somewhere else, protects at least one version of each system.

**Name the person and the deadline.** Decide who you call if the website or file server disappears, and how many hours your firm can operate without it. Put both on one page, and keep a printed copy somewhere other than the systems it describes.

**Run it again.** Repeat the drill at least once a year, and every time you change IT providers or website hosts.

## The call you want to be able to make

I had my client's website back within hours of the deletion.

If you can't name that person for your own firm today, I can help you write the one-page plan and run the first drill with you. [Book a free 30-minute call](https://cal.com/brianfranzen/first30min), or read about my services and published pricing at [b4help.com](https://b4help.com).
