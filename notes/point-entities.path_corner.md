---
id: z5scld7w6078d0owznmvu6b
title: path_corner
desc: ''
updated: 1681992569001
created: 1681954895033
---

The path_corner is a 16x16x24 trigger.  This is used for entities that have
following behavior to move to as their goalentity.  Typically this is only for
[[point-entities.func_train]] or [[enemies]].

The next waypoint is specified as the `target` of a path_corner.  Typically
multiple path_corner's are setup in a target->targetname chain like so:
- path_corner (1): `targetname` path1wp1, `target` path1wp2
- path_corner (2): `targetname` path1wp2, `target` path1wp3
- path_corner (3): `targetname` path1wp3, `target` path1wp1

Then a monster or train has its `target` set to one of the corners to start
following the path.

|Key|Value|
|---|---|
|targetname   | Name of current path corner
corner_event | Name of target(s) to trigger when used/touched
corner_route | Change path_corner route (1-3 routes, 4=exact, 5=random)
corner_switch| Change spawnflags REVERSE (-1=NO, 1=YES, 2=Toggle)
corner_pause | Change spawnflags NOPAUSE (-1=NO, 1=YES, 2=Toggle)
corner_pstate| Change passive state (-1=OFF, 1=ON, 2=TOGGLE)
state        | Starting route (1=forward, 2=alt forward, 3=backward)
target       | Targetname of FORWARD route
target2      | Alternative FORWARD route
targetback   | Override default BACKWARD route
wait   | fixed amount of time to pause at corner (=-1 stop)
delay  | random amount of time to pause at corner
alpha  | Override default for visual arrows (def=0.35)
speed  | Override default speed of func_train (def=100)

.

|Spawnflag|Name|Description|
|---------|----|-----------|
|1|Exact|Exact route logic (def=random route choices)|
|2|Instant|Follower will teleport to this corner from previous|
|4|Reverse|Flip direction when coming to this corner back to where we came|
|8|No pause|Train will not wait at the corner, not even 0.1s!|

### Advanced Features
It's possible to set a particular path_corner to be
teleport to such that instead of the follower moving smoothly to it, would
instantly teleport to it, though without the teleglitter effect and sound.  Teleport to next path corner is not only a feature for trains, but monsters as
well.

A path_corner fires an `event` when a monster or train gets to the path_corner.
 
The [[enemies.tether-system]] also makes use of the path_corner as its tethers.