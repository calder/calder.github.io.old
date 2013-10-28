---
layout: post
title:  Beyond Von Neumann architectures
categories: programming current
---

# Problem

Moore's law is chugging along steadily:

[![Transistor count over time](/img/moores-law-2011.svg)](https://en.wikipedia.org/wiki/Moores_law)

but CPUs aren't getting any faster:

[![CPU clock speeds over time](/img/cpu-clock-speeds-2011.png)](http://csgillespie.wordpress.com/2011/01/25/cpu-and-gpu-trends-over-time/)

So how do we put all those extra transistors to use?

# Memory

Memory (both RAM and disk) is still getting cheaper:
[![Memory price over time](/img/mem-price-2013.jpg)](http://www.jcmit.com/mem2013.htm)

Using extra memory to save the CPU a little work suddenly makes sense in ways that would have seemed insanely wasteful 10 years ago. [Julia](http://julialang.org/) is a perfect example.

# Specialization

The last 10 years of transistor growth have only marginally affected CPU speeds. Specialized hardware has enormous potential to put those transistors to better use. GPUs, video decoders, voice and gesture recognizers are only the tip of the iceberg.

This transition can happen in two ways. The first - which we see today - puts the burden on programmers. Specialized hardware requires specialized programming in order to use it.

The second will require a paradigm shift in the way we program. It means transmitting higher level semantic information lower down the toolchain. It means finding a way to make the difference between hardware and software totally transparent. Virtual machines are a great start on the latter, but totally ignore the former.

Imagine calling map in your programming language of choice and having it automatically offloaded to a hardware vector processor, or computed on the CPU if there isn't one. Imagine smart-RAM that understands your object map and can garbage collect itself. Or a graph processor that can do pathfinding in logarithmic time (disclaimer: I don't actually know if this is possible). Or a DOM renderer that can handle millions of nodes.

This won't be an easy change to make. It requires radically rethinking current systems and thus discarding thousands of human lifetimes of work. But I would be willing to bet that such a refactoring is not only worth it, but inevitable. Because without it we're going to hit the cold hard wall of complexity pretty quickly.