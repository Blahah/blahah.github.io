---
layout: post
title: "The data structures challenge"
description: ""
date: 2013-08-18 12:00
author: Richard Smith
author-link: http://blahah.net/about.html
---
{% include JB/setup %}

<br />

To kick start this new blog, I'm setting myself a challenge: implement 42 data structures in 42 days.

## The reason

I'm nearing the end of the first year of my PhD. I started 10 months ago as a biologist with a bit of programming experience. A fair description of my current role in the lab is somewhere between a computational biologist and bioinformatician. I'm writing software every day to handle huge amounts of data in short turnaround times, and I have no formal CS training.

<!-- more -->

The real killer insights of CS are in data structures and algorithms. I've done project-specific implementations of various simple structures, and I know a bit in abstract about more complex structures like bloom filters from reading source code ([e.g. of khmer](https://github.com/ctb/khmer)). But I know my work would benefit greatly from a thorough grounding in data structures. I'm fed up with not knowing enough, so I'm fixing it. Abstract learning is not sufficient - I want to cement the knowledge by *doing*.

## The challenge

From now (Sunday 18th August 2013) until I complete the list below, I'm going to implement at least one data structure per day (on average). I'll start with basics and abstract structures, and move up to specific variants and finally tackle the complex stuff. I'm not aiming for algorithmic perfection: the implementations won't be optimal first time round. Once I've finished the list, I'll go back and try to improve the implementations.

## The details

Because I often don't have spare coding time on a given day, I might stack up my structures on one day (for example, I might do 6 structures on a Sunday to cover the next week). There are 42 structures in the list below, so assuming I don't add more as I go, I'll be finished **on or before September 29th 2013**.

My language of choice is Ruby. There are various reasons, but it boils down to the fact that Ruby is a beautiful, intuitive and expressive language and I can think faster in it than any of the others I know. A decent set of Ruby data structures would also be useful to me on a daily basis, and I haven't found an existine one. Maybe it can help others too - [I'm releasing it as a gem](https://rubygems.org/gems/data_structures). You can [follow developent on Github](https://github.com/Blahah/datastructures).


## The structures

Enough talk: here's the unordered list (cobbled together from Stack Overflow posts) with wiki links.

### Array-like structures

- [Queue](http://en.wikipedia.org/wiki/Queue_%28abstract_data_type%29)
- [Priority queue](http://en.wikipedia.org/wiki/Priority_queue)
- [Deque](http://en.wikipedia.org/wiki/Deque)
- [Double-ended priority queue](http://en.wikipedia.org/wiki/Double-ended_priority_queue)
- [Stack](http://en.wikipedia.org/wiki/Stack_(data_structure%29)
- [Linked list](http://en.wikipedia.org/wiki/Linked_list)
- [Work-stealing queue](http://supertech.csail.mit.edu/papers/steal.pdf) (note: PDF link, no wiki article)
- [Suffix array](http://en.wikipedia.org/wiki/Suffix_array‎)
- [Disjoint set](http://en.wikipedia.org/wiki/Disjoint-set_data_structure)
- [Sparse array](http://en.wikipedia.org/wiki/Sparse_array)
- [Sparse matrix](http://en.wikipedia.org/wiki/Sparse_matrix)

### Graphical structures

#### Basic

- [Graph](http://en.wikipedia.org/wiki/Graph_(abstract_data_type%29)
- [Directed graph](http://en.wikipedia.org/wiki/Directed_graph)
- [Directed acyclic graph](http://en.wikipedia.org/wiki/Directed_acyclic_graph)

#### Heaps

- [Heap](https://en.wikipedia.org/wiki/Heap_(data_structure%29)
- [Binary heap](http://en.wikipedia.org/wiki/Binary_heap)
- [Fibonacci heap](http://en.wikipedia.org/wiki/Fibonacci_heap)

#### Trees

- [Tree](http://en.wikipedia.org/wiki/Tree_(data_structure%29)
- [Trie (radix tree)](http://en.wikipedia.org/wiki/Trie)
- [Binary tree](http://en.wikipedia.org/wiki/Binary_tree)
- [Binary search tree](http://en.wikipedia.org/wiki/Binary_search_tree)
- [Weight balanced tree](http://en.wikipedia.org/wiki/Weight-balanced_tree)
- [Self-balancing binary search tree](http://en.wikipedia.org/wiki/Self-balancing_binary_search_tree)
- [B-tree](http://en.wikipedia.org/wiki/B-tree)
- [B+tree](http://en.wikipedia.org/wiki/B%2B_tree)
- [Rope](http://en.wikipedia.org/wiki/Rope_(data_structure%29)
- [Decision tree](http://en.wikipedia.org/wiki/Decision_tree)
- [Treap](http://en.wikipedia.org/wiki/Treap)
- [R-tree](http://en.wikipedia.org/wiki/R-tree)
- [Huffman tree](http://en.wikipedia.org/wiki/Huffman_coding)
- [Merkle tree](http://en.wikipedia.org/wiki/Merkle_tree)
- [Min-max heap](http://en.wikipedia.org/wiki/Min-max_heap)
- [Fenwick tree](http://en.wikipedia.org/wiki/Fenwick_tree)
- [Suffix tree](http://en.wikipedia.org/wiki/Suffix_tree)
- [Suffix trie](http://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/suffixtrees.pdf) (note: PDF link, no wiki article)
- [Splay tree](http://en.wikipedia.org/wiki/Splay_tree)
- [Ternary tree](http://en.wikipedia.org/wiki/Ternary_tree)

### Probabilistic and streaming structures

- [Bloom filter](http://en.wikipedia.org/wiki/Bloom_filter)
- [Quotient filter](http://en.wikipedia.org/wiki/Quotient_filter)
- [Skip list](http://en.wikipedia.org/wiki/Skip_list)
- [Counting bloom filter](http://en.wikipedia.org/wiki/Bloom_filter#Counting_filters)
- [Count-Min sketch](http://en.wikipedia.org/wiki/Count%E2%80%93min_sketch)


Whew! A pretty long list. But many of these build on one another, so that many will inherit from their parent structures. The challenge is less daunting than it might appear at first.

Of course, some of these structures might be prohibitively slow in pure Ruby. I'm thinking in particular of bloom-filters and count-min sketches. But I'm going to go ahread an implement them in Ruby so that I understand them. Then, if performance is weak, I can rewrite in C and use Ruby bindings.

I'm also interested in implementing [lock-free](http://en.wikipedia.org/wiki/Non-blocking_algorithm) versions of as many of the above as possible. I couldn't find a nice list of structures with lock-free implementations, so I'll expand this point as I learn more..

### The end

This is a living document - I will update with links to explanatory posts and code as I complete them. I will also structure and annotate the list as I learn more about the structures.

Have I missed an important structure? Is one of these redundant? Suggestions/corrections to this list are welcome.

See you on the other side!
