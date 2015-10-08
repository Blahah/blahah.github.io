---
layout: post
title: "User friendly bioinformatics part 1: installation"
description: ""
date: 2015-06-09 10:39
author: Richard Smith-Unna
author-link: http://blahah.net/about.html
---
{% include JB/setup %}

This is the first in a three-part series about the journey I've had developing bioinformatics software, in particular transrate.

In the last 3 years as I have gone from a wet-lab biologist to a fledgling bioinformatician and now a tool developer. It was an intense learning process - one that is still going strong. I started in bioinformatics because our lab was generating a lot of data, and getting some insights from it, but it was clear there were many more insights still waiting to be got at. Learning bioinformatics has been deeply rewarding in many ways, but also deeply frustrating, and for a simple reason: bioinformatics almost completely lacks any concept of user experience design. What would, ideally have taken me a few months eventually became my whole PhD.

Bioinformatics has always been a grass-roots, get your hands dirty kind of field. We've had a trickle of software engineers and computer scientists who help drive standards forward at the leading edge, but the majority of the field is populated with people who have transitioned from other specialisms - biology, physics and maths in particular. In most cases people dabble because they need to, then get get focussed on a problem, and then the tool they have developed for internal, often one-time use is released as software to get an extra publication. Only in rare cases do people take tool development seriously as a research practise, and rarer still are those who do so with a sense of responsibility to the user.

## Who is the user?

A fresh-faced young bioinformatician sits down at her computer. She sees her reflection in the screen. Who is she looking at? In modern biology I think she is most likely to see:

- a biology PhD student who has to analyse some high-throughput data someone else generated
- a postdoc who is incredibly adept at molecular experiments, does sequencing, and is now trying to get up to speed on the analysis
- a research assistant who did a bioinformatics masters, typically with a few lectures on unix
- a programmer who has joined a biology lab - writes great code, not necessarily a unix ninja

Notice who she *isn't*:

- someone who has spent 15 years developing the linux kernel for multiple architectures, working with 12 programming languages on a weekly basis, and with 5 years experience of systems administration at a large genomics HPC facility

Almost every damn piece of bioinformatics out there is made for this last person. But you could fit the number of people who match that profile in an 8-bit integer.

What the most likely users have in common is this: they have a biological question and a dataset. They want to provide their question to a piece of software and get a quantitative result that contributes towards the answer.

This simple exercise of thinking about who the user is is called *user storifying*. It's a basic principle of user experience design, and taking a moment to do it can help focus and direct your development.

## What is reasonable?

What the user might reasonably expect to be able to do is:

1. do some research about the best tool to use
2. read the documentation for that tool
3. download it
4. run it
5. interpret the results with some guidance.

There is a fundamental fact at the core of bioinformatics: we are dealing with data from machines that are evolving astonishingly fast. High-throughput sequencing generates more data every year, with different properties, formats and applications. Our tools need to be developed and deployed rapidly. So while a user has reasonable expectations, there are reasonable limits on what can be expected of tool developers.

In an ideal world bioinformatics tools would meet the user on their own turf - the graphical user environment. But given the constraints listed above I think it is reasonable for bioinformatics researchers to be developing command-line tools. It frees developers from the considerable overhead of making GUIs, while requiring *in principle* only a relatively modest technical skillset on the part of users. Command-line tools have the additional benefit that they can be wrapped in GUIs at a later stage, if a technology becomes widely used.

What is not reasonable is to develop those command-line tools with no regard for users. In this short series of posts I will address three major pain-points I have experienced in bioinformatics. For each one I'll outline the problem with examples, then highlight some examples of good practice and/or good effort, followed by an explanation of what we've tried to do to address it in our own projects. Those pain-points are:

- installation
- the user interface
- documentation

I'm not saying at all that we have solved all the problems. We've thought about them a lot, and we've tried - so hard it has been genuinely painful - but they are too hard to be solved in . What I hope to achieve here is to make developers aware of the struggle their users have to go through, and encourage them to think about the simple principles of user experience design when making their tools. It needn't take much longer and it doesn't have to cost more.
