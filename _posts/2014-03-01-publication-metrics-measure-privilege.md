---
layout: post
title: "How can we measure quality, not privelege?"
description: ""
date: 2014-03-01 14:54
author: Richard Smith
author-link: http://blahah.net/about.html
---
{% include JB/setup %}

Scientists are evaluated based on publication citations and impact factor. We know this is a bad idea. People raised the issue [at least 15 years ago](http://www.bmj.com/content/314/7079/497.1), and [many times since then](https://www.zotero.org/groups/impact_factor_problems/items). But [nothing has changed](http://datapub.cdlib.org/2013/05/22/impact-factors/). As a young scientist collaborating on a variety of projects, I've got a bunch of papers in preparation with colleagues. This has made me aware of the poisonous effect the metrics situation has on science.

<!-- more -->

My older or more experienced collaborators need to publish in high-impact journals. I hear this every day. If it's not a Nature paper, it better be Science. Any 'lower' than that and we've failed, it's not even worth writing up. [REF assessments](http://www.ref.ac.uk/) are coming up and they have a secret list of good journals\*. We need papers in good journals or we've got no chance or progressing in our careers. Notice that we don't need *good papers*, we need them in *good journals*. We have to show **impact**.

_\* [Michelle Brook](http://twitter.com/MLBrook), who knows about these things, assures me this isn't true._

Glamour journals like Nature and Science have some of the most overblown papers I've seen anywhere. Unsexy journals like PLOS have interesting and thoughtful papers whose claims match the results. [ArXiv](http://arxiv.org) (not a peer reviewed journal) even more so. This is reflected in the relative retraction rates - [Impact Factor correlates with retractions](http://iai.asm.org/content/79/10/3855.full).

Being in Cambridge, and being a white male, I'm always trying to be aware of my privilege. This situation is a grotesque example of it. Researchers here are successful when measured by how often they publish in glamour journals. That is at least in part because *everyone* here submits every paper to them. Written a paper? Send it to Nature first. If it gets rejected, climb down the prestige ladder (Science > Cell > Current Biology) until it gets accepted. 

My previous university was the University of the West of England. Nobody considers this a top-tier university. Most researchers there would never even think of sending their work to Nature. If you're not submitting to Nature, you're not going to be in Nature. A vicious cycle.

We are gaming the metrics system, whether we're conscious of it or not. That's just how metrics work - you measure people on something and they will optimise for it. This is famously a problem in software development. We can assess programmers by the number of lines of code they produce. More is better. But of course this incentivises less concise code.

> "Measuring software productivity by lines of code is like measuring progress on an airplane by how much it weighs."
> _- Bill Gates_

Cambridge researchers tend to cite other people who have passed through other privileged institutions\*. Maybe this is deliberate, but maybe it's because they're just living in a bubble. It's a bunch of rich white men circle-citing one another. This citation club is a system for concentrating and maintaining privilege. So when we measure scientists on citations and impact, we're just measuring their privilege.

_\*this is anecdotal_

This is a recognised problem. People are making an effort to break away from these crappy measures of science output to ones less tied to conventional power. The [altmetrics](http://altmetrics.org/manifesto) movement has risen out of this. [AltMetric](http://altmetric.com) and [ImpactStory](http://impactstory.org) are examples, measuring 'impact' across social media and the web.

These sites do something useful - measure community engagement. If we think science is important, then engaging the scientific community and the public is also important. But is our ability to do this a measure of quality science? In other words, should be be evaluating scientists based on these metrics? On their ability to self-promote? I think not.

People who exercise influence in journal publishing are more likely to do well on traditional metrics. People who exercise influence in new media will be successful when measured by altmetrics.

A recent [AltMetric blog post about gaming altmetrics](http://www.altmetric.com/blog/gaming-altmetrics/) lists the ways people might try to get a higher AltMetrics score:

> 1. Alice has a new paper out. She tweets about it. HootSuite automatically posts all of her tweets to Facebook and Google+.
> 2. Alice has a new paper out. She writes about it on her lab’s blog and sends an email highlighting it to a colleague who reviews for Faculty of 1000.
> 3. Alice has a new paper out. She asks her colleagues to share it via social media if they think it’d be useful to others.
> 4. Alice has a new paper out. She asks those grad students of hers who blog to write about it.
> 5. Alice has a new paper out. She believes that it contains important information for diabetes patients and so pays for an in-stream advert on Twitter.
> 6. Alice has a new paper out. She believes that it contains important information for diabetes patients and so signs up to a ’100 retweets for $$$’ service.

They consider all of these acceptable except number 6.

I don't. Why should financial privilege be treated differently from the social privilege of a researcher who asks a colleague to review for F1000? Or asks a friend with a load of twitter followers to retweet? I think I would only feel comfortable doing #1, and might force myself to do #2. It's OK if people do them all, just don't reward them for it with Internet Points. And don't then use those points to conduct professional assessments of anything except what they actually measure.

Privilege in general is a problem. Metrics that don't directly measure the quality of the work are perpetuating privilege. I'm not at all convinced that currently popular altmetrics will help solve this.

They should help with other problems. For example, progress should speed up when we break free from the slow traditional review cycle.

Perhaps most importantly, altmetrics diffuse privilege; different people come to hold it. The divisions of privilege might cease to be drawn along gender, race and wealth lines. This is a very good thing. If privilege is something people can earn rather than being born with it, that's a big chunk of the problem dealt with.

But I'm talking about how we measure the quality of scientists and their outputs. How we make hiring decisions and decide what to read and cite. And for this purpose, 'impact' is a bad fit.

What we need is something that meets these conditions:

- focussed on quality
- as objective as possible
- difficult or impossible to game
- enables scientists and hiring committees to judge the work without having to read every single paper

Here's one idea: [automated sentiment analysis](http://en.wikipedia.org/wiki/Sentiment_analysis) across the post-publication review ecosystem. A set of metrics for every publication that measures *how experts feel about it*. Not just the experts we invite to the party, like at [F1000 Prime](http://f1000.com/prime). In the open, across all the places where experts talk about science. Surely that's a better measure of quality than anything we're doing now?

The basis for this is already in place. [PubPeer](https://pubpeer.com/) and [PubMed Commons](http://www.ncbi.nlm.nih.gov/pubmedcommons/) are crowd-sourcing expert evaluations of science. PubPeer is excellent because they verify the identity of commenters, but keep the comments anonymous. This means young researchers like me can leave honest comments with no fear of career reprisals. PubMed Commons takes the alternative route of signed reviews. This is also valuable for preventing unabated negativity. Once can imagine many other sites, each different, but each useful in its own way. We could assess sentiment across all these post-publication peer-review sites. That might be close to an objective measure of quality.

This idea has flaws, sure, but I think it's heading in the right direction, because it's *really* hard to game it. You can't control what other people say. Maybe you could try to convince all your colleagues to write glowing reviews. But we could tackle this, for example by giving weightings to reviewers according to their distance from the author in the [collaboration graph](http://en.wikipedia.org/wiki/Collaboration_graph). And I find it hard to imagine anyone commanding an army of commenters across dozens of sites.

In summary: Privilege is bad, quality is good. Self-promotion not the same as quality. How can we measure quality? Maybe with algorithms that collect expert opinion.

I'd love to hear what you think in the comments below, or on [Twitter](http://twitter.com/blahah404).
