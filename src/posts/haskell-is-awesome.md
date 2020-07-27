---
layout: layouts/post.njk
title: Haskell is Awesome!
date: 2020-07-27T23:31:28.642Z
tags:
  - school
  - haskell
  - functional-programming
  - compilers
---
I learned Haskell this semester. Haskell is a purely functional language. It offers programmers a different paradigm or approach to programming. It's a different perspective about what code should look like.

### Declarative Programming

Functional languages are a subset of declarative languages. These contrast with imperative languages. The idea behind imperative is to dictate to a computer how to perform the tasks that you want completed. In the declarative mindset, simply ask for the result that you want without explaining precisely how to achieve it.

Thinking of declarative languages in this way may seem odd to those who have only ever interacted with imperative languages. "How will the processor know what to do if I don't tell it explicitly??" is a common sentiment. However, this assumes that when we give instructions to the computer in an imperative syntax, it actually follows our instructions. This understanding may be mistaken.

### What Compilers Really Care About

Take for example this C code (C is an imperative language): a basic for loop that computes the sum of numbers from 1 to N

```c
int sumN(int N) {
    int result = 0;
    for( int i=0; i<N; i++ ) {
        result += i;
    }
    return result;
}
```

With some basic knowledge of combinatorics, this code with O(N) runtime can be transformed to get O(1) runtime. [The sum of the first N natural numbers is n(n+1)/2](https://www.wolframalpha.com/input/?i=sum%20from%201%20to%20n).

A smart programmer may simply replace this code with something that produces the equivalent output but performs much faster. Compilers will often do the same.

[Assembly code for above C code with level 1 optimization, compiled with Clang](https://godbolt.org/z/fGcjhb).

Compilers are not mere translators of code. They also optimize for speed and memory consumption. The basic promise of a compiler is that the compiled code will produce the same result as the original high-level code.

### Back to Declarative Programming

So the real power of declarative programming is not having to write out precise instructions for the processor to follow that the compiler may simply throw out the window. Compiler designers are very smart and their compilers are consequently also very smart. The idea is to simply ask for what you need and let the compiler write the actual code, which will likely be more efficient than the code you may write otherwise. It will also likely take into consideration the various features of your specific processor and optimize the code to make use of that (e.g. using [SIMD instructions](https://en.wikipedia.org/wiki/SIMD) where possible).

In the declarative style, one can simply *declare* the desired result and let the compiler take over from there. It is really a shift in responsibility from the programmer to the compiler.

After some experience with it, Haskell code looks quite elegant and succinct due to this paradigm shift.

### Bit More About Functional Programming and Haskell

Functional programming is declarative and organizes code into functions.

The key features that distinguish functional from imperative:

* no state/variables
* only [pure functions](https://en.wikipedia.org/wiki/Pure_function) allowed (there are a few small exceptions to this rule, but we'll overlook those for now)

Haskell aims to be purely functional so it adheres to these principles as much as possible.

These may seem like drawbacks and not really "features", but it is that restriction that allows working in the new paradigm.

### Why Don't People Use Functional Languages More?

This is a question I asked my professor after I began to appreciate the beauty of functional programming. It seemed strange that functional languages aren't as popular as object-oriented languages despite their benefits. The main reasons for this is that functional programming can be annoying at times (e.g. no function side effects make simple, common tasks cumbersome; lack of state makes it difficult to manage data critical to many applications).

Nonetheless, the reality is that we do use functional programming quite often, even if the language isn't strictly functional like Haskell. Why limit yourself when you can have the best of both worlds? Many functional programming features have debuted in object-oriented languages. Pythonic code, for example, is very functional in style -- with the additional benefits of maintaining states. The states lead to other problems however, such as not being able to write multithreaded code that can execute in parallel because of the interpreters GIL. Other languages, and even other Python runtimes, have tackled that issue in other ways.

The bottom line is that functional programming is awesome, but you don't have to give up variables to get many of its perks.