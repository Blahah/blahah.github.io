---
published: false
---

## One year, 50,000 assemblies later: lessons learned

The first year of my PhD is over. I spent a good chunk of my time exploring de-novo transcriptome assembly. My exploration has encompassed all the commonly used tools that I'm aware of, dozens of plant species and types of input data, and at least 50,000 assemblies. This post is a summary of what I've learned, what I found missing, and the tools I've developed to plug the gaps.

In particular I've spent a lot of time thinking about how to assess the quality of transcriptomes, and how to optimise assemblies as rapidly and effectively as possible.

I hope this document will serve as a community resource, and I very much welcome discussion and criticism.

### Contents

1. Workflow and pipelines
2. Pre-processing
 - trimming
 - filtering
 - error correction
 - coverage normalisation
3. Assembly
 - approaches
 - tools
4. Post-processing
 - clustering
 - reassembly
 - scaffolding
 - annotation
 - cycling
 - chimeras
 - filtering
5. Quality assessment
 - transcriptomes are not genomes
 - metrics
 - introducing Transrate
6. Optimisation
 - every species is different and needs re-optimisation
 - subsets of reads proxy the full set
 - introducing BIOPSY and Assemblotron
 
 ## 1. Workflow and pipelines
 
 **First up: transcriptome assembly is a complex beast.**
 
 There are a lot of steps that need to be completed to get a high-quality assembly. For each step there are many competing software applications, and each application has a large array of parameters that often need to be optimised to the task. The best program to use at each step, and the best settings to use for each program, vary widely depending on the species you're sequencing and what you want to do with the transcriptome. Put that all together, and there are hundreds of millions of possible assembly protocols.
 
 Despite this quagmire, we can carve out some rational approaches to assembly. The key things are:

 1. understand the purpose and implications of each step in the process
 2. carefully choose how to measure assembly quality
 3. automate your experiment with a self-optimising pipeline

 In the next few sections I'll help with points 1 and 2. I'm still working on point 3, but what I've got so far is quite useful, so I'll discuss that at the end.
 
 ## 2. Pre-processing
 
 Raw reads from a sequencing machine are messy data. As the old IT adage - Garbage In Garbage Out - suggests, they need cleaning up before you can put them through the assembly process. 
 
 ### Trimming
 
 adapters
 quality
 
 figure: before and after trimming, time and quality
 
 ### Filtering
 
 contamination (species/genus)
 rRNA
 
 figure: before and after filtering, time and quality
 
 ### Error correction
 
 ALLPATHS-LG errorCorrectReads.pl
 SEECER
 SoapDenovo Correction Tool
 
 figure: rice oases allpaths vs seecer, time and quality
 
 ### Coverage normalization
 
 khmer normalize-by-median, filter-abund
 
 figure: with/without khmer, time, quality metrics
 
 ## 3. Assembly
 
 ### Approaches
 
 overlap layout consensus
 de-brujn
 string graph
 rectangle graph
 
 ### Tools
 
 Velvet-Oases
 SOAPDenovo-Trans
 TransAbyss
 Trinity
 SGA
 ReadJoiner
 SPADES
 
 ## 4. Post-processing
 
### Clustering

CD-HIT-EST
UCLUST

### Scaffolding

SSPACE
GapFiller
SGA
GapCloser for SOAPDenovo
Easy scripts

### Reassembly

cap3
ReadJoiner

### Annotation

BLAST/USEARCH
PFAM
reciprocal best BLAST
conditional BLAST

### Cycling

### Chimeras

blastx/usearch
read evidence

### Filtering

Support Vector Machines
Random Forests