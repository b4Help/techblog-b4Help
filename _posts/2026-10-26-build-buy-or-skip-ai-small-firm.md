---
layout: post
title: "Build, Buy, or Skip: Deciding on AI for a Small Firm"
date: 2026-10-26
description: "A decision framework for small firms weighing an AI project: when to buy an off-the-shelf tool, when to build something private, and when to leave the task alone."
image: "/images/20_build_buy_or_skip_ai.png"
categories: [AI Strategy, Technology Strategy]
tags: [AI strategy, build vs buy, small business, private AI, fractional CTO]
---

A software rep emails you about an AI assistant for your team. One of your partners read an article about building a custom model. An employee has started pasting work files into a free chatbot. You now have three AI decisions in front of you, and you can't answer them the same way.

I use one framework for all of them. It sorts every AI proposal into build, buy, or skip, and you can run it on a sheet of paper.

## Name the task before you look at a tool

Write the job down in one sentence, with a person and a number in it. "Our paralegals spend six hours a week summarizing transcripts" is the kind of sentence you want. It tells you who does the work, how much time it eats, and what a tool would have to beat.

"We should use AI" leaves you with a purchase and no way to judge it. If you can't write the one-sentence version, stop there. You don't have an AI decision yet.

## Four questions that sort the decision

**Does an off-the-shelf product do this job today?** Look for a product with paying customers your size, instead of a demo or a roadmap slide.

**Can the data leave your building?** Client files, health records, financials and anything under a confidentiality agreement change the answer. Read the vendor's data terms before you let this one slide.

**How often does the task happen, and what does an hour of it cost?** A task that runs every day at a senior person's rate can justify real spending. A task that happens four times a year can't.

**Who owns the tool after launch?** Name the person who checks its output, updates it, and turns it off if it misbehaves. If you can't name one, skip the project for now.

## The decision table

| Your situation | Answer | Reason |
|---|---|---|
| A proven product does the job and the data can go to the vendor | **Buy** | You get support, updates and a monthly cost you can cancel |
| The data is confidential and every product sends it to a third party | **Build private** | The model runs on your hardware and the documents stay on your network |
| A product covers most of the job but needs your sensitive files | **Pilot first** | Test it on non-confidential material, then decide build or buy |
| The task is rare, or you can't name an owner | **Skip** | An unowned tool produces confident mistakes that no one reviews |

## Buying is the right default

Buy the product if a good one exists and your data can go to the vendor. You won't match a funded software company's support team or update schedule on your own, and you shouldn't try.

Read two things before you sign: where the vendor stores your files, and whether it trains models on them. If the contract won't tell you, treat that silence as a no.

## Build private when the documents can't leave

Some firms can't send their files anywhere. For them I build AI that runs on hardware they control. My own document AI system runs from a USB drive with no network connection. It reads PDFs, PowerPoint decks, spreadsheets and CSV files, answers questions with a citation to the source file, and runs on a machine with 4GB of RAM.

Private builds carry costs you need to see up front. Someone has to size the hardware and pick a model that fits it. On my own inference server, a Mac Mini with 24GB of memory, a 27-billion-parameter model with a 25,000-token context used 23GB of that 24GB. On my eight-test benchmark, a 9-billion-parameter model beat it and ran 3.2 times faster. Test candidate models on your own hardware and your own tasks before you pay for anything bigger.

## Skipping counts as a decision

Leave a task alone when it happens a handful of times a year, or when an hour of staff time costs less than the subscription. Write the decision down with the date, so the next rep who calls gets a quick answer and you can revisit it in a year.

## Bring me your AI decision

I'm taking on three founding clients at $6,000 a month instead of my standard $8,500, month to month, in exchange for a testimonial and permission to publish the results as a case study. If you're holding an AI decision right now, [book a free 30-minute call](https://cal.com/brianfranzen/first30min) and we'll run it through this table together. Full pricing is at [b4help.com](https://b4help.com).
