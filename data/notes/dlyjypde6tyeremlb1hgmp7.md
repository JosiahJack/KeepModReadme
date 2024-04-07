
There are numerous configurable settings and keybinds specific to the Keep mod, with most deriving from Arcane Dimensions (AD)'s way of doing things.

# Settings
The various mod settings are specified in the `keep/quake.rc` file.  All of the MOD features can be changed before loading by editing this file in a text editor.

### `temp1`
* **Type:** integer used as bitmask
* **Description:** Set by adding desired active values together.  Defaults to 132096 which is equal to 131072 + 1024 for particles on by default and disable projectile shotguns by default.  Specified in quake.rc like so:

`temp1 132096`

|Bit Value|Description|
|---|---|
|1|Unused|
|2|Unused|
|4|Unused|
|...|...|
|128|Unused|
|256|Turn OFF item offset (designed for new maps)|
|512|Turn ON sprite particles for any engine (default OFF)|
|1024|Turn ON particle system (default OFF)|
|2048|Turn OFF Dev Helpers (mark/arrows)|
|4096|Upgrade existing Axe, +75% dmg, gib zombies|
|8192|Upgrade SSG weapon pickups, +50% dmg, uses 3 shells|
|16384|Upgrade LG weapon pickups, Direct + Splashdamage|
|65536| Unused
|131072|Turn OFF Shotgun projectiles
|262144|Turn OFF Shotgun casings
|524288|Turn OFF Z aware monsters
|1048576|Turn OFF Enemy/player footsteps|
|2097152|Turn OFF AI path corner extra info|
|4194304|Turn OFF Monster liquid damage|

### Impulse Command Settings
The following are rarely needed special options done by entering `impulse #` in the console and changing # for one of the following numbers.  Some of these can be changed via console variables or temp1 as well.  This allows quicker in-game testing to see if a setting suits you or not.  These will display a console message explaining what happened.

|Impulse|Description|Default State|
|---|---|---|
|100|Toggle auto aim on/off|off|
|105|Toggle projectile size big/small (subtle)|big|
|110|Toggle z-aware arc projectile aiming on enemies on/off|on|
|115|Toggle pixel mode GL_LINEAR_MIPMAP_LINEAR (blurry mess)/GL_NEAREST_MIPMAP_LINEAR(crunchy pixels)|GL_NEAREST_MIPMAP_LINEAR|
|120|Toggle footstep noises on/off|
|125|Toggle liquid damages monsters (only affects certain monsters such as zombies) on/off|on|
|130|Toggle shotgun method projectile/hitscan (classic)|hitscan|
|135|Toggle shotgun drop shell casings on/off|on|
|137|Toggle missile homing (only for certain monsters such as monster_army_rocket) on/off|on|
|140|Display mod version|**[INFO]** Keep Mod, version 0.`##`|
|142|Display player position, useful for finding good intermission coordinates, same as `viewpos` + `setview` console commands|**[INFO]** Org (`# # #`)|
|150|Toggle dropping of artifacts in coop on/off/|on|
|152|Toggle coop weapons stay/remove-on-pickup|stay|
|154|Toggle coop health stay/remove-on-pickup|remove-on-pickup|
|155|Toggle coop ammo stay/remove-on-pickup|remove-on-pickup|
|158|Toggle coop powerups stay/remove-on-pickup|remove-on-pickup|
|160|Toggle weather, engine effects only, does not affect rainclouds, drips, and emitters|on|
|162|Cycle max player health through one of 25, 50, 75, 100|100, unless Evil Mode active|
|164|Cycle max player health through one of 50, 100|100, unless Evil Mode active|
|170|Toggle corpse and gib fade on/off (classic)|on
|178|Cycle HUD types through Standard 3-Bar Middle, Sides, Blank, Doom Classic, Quake Champions, Wide Single Row,Crosshair, Blank, Blank|Standard|
|220|Display mod settings||
|100|Toggle auto aim|
|100|Toggle auto aim|
|100|Toggle auto aim|

# Config
These files are used for specific engine confirguration and keybind settings:
* `keep/default.cfg`- Default Keybinds
* `keep/config.cfg` - Override keybinds.
* `keep/autoexec.cfg` (if present, manually user created) - Override Engine Console Commands

The default keybinds for Keep are in the `keep/default.cfg` file and are overriden by the user in-game.  The override is then automatically saved by the engine to `keep/config.cfg`.  You can modify this directly in any text editor, but please do not change default.cfg in case you need it as a backup.

These binds are specific to Keep, mostly for weapons:

|Bind Command|Description|
|---|---|
|"bind" "0" "impulse 77"|Cycle through weapons in weapon slot 0|
|"bind" "9" "impulse 9"|Cycle through weapons in weapon slot 9|
|"bind" "l" "impulse 59"|Toggle Power Shield powerup on and off, if collected.  Protects from damage by using cells ammo on impact|
|"bind" "k" "impulse 58"|Activate stored Quad powerup(Berserk Armor)|
|"bind" "j" "impulse 57"|Activate stored Invisibility powerup(Spirit Shroud)|
|"bind" "h" "impulse 56"|Activate stored Invulnerability powerup(Dragonhide Armor)|
|bind "e" "impulse 159"|Use key.  Used by purchase triggers|
|bind "b" "impulse 143"|Display coins collected in centerprint|
|bind "n" "impulse 144"|Display bones/gibs collected in centerprint (Versus mutliplayer only, and only for players on the monster team)|
|bind "g" "impulse 146"|Toggle flashlight on and off, if collected|