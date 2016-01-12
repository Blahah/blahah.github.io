---
layout: post
title: "Starting to sprint with slidewinder"
date: 2016-01-11 23:25
comments: true
published: true
author: Richard Smith-Unna
"author-link": "http://blahah.net/about.html"
---

{% include JB/setup %}

I've been fairly quiet since starting my Mozilla Science Fellowship in October last year. But behind the scenes, the other fellows and I have been furiously planning our projects.

My original plan was to spend my fellowship doing a single large project, creating an open science course at my university. But things have evolved in two main ways:

Firstly, after talking through ideas with the Mozilla Science Lab team, I've decided to focus on something that uses more of my particular skillset. **Software and resources that enable others to do open science will be my focus**.

Secondly, I've struck up a particularly strong collaboration with my fellow [Joey Lee](http://jk-lee.com/). We've spent many late nights agonising (via online chat) about how to most effectively use our fellowship time. We ultimately decided that **we work best by doing short, flexible projects** rather than large monolithic ones. And we found out that **we work particularly well together**. So, along with Joey, I'll be following a sprint model for the next phase of my fellowship (from now until the end of March).

<!-- more -->

### The sprint model

**We [Mozilla Science fellows](https://www.mozillascience.org/fellows) have been given an incredible opportunity**, and we're not taking it lightly. The support of MSL allows us to focus completely on whatever we want for 10 months. Incredible.

Two of the fellows, [Christie Bahlai](https://practicaldatamanagement.wordpress.com/) and [Jason Bobe](http://www.jasonbobe.net/projects.html), already have incredibly impressive long-running projects on the go (seriously, go check them out). But for Joey and I, we're relatively new to this (although [Joey's stuff is also mind-blowingly cool](http://jk-lee.com/projects/)). I personally don't yet know which of the many projects I'm involved in will be the most effective use of my time.

**I'm going to find out by doing sprints**. A sprint, in this context, means that for a set period of time (2 weeks by default) I'll work exclusively on one project. In that time I'll try to push the project as far as I can. Explore where it might go, whether a community could be built around it, and whether I'm really the best person to lead it.

A sprint project can be a new idea that will be realised for the first time, or it can take an existing project or idea and build on it, trying to achieve some goal. **What it absolutely must have is a clear set of goals** for the sprint time.

I mentioned that Joey and I are in a similar situation. More than that, we developed this sprint idea together, and we're **building collaboration into the system**. Joey and I [each came up with a list of sprint ideas](https://github.com/mozillascience/fellows-class-2015/blob/master/fellowship_sprints.md) (and [will come](https://github.com/Blahah/mozilla_science_fellowship/labels/micro-sprint) up [with more](https://github.com/joeyklee/mozilla_science_fellowship/issues)). We'll each work on our own ideas, but will always reserve **at least 20% of our time to collaborate** on our fellow's sprint. The 20% is a minimum because some of the ideas got us both excited, and we'll be working on those ones as full collaborations.

### My first sprint: slidewinder

**The uniting theme for my fellowship will be improving access to science**. That means making our products and resources easier to use and re-use, and making our communities more inclusive.

Public speaking is something I enjoy a lot, but creating slide decks is a nightmare. My frustration with this has built up over years, but in the final months of 2015 I was giving more and more talks, and finally I snapped. I set aside all my other work, sat down, and designed what I would really like slide creation to be like.

Consider the following scenarios that happen to me frequently when making a slide deck:

**I've written slides appropriate for this before**. I look around my filesystem and try to dig out the relevant decks, then open them and drag over the slides.

**I've seen a great slide in someone else's talk that would fit in perfectly here**. To use it, I have to track down their slide deck - possibly on slideshare - and download it. I have to fire up the right kind of presentation software and extract the slide, then insert it into my deck. Possibly I need to restyle it a lot - and more often then not I end up just replicating it from scratch. It should not be this hard.

**I want to use a figure from a paper in my talk**. Now I dig up the paper - perhaps online in which case I can download the figures (but watch the license!) - or perhaps in my reference manager. Then I need to cut out the bit I want and add it, and then add the citation. This is such a common occurence that I can't believe it's not built into the tools we use.

**I want to depict something that _someone_ must have diagrammed well before**. Now comes an interative process of google image search and asking people on Twitter. Usually it's from a paper, and then I'm back to the previous task.

**I'm sure someone has said what I want to say better than me**. Google-fu session ensues.

**I want to make it easy for others to reuse my content**. Mostly I put the deck up online somewhere, and I put the source on Github. But let's be honest, nothing about that makes it easy for others to use. Probably just me and a handful of other people can interact with that.

Perhaps these things don't sound like big frustrations - but to me they consume way too much time in the talk-writing process. I just want to get my ideas down, building on what I and others have done before. When something feels this painful to me, I start wondering why the tools don't make it easier. And in this case, I've come to the conclusion that it's just because nobody built the right tools.

### The slide is the thing

We're used to thinking about individual slides as merely parts of a deck - the deck is the thing we share with people. slidewinder flips that. The slide is the thing. It's a bit of text and media bundled together to communicate a message. That's the central dogma of slidewinder.

![slidewinder logo](https://raw.githubusercontent.com/slidewinder/slidewinder/master/assets/logo_wide_logo.png)

When you think about slides this way, things start to change. You collect slides, and store ways of arranging them in decks. You can share your slide collections with others, and we can collectively create community slide collections. Perhaps some examples will help show the value of this.

Most people include some basic bibliographic info in every talk - well, with slidewinder you have a bio slide. When you're making a new talk, you drop in the `bio` slide, and that's it. Perhaps you have a variety of different bio slides for different kinds of crowds. No problem - you just search 'bio' in slidewinder and choose the one you want.

In science we usually acknowledge funders in our talks. That's a slide - with slidewinder you'd start typing `fun`... in the search bar, and your funding acknowledgement slides would pop up.

None of that is revolutionary perhaps. Well, let's say I want to include a slide that has a diagram of a particular science software algorithm. With slidewinder, you'd check the 'use remote collections' box next to the search bar, and start typing out words that describe the image you want. slidewinder would query the Open Access literature to find figures matching your search terms, and present them to you in order of relevance. When you see the one you want, just drag it into your deck.

Any slide you bring in can be edited, you can create new slides, and you can apply or create styles. But it's the sharing and easy discovery of slides that has been missing until now.

With the slide as the thing we focus on, slide deck creation gets a lot more powerful.

### The history

When I had the idea last year, I hammered out some code the same night (our newborn son wasn't going to let me sleep anyway).

<blockquote class="twitter-tweet" data-partner="tweetdeck"><p lang="en" dir="ltr">Baby wouldn&#39;t let me sleep so I made a cmdline tool for rapid making &amp; remixing of markdown slide decks: slidewinder <a href="https://t.co/138TcfiBMg">https://t.co/138TcfiBMg</a></p>&mdash; ⓪ Rik Smith-Unna (@blahah404) <a href="https://twitter.com/blahah404/status/655269729834291202">October 17, 2015</a></blockquote>

Slidewinder is currently a command-line tool you can use to assemble slides written in markdown into a deck, which is then presented in the browser using Remark.js. It's written in Node.js, which is now my default choice for rapid app development.

My old long-time collaborator from [BioJulia](https://gitter.im/BioJulia/Bio.jl) [Ben Ward](https://github.com/ward9250) ([@Ward9250](https://twitter.com/Ward9250)) noticed the project and started using it. He gave [a talk about BioJulia at the BionductoR developer's meeting](http://biojulia.github.io/talks/EBDM2015/) that he created with slidewinder - this was a huge signal of confidence in the idea to me. He then quickly came up with ways to improve it and starting [submitting code](https://github.com/Blahah/slidewinder/pull/9). It became clear that Ben shared my vision and had the skills and energy to help make it happen, so we started a slidewinder [organisation](https://github.com/slidewinder/slidewinder).

### The plan

What we have now is a simple command-line tool, but our vision is much, much bigger. In two weeks, I hope to build a generalised framework for slide management and creation, and a simple GUI that can be deployed to the web or as a cross-platform desktop application. I also hope to launch that app at http://slidewinder.io, and to populate the slide collection there with every figure from every paper in the open access literature.

Joining me and Ben will be Joey (on 20% time as he's got his own awesome sprint idea), as well as various members of the incredible Mozilla Science Lab team. In particular my fellowship mentor [Abby Cabunoc Mayes](https://www.mozillascience.org/u/acabunoc) will be helping us keep on the right track, and I hope to get some design input from two of the best slide-deck creators I've ever witnessed, [Zannah Marsh](https://www.mozillascience.org/u/zee-moz) and [Aurelia Moser](https://www.mozillascience.org/u/auremoser) from the MSL team.

Of course, two weeks is not a long time. I don't expect to create a finished product - but I do hope to give a glimpse of what slidewinder might become.

I'll report back in two weeks with the slidewinder launch, and a writeup of the sprint.

~rik
