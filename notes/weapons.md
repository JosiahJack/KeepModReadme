---
id: tt3tq5iqjre6pwmilg8962d
title: Weapons
desc: ''
updated: 1657678934391
created: 1657646930409
---
There are numerous weapons available.  Below is a chart listing each weapon
with its stats.  The impulse value given below is the internal number used by
the code to switch to that weapon; this can be used via the console by entering
`impulse ###` console command and replacing \### with the desired number from
below to switch directly to that weapon without the need for pressing a slot's
keyboard key multiple times.  Also possible to add new keybinds for specific
weapons by adding `"bind" "keyhere" "impulse ###"` in your config.cfg file and
changing "keyhere" to desired keyboard key.  The weapon has to have been picked
up first.

Further down is a chart listing the keyboard key defaults for each weapon 'slot'
and the weapons in that slot.  Pressing the keyboard key will first switch to
the first weapon in the slot that the player has in inventory; further presses
of the same key will cycle through the weapons in the slot.

### Overrides

Some weapons are _override_ weapons.  An override will fully replace a weapon
in its slot, for instance the Shadow Axe replaces the standard Axe.  The
following overrides are not given by CheatCommand since they don't always apply
to every map (refer to [Cheat Codes](8.5-Cheat-Codes.md) for more info):
* [[weapons.weapon_blaster]]
* [[weapons.weapon_chainsaw]]
* [MIRV Launcher]
* [Plasma Gun]
* [Chaingun]
* [Riot Controller]
* [Quad Shotgun]

NOTE: The [Widowmaker](3.33-weapon_upgrade_ssg.md) _is_ given since it is too
awesome not to and suits any theme.

## Weapons Table

