---
published: false
---

## One year, 50,000 assemblies later: lessons learned

The first year of my PhD is over. I spent a good chunk of my time exploring de-novo transcriptome assembly. My exploration has encompassed all the commonly used tools that I'm aware of, dozens of plant species and types of input data, and at least 50,000 assemblies. This post is a summary of what I've learned, what I found was missing, and the tools I've developed to plug the gaps.

In particular I've spent a lot of time thinking about how to assess the quality of transcriptomes, and how to optimise assemblies as rapidly and effectively as possible.

I hope this document will serve as a community resource, and I very much welcome discussion and criticism.

### Contents

1. Workflow and pipelines
2. Pre-processing
 - trimming
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
5. Quality assessment
 - transcriptomes are not genomes
 - metrics
 - introducing Transrate
6. Optimisation
 - every species is different
 - subsets of reads proxy the full set
 - introducing BIOPSY and Assemblotron