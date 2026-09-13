---
layout: post
title: "AI for Law Firms Without the Privilege Problem"
date: 2026-11-16
description: "How a small law firm can use AI on client matters while keeping client information confidential, drawing on ABA Formal Opinion 512 and private deployment options."
image: "/images/23_ai_for_law_firms.png"
categories: [Private AI, Legal]
tags: [law firms, private AI, ABA Formal Opinion 512, confidentiality, fractional CTO]
---

Picture an associate at a small firm pasting a draft settlement agreement into a free chatbot to tighten the language. The output reads well. The associate didn't check the tool's data terms, and the partner has no idea the draft left the building.

Legal work involves a great deal of reading and drafting, the kind of work AI tools target. Your firm also carries confidentiality obligations that a retailer or a contractor doesn't. This post covers the technology side of using AI while keeping client information confidential.

**A note before you read further:** I'm a technology advisor, not a lawyer. Your state's rules of professional conduct and your ethics counsel govern what your firm may do. Treat this post as a technology checklist to bring to that conversation.

## The ABA's guidance from July 2024

On July 29, 2024, the American Bar Association's Standing Committee on Ethics and Professional Responsibility released Formal Opinion 512, its first formal opinion on lawyers' use of generative AI ([ABA](https://www.americanbar.org/news/abanews/aba-news-archives/2024/07/aba-issues-first-ethics-guidance-ai-tools/)). The ABA's announcement points to four Model Rules:

- **Rule 1.1, Competence.** Lawyers should understand "the benefits and risks associated" with the technologies they use to deliver legal services.
- **Rule 1.6, Confidentiality.** The ABA's announcement describes the duty to keep confidential "all information relating to the representation of a client, regardless of its source, unless the client gives informed consent."
- **Rule 1.4, Communications.** Lawyers must "reasonably consult" with clients about the means used to reach their objectives.
- **Rule 1.5, Fees.** Per the announcement, in most circumstances a lawyer can't charge a client for learning how to use an AI tool.

Rules 1.1 and 1.6 bear on your technology choices. You need to understand where a tool sends the text you type into it, and you need that answer before client information goes in.

## Where the exposure sits

Every AI tool runs a model somewhere. If the model runs on a vendor's servers, your prompt travels to those servers, and the vendor decides under its terms how long to keep it and what it may do with it. Those terms differ between vendors and between the free, business and enterprise plans of the same vendor.

The risk sits in two places: the terms your firm agreed to, and the tools individual staff adopted without asking anyone. You can fix the first with procurement. You fix the second with a policy and an inventory.

## Three tiers of deployment

**Consumer tools on personal accounts.** Staff sign up with a personal email and accept terms your firm hasn't reviewed. Keep client information out of this tier.

**Business or enterprise plans under a firm contract.** Your firm signs the agreement, and you can read the data retention and training terms, negotiate them, and hold the vendor to them. Your firm may be able to work here for some matters, once counsel has reviewed the terms.

**Private models on firm-controlled hardware.** The model runs on a machine your firm owns or controls, and the documents stay off third-party servers. This tier fits the most sensitive matters, and it asks the most of you on setup and maintenance.

## A private setup in practice

I built a document AI system to prove the third tier works on ordinary hardware. It runs from a USB drive with no network connection and indexes PDFs, PowerPoint decks, spreadsheets and CSV files. It answers questions with a citation to the source file, so a lawyer can check every answer against the document, and it makes no network requests. It runs on a machine with 4GB of RAM.

A small model on modest hardware answers slower than a cloud service and handles narrower questions. For reviewing a closed set of matter documents, that trade can make sense. For open-ended research, a contracted cloud tool may fit better. Match the tier to the matter.

## Steps for this quarter

1. **Inventory the tools in use.** Ask every lawyer and staff member which AI tools they've used on firm work in the last six months. Expect surprises and don't punish honest answers.
2. **Write the policy.** Name the approved tools, the tier each belongs to, and which categories of client information may go into each.
3. **Read the contracts.** For every business-tier tool, pull the data retention and model training clauses and send them to your ethics counsel.
4. **Talk to counsel about client communication.** Rule 1.4 raises questions about how and when to tell clients which tools touch their matters. Get your ethics counsel's view on engagement letter language.
5. **Pilot private AI on one closed matter.** Pick a matter with a fixed document set, run it through a private setup, and compare the time against your current process.

## Getting it set up

I help law firms build the technology side of this: tool inventories, deployment tiers, contract review for data terms, and private AI setups that keep documents in the office. If your firm wants AI and can't afford the exposure, [book a free 30-minute call](https://cal.com/brianfranzen/first30min). My pricing is published at [b4help.com](https://b4help.com).
