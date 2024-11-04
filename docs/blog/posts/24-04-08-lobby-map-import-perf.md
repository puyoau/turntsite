---
draft: false
date: 2024-04-08 
categories:
  - TURNT
  - In development
authors:
 - elim
---

# Lobbies/Leaderboards, Map Importing, Performance

There are three main things I'm working on. I'll list them in order of expected release:

<!-- more -->

### Lobbies/Leaderboards

This work has been going on for a while now, ey! Long story short, the fella working on the backend has a massive amount going on irl atm. So I'm setting up a basic database just to get things rolling. All the data and schemas will be exportable, so I'm making sure that we don't end up in a "it's just temporary, but actually it says like this forever" situation.

### Map Importing

I've made some good progress in having an ingame .map importer. While it's aimed at Trenchbroom, it should be able to handle GTKRadiant .map files as well as long as you don't use fancy q3 features (like curved surfaces). Any entities that the game doesn't support (basically all of them right now) will be stripped out before the geometry is generated so you won't need to worry about whether you'll break the game or not. 

The first iteration of map importing will be rough at best and not SUPER desirable. But it will at least provide a way for testers to slide around their maps. Any maps that people want added to the game after they've tested I'll be happy to add. At least until there's a content management system in place. Maps may also be loaded directly from a maps folder inside the game folder, so you won't necessarily have to wait until I push an update out to play somebody else's "finished" map.

### Performance Updates

This work is ongoing but is happening in a parallel branch. It's not critical to the game as it stands, but will become desirable as mappers start fleshing out more complicated maps.

General performance updates (simulation performance, physics improvements, netcode optimisation) will be dotted throughout the year. Graphics quality options are also on their way, which will both enable lower end machines to play on higher fps than they can currently as well as making the game look a bit nicer on newer machines if the players want to.

As always, apologies for the delay. It's tough to work on games fulltime as a job and also set aside time for TURNT, but I've never thought about stopping development on it. It's a good bit of fun and something the community deserves! And if I can ever find a way to make it open source sooner rather than later without getting myself in trouble at work, you bet your TIGHT ass I'll do it.

### Fun Side Note

Oh and as a fun side note, custom resolutions are on the way without affecting the fullscreen-ness of the program. So if you have an ultrawide monitor and want to play 16:9 you will be able to, and if you simply prefer 4:3 you'll be able to do that as well without needing to do any strange work outside of the game

