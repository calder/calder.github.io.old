---
layout:     post
title:      Onion pattern
categories: programming thought
---

I've been thinking a lot about processing encapsulated messages and [Onion routing](https://en.wikipedia.org/wiki/Onion_routing) recently. Here's a short digression on Barack Obama and elf tears.

Let's say you want to send President Obama a really important letter. This letter says "THE EARTH IS GOING TO ASPLODE UNLESS YOU XYZ". He's a busy guy though, so you can't just get a letter to him. Instead you put the letter inside another letter to an aid. Except even the aid's too busy. Maybe you find the aid's parent or friend or spouse and put THAT letter in ANOTHER letter.

In each letter, you have to include 1) enough information to convince the recipient to pass on the payload letter and 2) the payload letter itself. Each recipient then passes on to the next person 1) the payload letter and 2) some context (the fact that it's now coming from a trusted source rather than some rando).

We see this Process-AddContext-PassOn pattern in real world secretaries, network firewalls, and libraries like [D3](http://d3js.org/). It's like a bunch of elves peeling an onion layer by layer, except each elf peels only one layer and then passes on a shrinking onion and a growing vial of elf-tears (the result of processing the removed layers).

```
def secretaryHandleMessage (context, message)
  message = decodeMessage(message)
  context[something] = message.something
  presidentHandleMessage(context, message)
end
```