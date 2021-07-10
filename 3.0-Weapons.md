There are numerous weapons available.  Below is a chart listing each weapon with its stats.  The impulse value given below is the internal number used by the code to switch to that weapon; this can be used via the console by entering `impulse ###` console command and replacing \### with the desired number from below to switch directly to that weapon without the need for pressing a slot's keyboard key multiple times.  Also possible to add new keybinds for specific weapons by adding `"bind" "keyhere" "impulse ###"` in your config.cfg file and changing "keyhere" to desired keyboard key.  The weapon has to have been picked up first.

Further down is a chart listing the keyboard key defaults for each weapon 'slot' and the weapons in that slot.  Pressing the keyboard key will first switch to the first weapon in the slot that the player has in inventory; further presses of the same key will cycle through the weapons in the slot.

Some weapons are _override_ weapons.  An override will fully replace a weapon in its slot, for instance the Shadow Axe replaces the standard Axe.  Overrides are not given by CheatCommand, refer to [Cheat Codes](https://github.com/JosiahJack/KeepModReadme/wiki/9.0-Cheat-Codes) for more info.

## Weapon Info

|Name|Entity|Source Mod|Damage|Description|Ammo|Impulse|Tome of Power Effects|
|----|------|----------|------|-----------|----|-------|-----|
|Axe|<sub>weapon_axe</sub>|Keep|20|Weakest weapon.  Simple axe with a few different swing angles.  Possible to change from ID1 axe model to AD axe by setting `useold_axe` to 1 in a level's worldspawn.|None|1||
|Laser Blaster|<sub>weapon_blaster</sub>|Drake|24|Replaces shotgun on pickup.  Does same damage as shotgun but shoots a laser projectile.  Lasers ricochet off walls up to 3 times but lose 10% damage with each ricochet with a 15% chance of not ricocheting.|Shells|2||
|Chain Lightning Gun|<sub>weapon_chain_lightning</sub>|Zerstorer|15-30 * n where n = number of enemies within 350 units of hit enemy|Fires large shaft of lightning that splits between nearby enemies, damaging all at once, but uses cells very rapidly.  Discharging in the water drains all cells and causes damage in a 35 * cells radius with 35 * cells damage.|Cells|9||
|Crossbow|<sub>weapon_crossbow</sub>|ITS|100, 110|Fires either normal bolts or poison bolts.  Poison bolts cause poison debuff and do more damage.  Excellent stealth weapon since enemies can be shot without angering them.|Bolts, Poison|178||
|Flak Cannon|<sub>weapon_flak</sub>|AoA|125 explosion damage, 30 shrapnel @ 5 dmg each|Launches an arcing explosive projectile. Impact causes radius explosion damage, and launches 30 pieces of shrapnel in all diractions.|8 Nails and 2 Rockets|8|Hitscan instead of projectile|
|Grenade Launcher|<sub>weapon_grenadelauncher</sub>|ID1|100-120(120)|Lobs an explosive that explodes in 2.5 seconds|Rockets|6||
|Gungnir|<sub>weapon_gungnir</sub>|AoA|Melee: 40; Projectile: 40; Dive: 60-120 in 350 radius|Melee works without ammo, 1 voidshard adds the projectile, and the dive attack does radius damage. Attacking underwater provides a significant speed boost forward.|Void Shards|77|Summons the Eye of Odin, a vortex which pulls in projectiles, monsters, and players, and strikes them with lightning.|
|Elemental Tome|weapon_ice|AoA|24 Ice projectiles @ 2 dmg; 40 direct lightning dmg, forks to 30 lightning dmg for up to 5 targets. |Attack combo launches 24 Ice projectiles, followed by direct lightning damage, and subsequent forked lightning.|Elemental Mana|2|Tome'd forked lightning can target up to 10 targets. Adds boulder projectile to end of combo (120 direct dmg)|
|Laser Cannon|weapon_laser_gun|Hipnotic|18|Fires lasers in an alternating pattern of 2 blasts at once then 1 blast.  Lasers ricochet off walls up to 3 times but lose 10% damage with each ricochet with a 15% chance of not ricocheting.  Very rapid fire.|Cells|9||
|Lava Nailgun|<sub>weapon_lava_nailgun</sub>|Rogue, Keep|15|Lava variant of the Nailgun.  Fires red hot nails that pierce armor.  Cannot hurt Hephaestus (monster_lava_man).  Only does 9 damage against players.  Added weapon pickup for Keep mod; in rogue you would be given this once lava nails were picked up and nailgun was obtained.|Lava Nails|60||
|Lava Super Nailgun|<sub>weapon_lava _super_nailgun</sub>|Rogue, Keep|30|Lava variant of the Perforator.  Fires red hot nails that pierce armor.  Cannot hurt Hephaestus (monster_lava_man).  Only does 18 damage against players.  Added weapon pickup for Keep mod; in rogue you would be given this once lava nails were picked up and perforator was obtained, uses 2 ammo per shot.|Lava Nails|61|
|Thunderbolt|weapon_lightning|ID1|30 per 0.1 seconds|Fires a continuous stream of lightning.  Discharging in the water causes damage in a 35 * cells radius with 35 * cells damage, then drains cells to 0|Cells|8||
|Blood Mace|weapon_mace|AoA|45|Each hit recovers 5 HP. If on ground, first attack the player will lunge forward.|None|1|Gibs zombies. Adds third attack, area of effect health drain.|
|Mjolnir's Hammer|weapon_mjolnir|Hipnotic|50, 70 to zombies, Lightning is 80 initially, then 30 every 0.2s|More powerful melee weapon that does powerful blunt force but also shoots out lightning at any nearby enemies within 350 units when hit on the ground, uses and needs 15 ammo for ground hit's lightning.  Lightning continues to hurt its target for lifetime of 0.8s or until the target reaches 0 health or moves out of range of 350 units of ground impact point.  Firing in water has the same discharge effect as the lightning gun damaging everything in a 35 * cells radius with 35 * cells damage, then drains cells to 0.|None/Cells if ground hit|77|Uses 30 cells on ground hit to generate lightning ball that zaps **all** enemies within a 256 unit radius.  Each lightning beam shoots through up 3 enemies in a line.  Lightning will always gib zombies.  Causes (40) burst) damage when lightning orb explodes after 1.9secs.  Works underwater without hurting the user.|
|Multi-Grenade Launcher|<sub>weapon_multi_grenade</sub>|Rogue|(120) Main grenade if impact, (90) Mini grenades|Fires a yellow grenade that splits into 5 mini-grenades that then explode soon after.  If main grenade hits enemy or player before splitting, it does normal grenade damage.|Multi-Rockets|62||
|Multi-Rocket Launcher|<sub>weapon_multi_rocket</sub>|Rogue|60-75(75) each|Fires 4 rockets at once in a horizontal spread pattern.  Rockets semi-home to nearby monsters.|Multi-Rockets|63||
|Nailgun|weapon_nailgun|ID1|9|Fires nails out rapidly alternating from one barrel to the other.|Nails|4||
|Plasma Gun|<sub>weapon_plasmalightning</sub>|Rogue|80-100(70)|Fires a lightning ball that explodes on impact.  Lightning ball then shoots out lightning at any nearby enemies if there are some within a 320 unit range.|Plasma|64||
|Proximity Gun|<sub>weapon_proximity_gun</sub>|Hipnotic|(95)|Fires a red mine that sticks to walls.  The mine explodes only when something moves near it.|Rockets|176||
|Rapier|weapon_rapier|AoA|35 melee. 25 Projectile (with ammo).|Three quick melee attacks. Ammo adds a projectile that attacks 3 times. Bonus dmg against Shamblers.|Blood Crystals|4|Adds spin attack to rapier projectile, 120 radius damage.|
|Rocket Launcher|<sub>weapon_rocketlauncher</sub>|ID1|100-120(120)|Fires a rocket that explodes on impact.|Rockets|7||
|Sanguinators|<sub>weapon_sanguinators</sub>|AoA|25 dmg, hitscan.|Attacks cause blood to seek player, recovering health.|Blood Crystals|7|Bloodorbs become explosive projectiles that launch upon attack.|
|Fire Scimitar|weapon_scimitar|AoA|Melee: 40; Projectile: 75-150 in radius.|3-hit melee combo. First attack launches player forward. Third attack adds a projectile if you have ammo.|Elemental Mana|3|Much stronger dash, 1 projectile per attack.|
|Shotgun|weapon_shotgun|AD|4-24|Fires a fairly tight burst of 6 tracer pellets up to long distances at spread pattern of '0.04 0.04 0'.  Spread is '0.01 0.01 0' with Sharpshooter powerup.  Uses hitscan unless projectiles are enabled in [settings](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings) `temp1`. One of the weakest weapons in the game.  Note: AD fired 1 extra tracer for projectile version, changed to be matched with standard hitscan version.|Shells|2||
|Perforator|<sub>weapon_supernailgun</sub>|ID1|18|Fires nails rapidly for high damage,uses 2 ammo per shot.|Nails|5||
|Double-barreled Shotgun|<sub>weapon_supershotgun</sub>|ID1|4-56|Fires a double burst of 14 pellets in a wide spread of '0.14 0.08 0'.  Spread is '0.04 0.04 0' with Sharpshooter powerup.  Uses hitscan unless projectiles are enabled in [settings](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings) `temp1`.  Uses 2 ammo per shot.|Shells|3||
|Shadow Axe|<sub>weapon_upgrade_axe</sub>|AD|35|Replaces the normal axe.  Does more damage and is capable of gibbing corpses, notably useful for killing downed or lying zombies.|None|1||
|Plasma Gun|<sub>weapon_upgrade_lg</sub>|AD|45(20)|Replaces the lightning gun.  Fires a rapid burst of small blue plasma balls.  The plasma balls explode on impact causing splash damage.|Cells|8||
|Widowmaker|<sub>weapon_upgrade_ssg</sub>|AD|4-84|Replaces the Double-barreled Shotgun.  Fires 21 tracer pellets in a wide spread of '0.14 0.08 0'.  Spread is '0.04 0.04 0' with Sharpshooter powerup.  Uses hitscan unless projectiles are enabled in [settings](https://github.com/JosiahJack/KeepModReadme/wiki/8.0-Config-and-Settings) `temp1`.  Uses 3 ammo per shot.|Shells|3||
|Void Staff|weapon_voidstaff|AoA|45 on hit; 50-100 on detonate.|Launches Void shards, which can be detonated for radius damage. Projectiles accelerate upwards.|Void Shards|5|SErratic projectiles, increased damage.|
|Magic Wand|weapon_wand|Drake|16 per spark, 64 for full charge, 10-35(5 per spark plus 5 bonus on outer 2) if tome of power|Fires a number of hitscan spark effects equal to its currently charged ammo which is special mana only for itself, in a tight fan shape at a distance of 600 max. When mana is fully charged, center spark is a small spark explosion with knockback, recharges ammo up to 4 at all times, 1 recharge every 0.4s.|Mana Pool, no pickup needed|77|Mana is increased to 5 and never depletes until tome times out so every shot fires all 5 sparks.  Fires further and a fan of 5 sparks with death knight tracers on the outer edge 2 sparks for added visibility and bonus 5 damage each|

.

## Weapon Slots
|Keyboard Key|Slot's Weapon 1|Slot's Weapon 2|Slot's Weapon 3|Slot's Weapon 4|
|---|---|---|---|---|
|-|Example->Override1->Override2|Example|Example|Unused|
|1|Axe->Shadow Axe->Chainsaw|Grapple|Mace||
|2|Shotgun->Blaster|Elemental Tome(Ice)|||
|3|Double-barreledShotgun->Widowmaker->Shotcycler->QuadShotgun|Scimitar|||
|4|Nailgun|LavaNailgun|Rapier||
|5|Perforator|LavaSuperNailgun|VoidStaff||
|6|Grenade Launcher|Proximity Gun|Multi-Grenade Launcher||
|7|Rocket Launcher|Multi-Rocket Launcher|Sanguinators||
|8|Thunderbolt->Plasmagun(AD)|Plasmagun(Rogue)|Flak Cannon||
|9|Crossbow|Laser Cannon|Chain Lightning Gun||
|0|Wand|Mjolnir|Gungnir||