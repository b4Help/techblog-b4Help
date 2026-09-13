---
layout: post
title: "Twelve Routers and No Map"
date: 2026-10-19
description: "In 2011 I rebuilt an office network made of ten to twelve chained consumer routers. The rebuild, what router sprawl costs a small office, and why AI tool sprawl follows the same pattern."
image: "/images/19_twelve_routers_and_no_map.png"
categories: [IT Infrastructure]
tags: [network infrastructure, small business IT, managed network, AI tools, IT strategy]
---

In 2011 I took over the network at an office running ten to twelve consumer routers. The collection mixed Netgear, D-Link and Linksys hardware, and the business had added the units one at a time as it grew.

With a dozen routers, each configured on its own, the office had no one place to see or manage its network. Each router kept its own settings, its own admin login and its own firmware, so understanding the network meant visiting each box.

## Every addition made sense

A chain like that grows out of reasonable decisions. A new room needs Wi-Fi, so someone buys a router. A new floor needs more ports, so someone adds another. Each purchase solves the problem in front of the person who makes it.

You feel the trouble in the combination. Manufacturers build consumer routers to run a household network on their own. Chain several together and each one can hand out its own addresses and keep its own firewall, leaving you with networks inside networks that no one designed as a whole.

Troubleshooting in a setup like that means working out which box sits between a computer and the internet, one device at a time. Security means changing settings on every router and hoping you caught them all.

## The rebuild

I replaced the chain with HP ProCurve managed switches and SonicWall firewalls.

Managed switches let you configure and monitor the network from a central point. The SonicWall firewalls gave the office one controlled boundary with the internet. With both in place, the firm had one network to watch and one place to set security policy, where before it had a dozen.

Firmware updates became one job on a short list of devices, where before each router had needed its own attention.

The hardware mattered less than the change in ownership. After the rebuild, one design and one set of rules governed the whole network, and one person could explain it end to end.

## Seven years later

In 2018 I built a network for a different client on Ubiquiti's UniFi line: a Dream Machine, three managed PoE switches and two business access points. The PoE switches powered the access points over their network cables, so the install needed no separate power at each access point. The Dream Machine handled routing and managed the rest from one interface.

The two builds used different vendors and hardware from different decades. Both followed one principle: a single design, managed from one place, with a named owner.

## Signs your network grew the same way

Walk your office with these questions in mind:

- **Count the Wi-Fi network names** people connect to inside one office. Several names for one space point to several routers doing the same job.
- **Look under desks and in closets** for routers, extenders and small switches that someone plugged in to fix a local problem.
- **Ask who holds the admin login** for each device. Any device where no one on staff knows the login is a device no one manages.

Any one of these on its own is common. Finding all three suggests your network came together one purchase at a time.

## The same pattern in your AI tools

I see the router chain again in how small firms adopt AI in 2026. One employee signs up for an AI assistant. A colleague picks a different one. A department buys a transcription service, and someone else connects an AI plugin to the shared drive.

Each choice solves the problem in front of the person who makes it, the same way each router did. The combined result is client data spread across tools no one approved as a set, each with its own settings and terms.

The fix follows the router rebuild:

- **Map what exists.** List every AI tool in use and the account behind it.
- **Pick an approved set** and retire the rest on a schedule.
- **Name one owner** for AI tools, the way the managed network had one.

## Draw your own map

If your firm's technology grew one reasonable purchase at a time, whether routers, software or AI tools, I can map it and design the version you'd build on purpose. Pricing is published at [b4help.com](https://b4help.com). [Book a free call](https://cal.com/brianfranzen/first30min) and bring your best guess at the list.
