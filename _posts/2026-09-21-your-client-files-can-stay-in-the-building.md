---
layout: post
title: "Your Client Files Can Stay in the Building"
date: 2026-09-21
description: "Private AI runs on hardware your firm controls, so confidential documents stay off third-party servers. The case for it, the hardware it needs, and where hosted AI still wins."
image: "/images/15_your_client_files_can_stay_in_the_building.png"
categories: [Private AI]
tags: [private AI, on-premise AI, local LLM, data privacy, professional services]
---

A law practice, an accounting firm or a medical office holds documents that clients handed over on trust. Your clients gave you tax returns, case files and patient records with an expectation about who would read them. The moment someone at your firm pastes one of those files into a public AI chatbot, the provider stores a copy on servers you don't own, under terms you didn't write.

My position is that firms like these should run their document AI on hardware they control. You can do that today on a modest machine, and I have built a system that does it.

## A copy leaves with every paste

A hosted AI service processes your text on the provider's servers. The provider's current terms decide how long it keeps that text and whether its models learn from it, and a personal account and a business plan can carry different rules.

Some providers let you switch training off. OpenAI's help center explains that when you turn off the "Improve the model for everyone" setting, your conversations stay out of model training and still appear in your chat history ([OpenAI Data Controls FAQ](https://help.openai.com/en/articles/7730893-data-controls-faq)). That setting helps. For a firm with confidentiality duties, a document sitting in someone else's account history, trained on or not, still sits with a third party.

## The first job needs a small model

Firms reach for AI to do one thing first: ask questions of their own documents. You want the indemnity clause in a contract, or the depreciation figure from last year's return, without reading forty pages to find it.

That task doesn't call for the largest model on the market. It calls for a model that reads the documents you give it and answers from them, with a pointer to where it found the answer.

I built PaperTrail for that job. It runs offline from a USB drive, indexes PDFs, PowerPoint decks, spreadsheets and CSV exports, and puts the source file next to each answer. It makes no network calls. The language model inside it, Qwen 2.5 at 1.5 billion parameters, runs on a computer with 4GB of RAM, though you wait longer for answers on hardware that small.

The citations do more for a firm than extra model size would. A partner who can click through to the source paragraph can confirm an answer in seconds.

## Bigger models eat memory

I test models on a Mac Mini with 24GB of memory before I recommend them to anyone. A 27-billion-parameter model working with a 25,000-token context used 23GB of that 24GB. The model weights account for part of that number. The working memory for a long document stacks on top of the weights, and on that machine it left 1GB free.

A 9-billion-parameter model did better on the same hardware. It passed all eight tests in my benchmark where the 27B passed six, and it ran 3.2 times faster.

For budgeting, those results mean a thirty-person firm can run private AI for document work without a data center. You need a model sized to the job and a machine sized to the model.

## Where hosted AI still wins

Smaller local models trail the largest hosted models on open-ended reasoning and long, original writing. You install updates yourself, and someone at your firm, or someone you hire, has to keep the machine running and backed up.

Draw a line between the two kinds of work and write it down. Confidential documents go to private AI. Work that contains no client data, such as a first draft of a marketing email or an outline for a staff presentation, can go to a hosted tool under an approved business account.

Staff follow a rule they can remember. "Client names mean private AI" fits on a sticky note.

## What it takes to start

You need two decisions before you need hardware. Pick the documents you want to question first, because that choice sets the model size and the machine. Then name the person who owns the system, from updates to backups of its index.

With those settled, the rest is one capable computer and careful testing against your own files.

If your firm wants AI working on client documents that can't leave the office, I scope and build private setups on hardware you own. My rates are published at [b4help.com](https://b4help.com), and you can [book 30 minutes](https://cal.com/brianfranzen/first30min) to tell me which files you want to question first.
