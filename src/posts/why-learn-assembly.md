---
layout: layouts/post.njk
title: Why Learn Assembly?
socialImage: ""
date: 2017-10-18T21:06:40.378Z
tags:
  - programming
---
Assembly language? Who the heck wants to code in assembly language??

I'll say this much: it's not for the faint of heart.

Some people have similar thoughts of futility regarding C but the truth is that it's still very important.

![C for Systems Programming](/images/rsz-c-systems-programming.png)

Assembly is very relevant in systems programming. It's as low level as a sane man can program. If you have ever programmed in machine code, you deserve a gold trophy! (I'm not even going to qualify that statement by saying the code should've been useful as long as you understood what you wrote.)

But you might wonder: why bother writing code in assembly if gcc can convert your higher level code to assembly on its own? Well, for me, it's not so important that one actually know how to write an entire meaningful program in assembly. Rather, the greater benefit is thinking like a systems programmer. Let me explain...

I'm sure all programmers realize that the way they think and approach problems is quite different from the way a non-programmer would. We often consider not only the correctness of the solution but also the algorithmic efficiency. As a systems programmer, these considerations of efficiency are broken down even deeper. Oftentimes, an optimal Big-O runtime is not good enough and we want to strive to reduce the number of instructions because we notice redundancies in the way gcc has translated our code. gcc doesn't know exactly what we are trying to accomplish, it is only making educated guesses. Even when we may not fully know what we're trying to do, our understanding still surpasses gcc's generic attempts at comprehending our intentions.

When programming in assembly, I think thrice about every float I use, I think twice about every mul instruction and I even reconsider the necessity of a mov operation. Static memory allocation is also more cumbersome. Using conditionals (if-statement conditions) can have serious performance implications. These are all things an assembly programmer is considering when writing optimal code. It may take longer to code but well-written code will definitely be faster and more succinct, meaning that maximal benefit can be taken from the onboard memory and computational power of small programmable devices.

I am by no means even a novice systems programmer but after taking/TA-ing a course in assembly I don't like how often people bash it for being a useless skill.

And, for the record, true programmers code low level.

![XKCD: Real Programmers](https://imgs.xkcd.com/comics/real_programmers.png)

*(Credit: xkcd)*