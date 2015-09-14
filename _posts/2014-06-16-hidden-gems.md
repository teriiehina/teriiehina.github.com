---
layout: post
title: Hidden gems in WWDC 2014 Videos
categories:
- iOS
tags: [wwdc]
status: publish
type: post
published: true
---

Like always, Apple gave us a lot to watch with its WWDC. This year, excluding the Opening Keynote and the Apple Design Awards, there is 108 presentations one can watch.  Those amount to 89 hours, 4 minutes and 25 seconds exactly. That is more than 3 days and 17 hours of non-stop watching. A season of GoT is 10 episodes of 55 to 57 minutes each, thus 3 seasons would give us 28 hours. Less than a third.

So aside from "What to watch first", which will likely depends on your app's category or your personal interests, there are a few things that Apple didn't talk about, or very fast during the keynote, and that you might find useful, whatever your needs.

  - 223: Prototyping : Fake it till you make it.
  - 236: Building interruptible and responsive interactions
  - 302: The new iTunes Connect
  - 416: Building modern frameworks
  - 705: Distributing Entreprise Apps (which is always a good refresh)
  - 716: Fix bugs faster using Activity Tracing (my personal favorite, there isn't much content but Activity Tracing is really great for iOS or OSX)

What abou you ? Have you find others hidden gems ?


If you are curious of how to get the total length for videos (or audio), you can find [a commandlinefu page giving you an hint](http://www.commandlinefu.com/commands/view/3612/get-the-total-length-of-all-video-audio-in-the-current-dir-and-below-in-hms). The one I used was:

    mplayer -vo dummy -ao dummy -identify * 2&gt;&amp;1 | grep ID_LENGTH | sed 's/.*=\([0-9]*\)/\1/' | xargs echo | sed 's/ /+/g' | bc | awk 'S=$1; {printf "%dh:%dm:%ds\n",S/(60*60),S%(60*60)/60,S%60}'