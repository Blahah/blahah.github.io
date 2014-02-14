---
layout: post
title: Knowledge sets us free. Let's return the favour.
date: "2014-02-11 17:15"
comments: true
tags: science, publishing, openknowledge, freedom
published: true
author: Richard Smith
"author-link": "http://blahah.net/about.html"
---

Last night at [Open Research Cambridge](https://twitter.com/OpenResCam), [Jelena Aleksic](https://twitter.com/firegenome) gave a great talk about Open Access. In her closing comments, she floated the idea of an iTunes for scientific papers. Imagine being able to get any scientific paper for 79p. That's a reasonable price to cover costs of creating, archiving and distributing knowledge (given the research is already funded). Most people can afford it.

Current prices - $32 for one-off access to a Nature paper - are disgusting. Scientists created that knowledge, probably with public funding, then a team of other scientists peer reviewed it without getting paid, and Nature wants to make $32 from imprisoning it on their website? Fuck you, Nature.

<!-- more -->

### Music shows us how to set knowledge free

If we can possibly bring about a situation where knowledge comes at cost price (~79p), or better - free, at the point of consumption, it's our moral imperative to do so. To do that we have to destroy traditional publishing. No small task. Be we can take lessons from how the music industry was transformed.

Ubiquitous music piracy broke the strangehold traditional record companies had over listening to music. In the late 1990s CDs were £10-20. If you wanted to hear a particular song you had to buy a load of other songs at the same time and wait for them to be delivered to your house on a plastic disk. Then software made it trivially easy to pirate music, and in the last ten years record companies have been forced to change their business models to match the needs of their consumers. Now we can buy any song for pennies, and if someone can't afford it, it's easy to get it free.

**When it becomes trivial to pirate scientific papers whilst being very difficult to trace the source of piracy, and at the same time it becomes very easy to search and acquire pirated papers, the tyranny of publishers will be over.**

### A vision of the future

Let's imagine what that utopian world would look like by examining a few scenarios...

**1. A student/researcher has a library of hundreds or thousands of PDFs and associated metadata in their reference manager. They wish that knowledge was free.**

They fire up the Liberator software and hit a button. Their reference manager database is anonymised and liberated into an online, distributed repository.

**2. A student/researcher is browsing a journal's website.**

They are running the Liberator browser plugin that grabs every paper linked from every page they visit and anonymously sends it to the open respository network.

**3. Anyone wants to read a paper.**

They go to one of dozens of websites that let you search the distributed network of papers that have been liberated. They can download the paper and the data, and link out to open peer reviews from a variety of sites to enable them to judge the quality of the research for themselves.

**4. A student/researcher wants to liberate their entire subject.**

The Liberator connects to the distributed network and gets the list of papers already liberated - the "free list". When the user connects to the internet at their library, the Liberator compares the free list to what's available for access via the library. It starts anonymously crawling the publishers' sites and liberating papers that aren't free yet.

**5. A citizen wants to contribute to freeing all knowledge**

They visit a University library that has free public internet access, and deposit a tiny box in a discreet place. The box contains a raspberry pi with a USB wi-fi plug. The raspberry pi is running the Liberator, and starts crawling and setting papers free.

Perhaps they don't live near a University library. They visit anywhere with public internet and deposit their raspberry pi. It connects to a decentralised database of hacked or donated student library logins and begins crawling, liberating.

Perhaps there's no public wi-fi near them. They run the Liberator in TOR mode, and it anonymously crawls from the safety of their home using the login database to gain access.

**6. Someone (most likely, some consortium of publishers) attacks the network. They use court orders to take search sites offline and have servers shut down.**

Within seconds the network has recovered - mirror sites are pre-arranged to launch when others go down. All the data is held distributed around the world and cannot be destroyed without destroying the world's computers.

### The future is now

Sounds rosy, huh? Nobody gets hurt, and the whole of human knowledge becomes free. Publishers can't stop it: their customers are the Universities. They can't cut them off without cutting off their own income stream, and the Universities have already paid for all these papers. Millions of people running the Liberator are righteous leeches. They bleed the publishers to death. This allows us to rebuild knowledge archival and distribution for the modern era using open processes.

The cool thing is, this is all technically possible to achieve using tools that already exist, or that could be rapidly developed. I propose the following set of software to make this happen:

1. The Liberator: A web crawler that scrapes publishers websites and submits papers along with all their supplementary files and metadata to the Liberator network. The scraping uses [Zotero's community-maintained translators](https://github.com/zotero/translators) which already cover all the major publishers and many minor ones. It doesn't duplicate effort - it checks whether a paper is already free before liberating it. It can securely update over-the-air to add workarounds when publishers start trying to block the crawler. It can also find databases from all commonly used reference managers and anonymise and liberate their contents.
2. A torrent tracker with features that allow effective search and display of scientific papers. It produces RSS feeds that contain random subsets of the new papers in the network, so that new papers are evenly spread out around all seeders without anyone having to host all papers. These are minor modifications to existing open source torrent trackers, like [Gazelle](https://github.com/WhatCD/Gazelle).
3. Browser plugins that run Liberator whenever an academic publisher's website is visited. This is a trivial extension to the [Zotero connector plugins](https://www.zotero.org/download/).

**If you want to help make this happen, [go here and start talking](http://okfnpad.org/p/liberator) (anonymously, if you like).
**
