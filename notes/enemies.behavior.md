---
id: gb9igfysmrzmdslln5fttro
title: Behavior
desc: ''
updated: 1657649728010
created: 1657649587702
---
Enemy behavior in original Quake is largely simplistic.  See a player, get
angry at the player, chase the player in a straight line for indefinite amount
of time.  If the enemy bumped walls, they would search for 5 seconds in one
randomly picked direction either left or right.  If hurt, they would get angry
at whoever hurt them unless they had the same classname.  This behavior is
still preserved when no changes or customizations have been made.

One exception is that monsters now look for any other opposing monster or 
player, not just players.  See Alignment below.

## Basic Overview
It is possible to make numerous customizations to enemy behavior.  We have 3
variables that determine behavior on a monster:

* alignment
* temperament
* vulnerability

All 3 can be changed by the mapper per monster.
All monsters default to 0 for all 3, which is Evil Angry Normal.

|Key|Value Descriptions|
|---|---|
|alignment|0 = Evil, generally opposed to players.  Ignores neutral alignment.
||1 = Good, generally on the player's side.  Ignores neutral alignment.
||2 = Neutral, indifferent to everyone unless provoked.  Passive temperament by default.
|temperament|0 = Angry: reacts on sight, pain, or hearing nearby combat or shooting players.
||1 = Cowardly: Will flee away unless cornered, with slight chance of fighting back when not cornered
||2 = Passive: Will not respond if others are getting attacked.  Only respond and get angry if attacked directly.
||3 = Calm: Will attack opposing enemies on sight, will follow leaders on sight if not otherwise occupied. Forgetful of enemies.
||4 = Psychotic: Similar to Angry, but will attack anyone, even friends, if they hit us.
|vulnerability|0 = Normal: Take 100% damage from everyone.
||1 = Resistant: Take 100% damage from differing alignment, 50% from same alignment, that is, friends.
||2 = Seraphic: Take 100% damage from differeing alignment, 0% from same alignment.