---
layout: post
title: "Tutorial: A quick look implementing Queues with Stacks"
---

I was recently given a question on an exam that proposed a way of implementing a queue. Let's first look at what a queue is:

Consider a list of items, let's say fruit. Because our collection is a list, we expect the items to be added in a specific order, usually this means that viewing the list shows the items in the order that we added them in. Stacks and Queues go an extra step, saying that there should also be a specific order in which the items are *removed*.

- A stack uses *First in, Last out* or *FILO* or *LIFO* as it's policy. You can think of this as putting fruit on top of a fruit bowl. The poor apple which was the first to enter is likely going to be the last to leave, and when it does it's probably headed straight to the bin. Items are added to a stack using `push` and removed using `pop`.
- A queue uses the lawful *First in, First out* or *FIFO* policy. In this case, you're an anarchist who makes sure they take the bottom apples out of the bowl first? I don't think this metaphor works. Items are added to the queue using `enqueue` and removed using `dequeue`.

Okay, now that we're caught up, the question:

> Write an implementation of a Queue data structure that uses two stacks, `s1` and `s2`, where `s1` is used to hold the items, while `s2` is used during the `enqueue` operation.

This is an interesting exercise that has a very simple solution. Every time we want to add an item to our "queue", we `pop` all the items from `s1` and `push` them to the auxiliary `s2`. Why do we do this? Now our `s2` contains all the items in `s1`, but in the *reverse order*. This means that the first item to be added to `s1` is now the last item to be added to `s2`, so we can perform `push` on `s2` to add the new item to our "queue". Now, we can `pop` and `push` back to `s1` again.

Here's some python code to demonstrate what's going on:

```python
class Queue:
    def enqueue(int item):
        """Adds an item to the queue"""
        pass

    def dequeue() -> int:
        """Removes an item from the queue"""
        pass
```

