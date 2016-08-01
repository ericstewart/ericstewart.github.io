---
layout: single
title: Everywhere, The Game of Life
modified:
categories: blog
description: "Implementations of Conway's Game of Life found in the wild"
excerpt: "Implementations of Conway's Game of Life found in the wild"
tags: [coderetreat]
header:
  image: Conways_game_of_life_breeder_animation.gif
  teaser: Conways_game_of_life_breeder_animation.gif
  credit: Chris Benton
  creditlink: https://en.wikipedia.org/wiki/File:Conways_game_of_life_breeder_animation.gif
date: 2016-01-14T08:43:03-06:00
---

If you have ever participated in a [Coderetreat][], you are likely
to have implemented [Conway's Game of Life](http://www.conwaylife.com/wiki/Conway%27s_Game_of_Life) (GoL). It is a reasonably
simple simulation of where cells evolve as an example of a *Cellular Automaton*. It is a well-suited exercise for [Coderetreat][] since the rules are
relatively simple, yet it presents the need for a good number of
design choices. If you are unfamiliar with it, read the link above or check out [The Game of Life: a beginner's guide](http://www.theguardian.com/science/alexs-adventures-in-numberland/2014/dec/15/the-game-of-life-a-beginners-guide).

Like a person shopping for a car who suddenly notices all the models they are interested in while driving around town, I see implementations of *Conway's Game of Life* everywhere. They are interesting to look at now and then, especially when I am not preparing for or in the middle of a Coderetreat.

Some recent finds:

* [cljs4excel GoL](https://github.com/cfelde/cljs4excel/blob/master/examples/conway/conway.md) - An example project demonstrating running [ClojureScript][] in Microsoft Exel (via the [cljs4excel project](https://github.com/cfelde/cljs4excel))
* [https://github.com/Syntaf/GameOfLife](https://github.com/Syntaf/GameOfLife) - A terminal based GoL implemented in [Rust][] (very colorful)
* [bostonaholic/conway-cljs](https://github.com/bostonaholic/conway-cljs) - A [ClojureScript][] implementation of GoL. [See it here](http://matthewboston.com/conway)
* [teropa/life.cljs](https://gist.github.com/teropa/37bf6d41f0296259c683) - Another [ClojureScript][] implementation (also using [Reagent](http://reagent-project.github.io) in a Gist
* [Conway's Game of Life - A Demonstration and Postmortem of a Clojure/ClojureScript Project](http://fn-code.blogspot.com/2015/03/conways-game-of-life-demonstration-and.html) - A write-up with code samples on implementing GoL in [Clojure][]
* [sasa1977/conway.ex](https://gist.github.com/sasa1977/6877c52c3c35c2c03c82) - An implementation of GoL in [Elixir][]
* [eoinsha/gol_ex](https://github.com/eoinsha/gol_ex) - Another [Elixir][] implementation of GoL (one of the few I could get running (I'm new to Elixir))

You can see where some of my recent language interests lie by what I present here. I find it helpful to read the code in implementations of a problem I am already familiar with to practice code reading and learn about different implementation approaches.

Please let me know if you have seen a *Game of Life* implementation that you find interesting or insightful. Also, what code do *you* read for learning?

[Coderetreat]: http://coderetreat.org
[Clojure]: http://clojure.org
[ClojureScript]: http://clojure.org/about/clojurescript
[Rust]: https://www.rust-lang.org
[Elixir]: http://elixir-lang.org
