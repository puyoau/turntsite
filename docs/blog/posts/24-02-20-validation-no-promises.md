---
draft: false
date: 2024-02-20 
categories:
  - TURNT
  - In development
authors:
 - elim
---

# Leaderboards/Lobbies, Validation Server, Optimisation

Hello everyone! 

Just letting you all know I'm alive and that development is still coming along.

<!-- more -->

With the impending completion of leaderboards and lobbies, I've had to put the validation server under some pressure to see if it buckles anywhere. Right now on the single-core VPS it runs on, it takes around 2000ms (2 seconds) to validate a run that is 45seconds long. While this might sound good, this is actually kinda rubbish given how simple the game simulation is (mathematically speaking).

As such I've been doing some optimisation passes. I've profiled where the game sim is lacking, and a majority of it rests in commonly-used functions which are performing vector math in GDScript. For instance, the biggest culprit by far is ground detection (which is only 14 lines of code!). I've been moving some of these frequently-accessed functions to C++ and making sure that the overhead of making calls to-and-from GDScript and C++ are not hindering the optimisations more than the benefits gained.

So far so good, though! Don't want to release any numbers right now until I can validate that the simulation is unaffected (ie demos are still valid after the changes) but it seems to be coming along well. This optimisation affects the game simulation in general, so all players will see the benefits too. Those of you already comfortable running 250fps+ probably won't notice anything, but anyone struggling on some lower-powered systems may see some improvements (especially in larger maps like dfwc2017-6).

My pace has been picking up on TURNT lately, and while I'm uncomfortable promising any kind of release schedule for the next update (because I haven't been delivering "on time" for a while) I can say that I'm looking forward to seeing you all try what's up next!