|Name______________________|Entity_________________________|Source Mod_____|Damage_______________________________________________________|Description_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________|Ammo (Uses 1 Unless Specified)_______________|Impulse|Tome_of_Power_Effects___________________________________________________________________________________________|
|:-------------------------|:------------------------------|:--------------|:------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|:------|----------------------------------------------------------------------------------------------------------------|                                                                                                                                   
|Blood Mace                |weapon_mace                    |AoA            |45                                                           |Each hit recovers 5 HP. If off ground, first attack the player will lunge forward.                                                                                                                                                                                       |None                                         |83     |Gibs zombies. Adds third attack, area of effect health drain.|
|MIRV Launcher             |weapon_mirv                    |Drake          |120(120)                                                     |Multiple Independently Targeted Reentry Vehicles. Replaces the rocket launcher.  Launches a player guided missile that spear gibs anything in its path before it splits into 4 separate exploding missiles.                                                             |5 Rockets                                    |7      |Fires 5 shots in fan like multi-rocket launcher.
|Mjolnir's Hammer          |weapon_mjolnir                 |Hipnotic       |50, 70 to zombies; lightning initially 80, then 30 every 0.2s|Powerful blunt force melee.  Shoots out lightning if hit on ground but uses and needs 15 ammo and lightning continues to hurt a live target for 0.8s or unless out of 350 range from ground impact point.  Firing in water has the same discharge effect as thunderbolt.|None/Cells if ground hit                     |77     |Uses 30 cells on ground hit to generate lightning ball that zaps **all** enemies within a 256 unit radius.  Each lightning beam shoots through up 3 enemies in a line.  Lightning will always gib zombies.  Causes (40) burst) damage when lightning orb explodes after 1.9secs.  Works underwater without hurting the user.|
|Multi-Grenade Launcher    |weapon_multi_grenade           |Rogue          |(120) if main impacts, (90) * 4 Mini grenades                |Fires a yellow grenade that splits into 5 mini-grenades that then explode soon after.  If main grenade hits enemy or player before splitting, it does normal grenade damage.                                                                                            |Multi-Rockets                                |62     ||
|Multi-Rocket Launcher     |weapon_multi_rocket            |Rogue          |60-75(75) each                                               |Fires 4 rockets at once in a horizontal spread pattern.  Rockets semi-home to nearby monsters.                                                                                                                                                                          |Multi-Rockets                                |63     ||
|Nailgun                   |weapon_nailgun                 |ID1            |9                                                            |Fires nails out rapidly alternating from one barrel to the other.                                                                                                                                                                                                       |Nails                                        |4      ||
|Plasma Gun                |weapon_plasmalightning         |Rogue          |80-100(70)                                                   |Fires a lightning ball that explodes on impact.  Lightning ball then shoots out lightning at any nearby enemies if there are some within a 320 unit range.                                                                                                              |Plasma                                       |64     ||
|Proximity Gun             |weapon_proximity_gun           |Hipnotic       |(95)                                                         |Fires a red mine that sticks to walls.  The mine explodes only when something moves near it.                                                                                                                                                                            |Rockets                                      |76     ||
|Rapier                    |weapon_rapier                  |AoA            |35 melee, 25 projectile (with ammo)                          |Three quick melee attacks. Ammo adds a projectile that attacks 3 times. Bonus dmg against Shamblers.                                                                                                                                                                    |Blood Crystals                               |89     |Adds spin attack to rapier projectile, 120 radius damage.|
|Rocket Launcher           |weapon_rocketlauncher          |ID1            |100-120(120)                                                 |Fires a rocket that explodes on impact.                                                                                                                                                                                                                                 |Rockets                                      |7      ||
|Sanguinators              |weapon_sanguinators            |AoA            |25 dmg, hitscan.                                             |Attacks cause blood to seek player, recovering health.                                                                                                                                                                                                                  |Blood Crystals                               |87     |Bloodorbs become explosive projectiles that launch upon attack.|
|Fire Scimitar             |weapon_scimitar                |AoA            |melee 40; projectile 150(200)                                |3-hit melee combo. First attack launches player forward. Third attack adds a projectile if you have ammo.                                                                                                                                                               |Elemental Mana                               |88     |Much stronger dash, 1 projectile per attack.|
|Shotgun                   |weapon_shotgun                 |AD             |4-24                                                         |Fires a burst of 6 pellets in a spread of '0.04 0.04 0'. Spread is '0.01 0.01 0' with Sharpshooter. Defaults to hitscan, see [`temp1`](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings). Note: AD fired 1 extra visual tracer for projectiles. |Shells                                       |2      ||
|Perforator                |weapon_supernailgun            |ID1            |18                                                           |Fires nails rapidly for high damage.                                                                                                                                                                                                                                    |2 Nails                                      |5      ||
|Double-barreled Shotgun   |weapon_supershotgun            |ID1            |4-56                                                         |Fires a burst of 14 pellets in a spread of '0.14 0.08 0'. Spread is '0.04 0.04 0' with Sharpshooter. Defaults to hitscan, see [`temp1`](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings).                                                      |2 Shells                                     |3      ||
|Plasma Gun                |weapon_upgrade_lg              |AD             |45(20)                                                       |Replaces the lightning gun.  Fires a rapid burst of small blue plasma balls.  The plasma balls explode on impact causing splash damage.                                                                                                                                 |Cells                                        |8      ||
|Widowmaker                |weapon_upgrade_ssg             |AD             |4-84                                                         |Replaces the Double-barreled Shotgun.  Fires 21 tracer pellets in a wide spread of '0.14 0.08 0'.  Spread is '0.04 0.04 0' with Sharpshooter powerup. Defaults to hitscan, see [`temp1`](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings).     |3 Shells                                     |3      ||
|Void Staff                |weapon_voidstaff               |AoA            |45 on hit; 50-100 on detonate.                               |Launches Void shards, which can be detonated for radius damage. Projectiles accelerate upwards.                                                                                                                                                                         |Void Shards                                  |84     |Erratic projectiles, increased damage.|
|Magic Wand                |weapon_wand                    |Drake          |16 per spark, 64 for full charge                             |Fires a hitscan spark effects equal to currently charged mana ammo in a tight fan shape at a distance of 600 max. When fully charged, center spark is a small spark explosion with knockback, recharges ammo up to 4 at all times, 1 recharge every 0.4s.               |1-5 None                                     |79     |Mana is increased to 5 and never depletes until tome times out so every shot fires all 5 sparks.  Fires further and a fan of 5 sparks with death knight tracers on the outer edge 2 sparks for added visibility and bonus 5 damage each.|

<br />

## Weapon Slots
|Keyboard Key|Slot's Weapon 1|Slot's Weapon 2|Slot's Weapon 3|Slot's Weapon 4|
|---|---|---|---|---|
|-|Example->Override1->Override2|Example|Example|Unused|
|1|Axe->Shadow Axe->Chainsaw|Grapple|Mace||
|2|Shotgun->Blaster|Elemental Tome(Ice)|Air Fist||
|3|Double-barreledShotgun->Widowmaker->Shotcycler->QuadShotgun|Scimitar|||
|4|Nailgun|LavaNailgun|Rapier||
|5|Perforator|LavaSuperNailgun|VoidStaff||
|6|Grenade Launcher|Proximity Gun|Multi-Grenade Launcher||
|7|Rocket Launcher->MIRV Launcher|Multi-Rocket Launcher|Sanguinators||
|8|Thunderbolt->Plasmagun(AD)|Plasmagun(Rogue)|Flak Cannon||
|9|Crossbow->Asgard Arbalest|Laser Cannon|Chain Lightning Gun||
|0|Wand|Mjolnir|Gungnir||