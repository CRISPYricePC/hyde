---
title: Writing a terrible program taught me a lot about C
---

People always tell me that the programs you write in your past will come back to haunt you; you'll look back and cry with amazement at your stupidity.

Year 11 me thought I could run from this truth, which is why I deleted all of my awful python projects, vouching to never develop a full application with a language that I wasn't 100% comfortable with. My strategy has failed me.
<!--more-->

Firstly, programming is an endless cycle of making mistakes and learning. If you think you finally understand a programming language, you don't. Something is always there that's gonna confuse the hell out of you. Something you thought you understood well will shock you with how much you don't understand. Saying you're 100% confident with a language is like saying you're 100% confident you're immortal.

Secondly, university happened. I'm now being thrown coursework for medium to large programming projects in languages I wouldn't even have ever wanted to touch. More specifically, the project I just submitted yesterday is the worst of these.

## I think I've learned more about C in the last two weeks than my whole first year of University

Everything that we had to do in this project, we covered in lectures, we covered in labs. I absorbed the information, stepped out of the lecture hall going "*Huh! I get pointers!*". I did not "*get*" pointers, my cockiness is exactly the thing that proved that I did not "*get*" pointers in the slightest. The project we were set that day proved this completely:

>  Write a management system for a library. Use the header file provided as a starting point
>
> Submit a report of how you developed it and what you did to improve over time

Immediately I was on the case, I knew the project would be large and consume a lot of my time so I started day-one. However, my onset was just as immediate as my stupidity.

"*I am a god, a king of pointers, I wield `malloc` and `free` with an iron fist and I never leak memory*", yes it's an exaggeration of what was going through my mind at this very moment, but looking back, that's what it felt like.

I began to write memory allocation statements wherever I felt like it, remembering, of course to write a free statement to complement. But it doesn't work like that; pointers are messy and you can never anticipate what's going to slip through the cracks of your absolutely dreadful program.

## The cracks were forming, but I didn't notice

I spent the first three weeks writing implementing the header file provided with a linked list system, only to realise that I needed 3 of these linked lists, and it was not generic. I made the same menu for all the modules, but rewrote it each time I needed it. My mind was turning to mush, and I didn't notice any of these huge flaws in my design.

The nail in the coffin was when I finally finished the first module, after nearly four weeks, with one week to go. I opened a memory checker and ran it through the program:

```log
4352 bytes in 124 blocks leaked
```

One week left...

The rest of that day was spent fixing the leaks that were there, but I had found nowhere near all of them. It was at this point that it dawned on me that this is what people meant when the programs of yesteryear come back to haunt you.

Pressure driven, coffee driven, I drove on.

## The heavens smiled upon us

On the day before the submission date, we received an extension of one week. That one week was what was going to save me. Line after line I wrote, leaving a gory carnage of segmentation faults and memory leaks in my wake, no part of my laptops screaming shell would be safe from my massacre. But the program was progressing.

From segmentation faults to double frees to memory corruption, I shook off the increasingly more concerning warnings and runtime errors, for I would fix them later with all the time I'll have spare. Spoilers: I had no time spare.

## The nail in the coffin

The night before the deadline, I finished my unit tests, they all passed! Time to patch it all together aaaaaand:

It doesn't work...

You can't get through more than 6 menus without the program crashing. I stood up, performed the quietest rage I could possibly do at midnight in a COVID-19 quarantine-packed house, zipped up the repository and submitted. The weights on my shoulder were lifted and I went to bed.

I'd completely forgotten that this project had to accompany a report on my development...

Enjoy your C-vomit, professor!

*PS. I got 70% somehow!*