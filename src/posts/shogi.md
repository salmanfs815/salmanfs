---
layout: layouts/post.njk
title: Shogi
metaTitle: Shogi
metaDesc: Led team of 5 to develop an interactive desktop application to play
  single or multi-player Shogi, a Japanese chess variant, with various game
  modes and difficulty levels
date: 2017-01-01T03:20:50.459Z
tags:
  - projects
  - julia
  - ai
  - chess
  - ""
---
I was the team leader for a term project in a software engineering course. Our team of 5 developers designed, developed and tested a program to play Shogi, a Japanese variant of chess. We used Julia for programming , GTK+ library for the graphical user interface, SQLite3 for the database and Fossil for version control. Users had the option to play the game in multiplayer mode with another user on the same computer, over email or over the local area network. Players could play the game using the CLI (colorful ASCII art) or the GUI. The program included 4 game modes (minishogi, standard shogi, chu shogi and tenjiku shogi) and 5 difficulty levels (normal, hard, suicidal, protracted death and random). The different game modes meant different pieces and a unique set of permissible movements for each. The difficulty levels were for how challenging the AI would play against the user. We also setup a one-click installation procedure (Linux and Windows compatible) for the game to ease installation headaches for users (download dependencies, create a launcher icon, etc.).

My primary development focus was the AI and its difficulty levels. I also worked substantially on the game state initialization and the command line interface (CLI). I implemented the decision making algorithm using a Monte Carlo tree search.

Some of the challenges I faced when developing this project were the new language and technology, unfamiliar concepts, working in a diverse team and new requirements. We were programming in Julia, a relatively new and not-so-popular-yet programming language. Julia's lack of maturity meant that documentation was difficult to find, especially for SQLite3 and GTK. Using Fossil for version control also presented some challenges as hosting services for Fossil were few and unreliable. Working in a diverse team meant that each developer had interesting ideas to offer and unique solutions to tasks at hand. As such, unifying our code proved to be a challenge. However, within a short span of time, we had agreed to a set of guidelines to ensure that our code was coherent. Another major challenge that we faced was the evolving project requirements. Every 2 weeks, we would be handed a new set of additional features to implement. This meant that we had to develop with a high level of abstraction so that when new requirements were released, we could easily handle their integration without excessive refactoring.

Throughout all of this, I guided my team and made important decisions about how to deal with new challenges. I assigned tasks to team members and aided them if they required any assistance. As a result, we all achieved high marks for this project.