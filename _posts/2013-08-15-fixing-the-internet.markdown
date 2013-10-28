---
layout: post
title:  Fixing the internet
categories: programming current
---

# From addresses to identifiers

TCP/IP was designed a long time ago - a time before laptops, let alone ubiqitous mobile devices. In the 1983 it was made perfect sense for IP addresses to have a *geography* like their physical counterparts. Back then computers never went anywhere. And whether you're sending a letter or a data packet, you need somewhere to send it to.

This approach makes three assumptions:

1. A recipient will maintain a static address.
1. A recipient will be online at all times.

In 2013, neither of these assumptions is true of the majority of the worlds' [10 billion](http://techcrunch.com/2013/05/09/internet-of-everything/) internet connected devices. This means that primitives like push notifications and email need to be handled - with great added complexity - by a third party, as a layer built *on top of* rather than *into* the network.

A system based on unique identifiers rather than addresses offers several advantages:

1. **Dynamic** - Routes are discovered rather than hardcoded.
1. **Asynchronous** - Messages can be stored until a route is found.

Viva la identificación!

# Eliminating trust

...