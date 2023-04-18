---
id: uesi617nw8a02r19kn2bhut
title: Bosses
desc: ''
updated: 1657677981318
created: 1657645842218
nav_order: 2
---
_Boss_ is used to classify a type enemy usually used in a finale and typically much larger, more powerful, or having more varied attacks.  Typically health is much higher than standard enemies, or at least higher than a Shambler.

Any boss can be a normal monster.  One of Keep's mantras is that "the mapper is always right", and thus Keep allows you to use a monster however you want, with or without special setup. 
 Historically, bosses in Quake have been used in special setups, alone or with underlings.  Keep makes it such that any monster can be used as a normal enemy or a boss.

Any monster can be a boss, it merely depends on the context. It is also possible to override default monster values such as `health` and `deathstring`.  `deathstring` should start with a space and reference being killed by the monsters `netname`.  For instance `" was tusk-skewered by a raging Wildebeast."` (without quotes when entered in the map editor).  This gets put in a statement immediately after the player's netname in the displayed message at the top of the screen whenever the player dies, example: `Ranger was tusk-skewered by a raging Wildebeast.` 

## Purpose of This Page
* Show what is somewhat hidden: Many bosses are simply variants of existing enemies and are only able to be used by placing a normal enemy and then checking the appropriate spawnflag.  Even more hidden, some boss variants are determined (historical implementation) by their skin color or some other attribute specified by the mapper.  In some more obscure or potentially confusing instances, these have been made into separately listed entities with their own names for ease of discovery and implementation.
* This listing is meant to provide a helpful understanding of the possible end battles available in Keep without having to read through every available monster in the very long full list.  It isn't always obvious that a monster was intended or can be suitable as a boss.
* Delineate which monsters have special setups as an option.

# Boss List
Note: This listing is of monsters historically used as bosses, for a comprehensive listing of all monsters, refer to the listing in [[enemies]].
* [[enemies.monster_anac]]
* [[enemies.monster_armagon]]
* [[enemies.monster_balrog]]
* [[enemies.monster_bane]]
* [[enemies.monster_baron]] (Normal, Fire, Earth, Wind, Water)
* Boglord
* Fire Shambler
* Chthon (lightning event killable)
* Chthon (normal weapon killable)
* Chthon (firetop boss)
* Slime Chthon (normal weapon killable)
* Cyberdemon
* Dark Lord
* Death Lord
* Brigade Commander (aka Fury Boss)
* Dragon
* Sculptor (aka Eidolon)
* Gug
* Hell Lord
* Warlord
* Ice Golem
* Judicator
* Sword of Justice (aka Prospero?)
* Hephaestus
* Vomitus Meatwad
* Minotaur (aka Garoch aka Shuffler aka Yakman)
* Guardian
* Mummy
* Warlock
* Demon Magus (aka Troglodyte aka Faustus)
* Nightshade
* Scragmother
* Shub-Niggurath (teledeath only, passive)
* Shub-Niggurath (normal weapon killable, attacks)
* Shub-Niggurath (upsidedown, normal weapon killable, attacks)
* Shub-Niggurath Tentacle
* Dragon King
* Seeker
* Vore Queen
* Guardian Skull Wizard
* Searg (aka Super Grunt)
* Overlord
* Sweeper
* Master (aka Trogboss)
* Lava Worm (aka Virtus)
* Vomitus
* Vermis
* Wraith (nonminions AD variant)
* Zerstorer
* Inquisitor
* Nehahra

### TBD
* Nyarchon
* Death
* Famine
* Pestilence
* War
* Nyarlathotep
* Trickster
* Revenant Pharoah
* Mhorbo (on player's side though)