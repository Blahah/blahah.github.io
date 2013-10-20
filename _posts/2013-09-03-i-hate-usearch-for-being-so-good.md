---
layout: post
title: "I hate usearch for being so good"
date: 2013-09-03 18:15
comments: true
categories: bioinformatics, alignment
published: true
author: Richard Smith
"author-link": "http://blahah.net/about.html"
---

Aligning biological sequences to other biological sequences is the bread and butter of bioinformatics.

By far the most popular software for this purpose is [BLAST](http://en.wikipedia.org/wiki/BLAST), the Basic Local Alignment Search Tool. BLAST was [published in 1990](http://www.blastalgorithm.com/), and at the time its heuristic algorithm was a huge advance (in computational speed) over the Smith-Waterman algorithm. People have since used it for all manner of sequence alignment tasks.

More recently, alternative aligners have risen to prominence in some specific alignment cases. For example, for aligning short next-generation sequencing reads to a set of longer sequences, bowtie, bwa, SOAP, and friends are all orders of magnitude faster than BLAST, and this is recognised by their usage.

<!-- more -->

But in the case of plain old alignment of one or more nucleotide or amino acid sequences against a database of one or more nucleotide or amino acid sequences, BLAST, and to a lesser extent its cousin BLAT, stil dominate. The problem is these programs are SLOW. Really, really slow. And the rate of sequence production is now really, really fast. BLAST can't keep up.

In fact, if it wasn't for [USEARCH](http://drive5.com/usearch/), a new aligner that outpaces BLAST by several orders of magnitude on the mundane alignment tasks it's so famous for, most of the work I've done in the first year of my PhD would not have been possible. Some days I'm aligning several thousand assembled contigs to a reference genome, and repeating the process several thousand times over. With USEARCH that takes hours. With BLAST it takes **weeks or months**.

![Alt text](http://drive5.com/usearch/perf/hist1.gif "USEARCH vs BLAST and MEGABLAST nucleotide alignment speed and sensitvity on the RFAM test set.")

[Benchmarks show](http://drive5.com/usearch/perf/) that for nucleotide alignments, USEARCH processes ~300 alignments for every one that BLAST can manage, with no loss in sensitivity. This matches my experience, and in some cases I would say I've had significantly greater speed improvements than this. I'll record some benchmarks of my own next time I can bring myself to fire up BLAST again.

The problem with USEARCH, though, is its license. Only the 32bit version is free, meaning a hard 4GB memory limit. But even worse than that, it's closed source and the method is essentially unpublished ([there's a paper](http://bioinformatics.oxfordjournals.org/content/26/19/2460.full), but the details are scant - certainly missing information that would be required to recreate the software from scratch). I can run my alignments with USEARCH until the cows come home, and I can verify the results by comparison with BLAST results. But for every result I don't verify, I can never be sure it's not done something unexpected. I can't check the source code or the mathematical working of the algorithm, so ultimately I don't trust it.

To my knowledge there is nothing that comes close to the speed of USEARCH. The world needs an *open source* aligner with USEARCH's speed and sensitivity.

For now, I'm using USEARCH, but I feel like I'm violating myself by doing so. I hate you USEARCH, for being so damn good and not telling us how.