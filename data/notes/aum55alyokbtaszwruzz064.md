All enemies have certain attributes in common.  All enemies start with `monster_` in their entity's classname.

For understanding the `Type` given below, refer to [[general.data-types]].

## Spawnflags

### `spawnflags`
* **Type:** integer
* **If Set:** This value is a decimal value used as on/off bits.  Each bit indicates whether to use or don't use a certain option.  The sum of the decimal values is the resultant `value` of the `key` called `spawnflags` (Recall that Quake uses `key|value` pairs on all entities to specify data about that entity, for instance `targetname|hello` gives that entity the name of "hello").  For spawnflags, level editors let you check off check boxes to select certain options.  The values are summed together to give the `value` to `spawnflags`; for instance checking 2, 4, and 8 gives a summed `value` of `14`.  Since each value is equal to the binary equivalent of 1, 10, 100, 1000, etc. each sum is inherently unique and guarantees that only certain digit places are changed from 0 to 1.  The maximum number of bits available is 24. `Technical Note: since Quake uses 32 bit floats, you might wonder why we can't use all 32.  The remaining bits would be used to indicate positive/negative and to specify power to raise to such as 2 for squared, but Quake's parser doesn't look at these for spawnflags.`

|Number|Name|Desription|
|------|----|----------|
|1|Ambush|This makes enemies not react to nearby angry monsters or noises of the player.  They will lurk until targeted or until they see the player.|
|2| | (Special option, if used, see specific enemy's use)|
|4| | (Special option, if used, see specific enemy's use)|
|8|No Sightsound | This prevents enemies from making their usual alert noise when they are targeted or see the player.|
|16| NoIdle | This prevents enemies from making their usual idle noises while standing or walking, useful for lurking monsters who are hiding in closets or around corners.|
|32|NoGFX | Only useful if 64 Delay Spawn is also set.  This prevents them from making the usual teleport sound or teleglitter effects when they spawn in.|
|64| Delay Spawn |Super useful. Makes it such that monster will only spawn in when targeted.  Monster will spawn right where placed, if there's room.  Only spawns once. In standard Quake (also lovingly referred to as "vanilla"), it was necessary to have the monster standing in a place such as a separate box off to the side of the map with a `trigger_teleport` on top of them that would be `target`ed to have them teleport in to an `info_teleport_destination`.  This is no longer necessary by using this spawnflag and reduces the complexity for teleporting in monsters.}
|128| Angry |  This causes the monster to spawn angry at the player as if the monster had seen the player.  Usually used along with 64 Delay Spawn to have monsters teleport in angry, but also possible to have monster start angry at level start.  NOTE: This overrides the passive state of the monster and monster will always be upset at and attack the player.|
| 256 | Not in Easy |This monster will be completely removed for Easy skill setting. NOTE: 256, 512, 1024, and 2048 are called the Appearflags.  _Appear_ refers to whether or not the monster will be present at all, normally or delay teleported.|
| 512 | Not in Normal | This monster will be completely removed for Normal skill setting.|
|1024 | Not in Hard |This monster will be completely removed for Hard and Nightmare skill setting.|
|2048 | Not in Deathmatch |This monster will be completely removed for specialty Deathmatch modes.  NOTE: All monsters are usually removed for normal Deathmatch.|
|4096 | | (Special option, if used, see specific enemy's use)|
| 8192 | | (Special option, if used, see specific enemy's use)|
|16384 | |(Special option, if used, see specific enemy's use)|
|32768 | Can Drown | This monster will drown when in a liquid (water, slime, lava).|
|65536 | | (Special option, if used, see specific enemy's use)|
|131072 | | (Special option, if used, see specific enemy's use)|
|262144 | | (Special option, if used, see specific enemy's use)|
|524288 | | (Special option, if used, see specific enemy's use)|
|1048576 | | (Special option, if used, see specific enemy's use)|
|2097152 | | (Special option, if used, see specific enemy's use)|
|4194304 | | (Special option, if used, see specific enemy's use)|
|8388608 | | (Special option, if used, see specific enemy's use)|
* **If Left Blank:** Monster will start and behave normally.

## key|value's
|Key             |Type   |If Set              |If Left Blank      |
|----------------|-------|--------------------|-------------------|
|`angrytarget`   |string |If monster starts angry (either spawnflag 128 or by being targeted), this specifies who to be angry at.  Monster will search for and find first entity with matching `targetname` in the edict list and set that entity to the monster's `enemy`, but only if the target is a monster.|A player will be found instead.|
|`deathtarget`   |string |When monster dies, this is an extra `target` to trigger.  Works in addition to setting `target`.  The `deathtarget` will be used, e.g. if a door is deathtargeted, then the door's `use` will happen; doors typically open on use.|Nothing additional will happen (normal `target` will still work on death).|
|`health`        |integer|This changes the monster's starting health.  Also overrides any health changes caused by spawnflags.|The default monster health will be used.|
|`exactskin`     |integer|This changes the monster's `skin` to use the exact value specified.  If the value is too high, most engines will default to `skin` 0.|The default monster `skin` will be used and random range will be used, if the monster has it (e.g. monster_army has a few random skins)|
|`upgrade_axe`   |boolean|Monster will only appear if the player has the upgraded Shadow Axe weapon that can gib fallen zombies.|The monster will appear normally.|
|`upgrade_ssg`   |boolean|Monster will only appear if the player has the upgraded Widowmaker (triple shotgun) weapon.|The monster will appear normally.|
|`upgrade_lg`    |boolean|Monster will only appear if the player has the upgraded AD plasmagun weapon.|The monster will appear normally.|
|`nomonstercount`|boolean|Enemy won't count towards the total until it is killed.  Useful for monsters in super secrets.|Enemy counts as 1 towards the count.  If this is a denizen, will count towards the total number of denizens instead.|
|`delaymonstercount`|boolean|Monster won't contribute to the total count until it is spawned.  Useful for monsters in secret areas or super secrets.|Enemy counts as 1 towards the count.  If this is a denizen, will count towards the total number of denizens instead.|
|`infightextra`|float|When monster infights with another monster, it's damage will be multiplied by this `infightextra` value.  Can be less than 1 if you want infighting to take longer.  Cannot be less than or equal to 0 or it will be treated as if it were left blank...|Will default to 1.  Normal damage will be dealt against other monsters.|
|`pain_ignore`|boolean|Monster will never go into pain animation.|Monster will react to pain normally, if they have a pain animation.|
|`noinfighting`|boolean|Monster will not react to damage from monsters, unless they are psychotic.  Will still change enemy to another player if damaged by a player.|Monster will react and infight normally with other monsters, so long as they have opposing alignment, differing classgroups, differing classnames.|
|`no_liquiddmg`|boolean|Monster will not get hurt by lava or slime.|If monster is normally damaged by a particular liquid, they will be damaged.  E.g. zombies are usually damaged by most things.|
|`no_zaware`|boolean|Monster will not adjust lobbing aim for difference in height.  Usually only useful for ogres.  This is default ID1 behavior for normal ogres and has no affect on standard monster_ogre's.  This flag is really only useful for Hunter Ogres (monster_hogre, monster_hogremac, monster_hogreham).|If monster has z-aware capability, it will adjust its aim to help it hit players better...somewhat uncannily accurately too.  Only Hunter Ogres have this ability (monster_hogre, monster_hogremac, monster_hogreham)|

### `bboxtype`
* **Type:** integer
* **If Set:** Overrides the monsters size.  "bbox" stands for "bounding box" and is the rectilinear, axes-locked size of the monster in the world in x, y, and z directions.  There is a catch, however, as the exact size specified only affects the bullet tracing and impact against the monster and player collision with the monster.  The monster's collision size against the world will always only be one of 2 sizes.  The engine will round the size to the nearest one of these 2: hull1 of 32 x 32 x 56, or hull2 of 64 x 64 x 88. (Technical Note: hull0 is point size 0 x 0 x 0 used by bullets, etc.  The hulls are baked into the map at compile time.  This size is unrelated to the shown editor's box; the editor will use the fgd's size which could be either one of the hull sizes or the bbox size).

|Bbox Name|Value|Mins, Maxs|Volume|
|---|---|---|---|
|Tiny|1|-16 -16 -24, 16 16 16|32 x 32 x 40|
|Square|2|-20 -20 -20, 20 20 20|40 x 40 x 40|
|Flat|3|-4 -24, 24 24 22|48 x 48 x 46|
|Short|4|-16 -16 -24, 16 16 32|32 x 32 x 56|
|Tall|5|-16 -16 -24, 16 16 40|32 x 32 64|
|XTall|6|-16 -16 -24, 16 16 64|32 x 32 x 88|
|Wide|7|-24 -24 -24, 24 24 40|48 x 48 x 64|
|Giant|8|-24 -24 -24, 24 24 64|48 x 48 88|
|WideFlat|9|-32 -32 -24, 32 32 24|64 x 64 x 48|
|Massive|10|-32 -32 -24, 32 32 64|64 x 64 x 88|
|Golem|11|-24 -24 -24, 24 24 72|48 x 48 x 96|
|Dog|12|-20 -20 -24, 20 20 16|40 x 40 x 40|
|Shade|13|-64 -64 -24, 64 64 64|128 x 128 x 88|
|Fish|14|-16 -16 -24, 16 16 24|32 x 32 x 40|
|FishSmall|15|-12 -12 -16, 12 12 16|24 x 24 x 32|
|Eel|16|-16 -16 -16, 16 16 16|32 x 32 x 32|
|Wyrm|17|-112 -112 -24, 112 112 112|224 x 224 x 136|
|Ryu|18|-56 -56 -24, 56 56 56|112 x 112 x 80|
|Hydra|19|-20 -20 -16, 20 20 16|40 x 40 x 32|
|Willy|20|-32 -32 -24, 32 32 5|64 x 64 x 29|
|Cyber|21|-20 -20 -36, 20 20 74|40 x 40 x 110|
|Anaconda|22|-32 -32 -16, 32 32 174|64 x 64 x 190|
|Justice|23|-16 -16 -24, 16 16 56|32 x 32 x 80|
|Psyder|24|-32 -32 -24, 32 32 160|64 x 64 x 184|
|XMassive|25|-32 -32 -24, 32 32 80|64 x 64 x 104|
|BrkTiny|26|-12 -12 -24, 12 12 16|24 x 24 x 40|
|ShalBoss|27|-46 -40 -24, 46 40 100|92 x 80 x 124|

* **If Left Blank:** The enemy will default to its usual size.

|Key             |Type   |If Set              |If Left Blank      |
|----------------|-------|--------------------|-------------------|
|`gibondeath`|boolean|The enemy will burst into gibs when killed, if it supports gibbing.  Some monsters cannot be gibbed or have special deaths auch as monster_tarbaby or monster_skullwiz who explode and fade respectively.|The enemy will die normally, gibbing only if hurt to a health below its gibhealth.|
|`bodyfadeaway`|float|Changes the default time for the body to fade and dissappear after killed.  Time = 10 + ((random between 0 and 1) * `bodyfadeaway`.  If the worldspawn's `bodyfadeaway` is set to greater than 0, that will override this setting and default to 10 to 15 seconds.|The enemy's body will fade after 999999 seconds (about 4.6 hours), unless the map's worldspawn `bodyfadeaway` is greater than 0.|
|`turrethealth`|float|What percentage of health should be remaining before a monster that is acting as a turret is released from turret mode and begins to chase the player.  Useful for perched ogres who are in turret mode (stationary, projectile attackers), who you then want to jump down and chase the player after the player has hurt them.  Monster will remain stationary until health = health * `turrethealth`.  Monsters not in turret mode will ignore this value.|Monsters in turret mode will remain stationary until dead.  Monsters not in turret mode will ignore this value.|
|`turrettarget`|string|Set to the name of a target to activate when the monster's health falls below health * `turrethealth`.  Useful if you want to have the environment react to a monster who is no longer in turret mode (stationary, projectile attacker), such as a door opening or a breakable breaking as the monster gets angry and bursts forth.  Monsters not in turret mode will ignore this value.|Monsters released from turret mode will not trigger anything then.  Monsters not in turret mode will ignore this value.|
|`cooponly`|boolean|The enemy will only be present in coop, regardless of skill setting.  Skill settings Appearflags are still respected if coop is active and monsters who are set to remove on that skill will still be removed.|The enemy will appear normally.|
|`passive_state`|boolean|The enemy will not attack the player on sight and only attack if provoked or if they see the player attack another monster.|The enemy will behave and get angry normally when they see the player.|
|`passive_resethp`|boolean|Reset health to full when returning to passive.  After the player has been lost out of sight, the monster will return to being passive.  Useful for magical guardians who have a tether point set, but a tether is not required.|The enemy's health will never reset.|
|`passive_resettimer`|float|Time after player has been lost out of sight before the monster forgets the player and returns to being passive and non-angry.|The enemy will not forget the player until after 999999 seconds (about 4.6 hours).|
|`angles`|vector|Pitch Yaw Roll for viewing angle.  For instance 0 90 0 to face "north".  Set the middle value to -1 for random facing orientation, e.g. 0 -1 0.  Pitch and Roll are otherwise not used.|The enemy will orient based on `angle` if set by the map editor.|
|`jumpdist`|vector|Jump distance defaults for monsters that have jumping behavior (e.g. monster_voreling). Specified as X Y Z with spaces between.  X = distance, Y = height.|The enemy will jump with its defaults.|
|`jumprange`|vector|Range at which the monster will attempt a jump attack - x y 0, for example 200 300 0, which means the monster will attempt jumps when the player is between 200 and 300 units from it.|The enemy will jump with its defaults.|

## Special Overrides
These are attributes not listed on the fgd and are meant for special use cases or testing.  It is highly recommended to _not_ use these values since it can confuse players when, for instance, enemies simpy won't die if their health is made to be higher than normal.  Could also have a use in a special bonus level to make all enemies have only 1 health.

|Key             |Type   |If Set              |If Left Blank      |
|----------------|-------|--------------------|-------------------|
|`health`|float|Changes the enemy's health to be this value.  Setting to less than or equal to zero will be the same as if left blank.|The enemy will have its default health and be predictable and satisfying.|
|`deathstring`|string|Changes the message displayed when the player is killed by this enemy.  Should always have a space as the first character and also highly recommended to include the monster's name.  Example: ` was tusk-skewered by a raging Wildebeast.`|The enemy will have its default message and netname displayed within.  Some enemies randomize between a few different appropriate messages.|

***

# Example Monster
>Picture goes here>

![Example](assets/img/ogre.png)

>Used ogre as an example

Description goes here and provides interesting info that isn't described in other fields.
Example: Not actually an available entity.  Able to teleport away.

|Name  |Desription|
|------|-------------|
|Entity|entity name, e.g. monster_example|
|Source Mod(s)|name of mod(s) found in with primary mod listed first|
|Health|health amount|
|Gib Health|damage below 0 required to gib the monster into chunks|
|Pain Flinch|damage required to cause pain animation|
|Drops|what enemy drops on death|

.

|Attack Type|Attack Name|Description|Damage|
|-----------|-----------|-----------|------|
|Projectile |Example Shot|Min-Max shown with hyphen|Hit(Splash)|
||Example Shot2|Radius shown in ()'s|0(100)|
|Melee|Example Thwack!|Does 0-3 damage per frame|3-9||
