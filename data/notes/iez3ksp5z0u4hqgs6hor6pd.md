
![Monster Picture](assets/img/archer_lord.png)

Archer knight that shoots arrows with a bow.  Aims for bit before firing; will
avoid firing if there is someone in the way who is friendly and wait for a
clear shot.

 > Model is based on the archer from Hexen2.  AI used is mostly Quake's with
 > bit of Hexen2's.  Fancy moves such as ducking and sidestepping are NOT used, 
 > since it is so un-Quake (and I simply want a medieval style grunt/enforcer).
 > Holding his shot after drawing the bow, along with much of the shooting AI, 
 > was ported over.  -- Patrick Martin

|Name  |Desription|
|------|-------------|
|Entity|monster_archer_lord|
|Source Mod|Hexen 2, Drake|
|Health|325|
|Gib Health|-40|
|Pain Flinch|40|
|Drops|2 Bolts|

.

|Attack Type|Attack Name|Description|Damage|Speed|
|-----------|-----------|-----------|------|----|
|Projectile |Arrow Shot|1 arrow launched|30|1000|

.

Hexen2:  40% chance to automatically shoot in melee.
In Hexen, this is done before random and shot checks.
Here in Quake, do this after checking shot because it is possible for
thin monsters to squeeze between the archer and target even in melee range.