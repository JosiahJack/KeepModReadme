---
id: 76to6fztygwk9bqxj663bx2
title: Common Attributes
desc: ''
updated: 1681958297387
created: 1657646721298
---
There are a few common attributes for all items.  Most of these relate to respawning after being picked up.

|Key|Type|Default|Description|
|---|---|---|---|
|spawnflags|integer|16|Respawn.  Set to enable the item to respawn after being picked up.  Set the other `respawn_*` attributes to customize default timers.|
|||32|Floating.  Can prevent items from falling out of the level and is useful to tuck items into cubby holes or to have tantalizing magical items floating in air making you wonder how to get to them.  Also useful to have items start up in the ceiling (possibly above a `func_illusionary`), and have them fall later on.  Target to have the item drop down.|
|||64|Start OFF.  Entity will start in the OFF estate.  Use the [[point-entities.logic-and-entity-state-system]] to enable later on.|
|||128|No Particles.  Disables the particles and effects for respawn.  Items with respawn active, will be faintly transparent.|