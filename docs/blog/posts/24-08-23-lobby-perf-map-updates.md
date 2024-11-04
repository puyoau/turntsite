---
draft: false
date: 2024-08-23 
categories:
  - TURNT
  - In development
authors:
 - elim
---

# Lobbies/Leaderboards, Performance & Netcode, Map Importing

A quick update to let you all know I'm alive!

<!-- more -->

### Lobbies/Leaderboards

Lobbies are very close to completion. The next update will feature lobbies. By default there will be an "official" always-active lobby. This is basically the same as the online server you all know, however anyone in the lobby can play any map they want. Changing map to one that somebody else in the lobby is playing will allow you to see them in the world and spectate them. If you're in a lobby and play a demo from a different map, it will simply change your map within the lobby before playing the demo. This means you won't be disconnected.

Lobbies can feature any map, with the exception of maps in development (sorry, this is still a WIP). You can also play any physics type you want and enter practice mode while remaining in the lobby. Practice mode is supported by spectating, so I hope to see people theorycrafting and building routes together soon!

Leaderboards are still in development, but I've got a middle layer working now which allows me to provide all the leaderboard functionality we're after. There are frequent DB migrations occurring to ensure that all data saved to the intermediate solution end up in the backend. Then, when I flick the switch to swap over to the "proper" backend, there will be no downtime and things will resume as always.

### Performance & Netcode

A lot of work has been going on, moving all of the important netcode to C++. A lot of this is a biproduct of building lobbies (and not just rebuilding the netcode for the sake of it), but so far I've managed to keep things 1:1 while porting. bits and pieces over. I'm trying to strike a balance of improving CPU-side perf for both clients and server without spending ALL of my time and effort just being a geek. I really do want this game to progress, so I cannot continue rebuilding things that already work over and over.

So far I've reduced bandwidth consumption by ~35% per-player, and I'm seeing simulation speeds (which affect both server and client) improve by around 15% on higher end hardware (5900X, Win64 as my test) and approx 30% on lower end hardware (4th gen i3 in a Surface Pro 3 - the machine I'm using as my min-spec test since it's what I have available).

I've also started preparing more graphics options. This is mostly for lower end GPUs, but ultimately I also know a lot of us (myself included) simply like making our game look like shit to provide the best visual clarity. I will ensure I accommodate both performance concerns as well as clarity concerns. The game is for our bipedal community to have fun going fast, not to force potentially-unwanted visuals in everyone's faces. However, for those who do enjoy higher end graphics I will be more than happy to delve deeper there too - but later on in development.

### Map Importing

In order to properly support both TrenchBroom and GTKRadiant, I've needed to accept the fact that collision geometry is essential. Maps like dfwc2017-6 show issues by generating the collision geometry from the regular map geometry (ie, the bridge before the 2nd shootable door) so I've been investigating how I can properly support this without breaking the physics. Anyone remember the old issues of landing on top of two joining meshes and being stopped as if you hit a wall? I need to avoid that hahaha

Lots coming in the next update. My desire is to release it in time for the holiday season. Life does its things though so no promises of course, but work has been steady for a few months now so there is very real progress being made. Looking forward to proving it to you all!