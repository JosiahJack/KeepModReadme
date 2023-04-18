---
id: y3svp82bm5u5sfu4brr9y80
title: Logic and Entity State System
desc: ''
updated: 1657650198658
created: 1657650191656
---
There are various invisible entities that control different aspects of the game and handle triggering and using the functions of other entities.  These are useful in many situations and allow for a large amount of flexibility in setups and creating special events, large and small.

# General Logic Entities

#### `info_player_start`
Starting point for the player in single player games.  Also used as one of the spawn points for coop.  Placing more than one will create a warning, should only ever be 1, which is why we have...

#### `info_player_startdev`
Forced to use and only used as starting point if `developer` is 1.  Useful for immediately starting in area of the map for testing without having to noclip over there.

#### `info_player_coop`
Starting point for coop players.  Coop players will start here first, if present, before picking the `info_player_start` instead.  `spawnflags` 64 will cause this to start off.  Can be enabled or disabled using the entity state system (see below).

#### `info_player_start2`
Secondary starting point for the player in single player games.  Player will spawn here if serverflag bitmask value 16, 32, or 64 is true or if player had all 4 runes in previous map.

#### `info_player_coop2`
Secondary starting point for the player in coop games.  Player will spawn here if serverflag bitmask value 16, 32, or 64 is true or if player had all 4 runes in previous map.  Coop players will start here first, if present and met the above conditions, before picking the `info_player_start2` instead.  `spawnflags` 64 will cause this to start off.  Can be enabled or disabled using the entity state system (see below).


#### `info_player_deathmatch `
Secondary starting point for the player in deathmatch games.  You should sprinkle at least 4 of these around every level.  `spawnflags` 64 will cause this to start off.  Can be enabled or disabled using the entity state system (see below).

#### `info_skyroom`
Skyroom camera for QSS/FTE engines for implementation of 3D skyboxes.  Automatically sets worldspawn's `_skyroom` value to the origin vector of the location of this entity.  Overrides worldspawn.  Only 1 should be used.  If using multiple, the last one placed in the map editor will be used.

#### `info_intermission `
This is used to display a view of the level after completing it.  Typically shows off one of the best viewing angles of an area of the map.  Best if used to showcase memorable setpieces.  Can be and highly recommended to be more than one.  Clicking the mouse switches to the next camera.  Pressing jump will exit the level.
|Key|Type|Default|Description|
|---|---|---|---|
|target|string||Used to trigger actions upon first switching to this intermission camera.  Happens once only.|
|mangle|string|`0 0 0`|Viewing angle for the intermission camera. Set as a vector like `p y r` (pitch yaw roll).  Pitch is up and down, negative to look up, positive to look down.  Yaw is the rotation left and right and is same as when setting monster facing direction (e.g. 90 is north, 270 south etc.). Roll is if you want to look at something sideways, positive to tilt your head to the right, negative to tilt your head to the left, 180 to flip upside-down.|
|fog_density|float|0|Set to change the fog density when switching to this intermission|
|fog_colour|vector|`0.1 0.1 0.1`|Set to change the fog color when switching to this intermission, set like `r g b` (red green blue) with value between 0 and 1.0.|
|speed|float|2|Total time to transition from previous fog settings to this intermission's fog settings.|

#### `info_skullwiz_destination `
Used by `monster_skullwiz` when phasing to teleport to while invisible.  Set `target` and `targetname` to other `info_skullwiz_destination`'s in order to have the `monster_skullwiz` teleport to them in a set sequence.
|Key|Type|Default|Description|
|---|---|---|---|
|target|string||Name of the next `info_skullwiz_destination ` in the chain.|
|distance|integer|192|The player must be at least this distance away from this point before teleporting to it.|

#### `info_overlord_destination `
Used by `monster_super_wrath` to teleport to when randomly teleporting away.  Overlord will teleport to a random one of these points.  Set multiple if desired.

#### `info_morph_destination`
Used by `monster_morph` to teleport to when randomly teleporting away.  Guardian will teleport to a random one of these points.  Set multiple if desired.

#### `info_target`
Useful to set a position for an object to move towards, such as a door or button.

#### `info_home`
Useful to set a starting position for a `func_qrobot`.

#### `info_null`
Useful to set a spotlight target.  Removed on game start.

#### `info_notnull`
Does nothing...but can!  Useful for various map hacks by giving it various code functions to `think`.
|Key|Type|Description|
|---|---|---|
|targetname|string|Name of this entity for use by others either as reference or to trigger the `use` function on this entity.|
|use|string|Name of the function to execute when this is targeted. Specify as it is found in the qc code, for instance `func_door_use`, without quotes. Requires a `targetname`|
|think|string|Name of the function that will execute after `nextthink` seconds have elapsed after map start. Specify as it is found in the qc code, for instance `func_door_use`, without quotes. Requires a `targetname`|
|touch|string|Name of the function that will execute whenever something else registers a touch by physics to this entity. Specify as it is found in the qc code, for instance `func_door_trigger_touch`, without quotes. Requires a `targetname`|
|nextthink|float|Amount of time in seconds after map start before executing the `think` function.  `think` must be set for this to affect anything.|
|<field>|<any>|Set any desired fields by adding them manually.  This could be any supported data field defined by the qc code and relevant to the other functions you've set on this hack.  For instance you could set `wait`, `delay`, `count`, `dmg` etc.|

#### `info_command`
Triggerable console command.  Use with caution!  Be nice!!
|Key|Type|Default|Description|
|---|---|---|---|
|targetname|string||Name of this entity.  Required.|
|message|string||This is the actual command to pass to the console.  Works as if the player had typed the command into the console once this entity is targeted.|
|spawnflags|integer|8|No auto newline.  Prevents automatically adding `\n` which would then execute the command.  Useful for sending partial entries to the console one after the other using multiple `info_command` entities.  This makes this `info_command`'s message not execute until another `info_command` is triggered that does not have this spawnflag set.|

#### `info_command_server`
Same as `info_command` but gets sent to all players and not just the current player on this PC.  Useful for coop or deathmatch.
|Key|Type|Default|Description|
|---|---|---|---|
|targetname|string||Name of this entity.  Required.|
|message|string||This is the actual command to pass to the console.  Works as if the player had typed the command into the console once this entity is targeted.|
|spawnflags|integer|2|Activator Only.  Turns this back into an `info_command`.|
|||8|No auto newline.  Prevents automatically adding `\n` which would then execute the command.  Useful for sending partial entries to the console one after the other using multiple `info_command` entities.  This makes this `info_command`'s message not execute until another `info_command` is triggered that does not have this spawnflag set.|

#### `info_command_spawn`
Same as `info_command_server`, but automatically carries out when the map starts.
|Key|Type|Default|Description|
|---|---|---|---|
|targetname|string||Name of this entity.  Required.|
|message|string||This is the actual command to pass to the console.  Works as if the player had typed the command into the console once this entity is targeted.|
|spawnflags|integer|8|No auto newline.  Prevents automatically adding `\n` which would then execute the command.  Useful for sending partial entries to the console one after the other using multiple `info_command` entities.  This makes this `info_command`'s message not execute until another `info_command` is triggered that does not have this spawnflag set.|
|||16|Resend on load.  Makes this execute again anytime the player loads from a save/quicksave.|

#### `info_bomb`
Used as the center point when activating the bomb effect.

#### `info_effect_pulse `
Projectile light effect.  Laucnhes an invisible projectile that has `effects` set to carry a light with it.  Useful for added dynamic lighting.
|Key|Type|Default|Description|
|---|---|---|---|
|speed|float|400|How fast it should move|
|delay|float|0.1|Delay in seconds before it sends out a pulse|
|wait|float|0.1|Interval time between sending another pulse.  Set to -1 for only once, but needs `targetname` set for triggering if so.|

#### `trigger_relay`

# Entity State System
When the Arcane Dimensions mod came out, it introduced a novel idea for handling the enabling and disabling of various entities, including triggers.  Quoting its description here:

`When Quake first came out there were strict limitations on how many entities
could exist and be active at the same time. The quick fix solution to this
problem was to use the ``killtarget`` key so that entities could be removed. 
This was a very powerful feature with very few restrictions on what it 
could affect or destroy at the same time.`

`The idea of the entity state system is to create a way to safely switch
entities on, off or have then temporarily disabled. This will help prevent
situations where entity chains are broken or strange errors occur because
the touch function does not have an entity anymore.`

`The entity state is a new key on entities which is designed to work in a
passive mode until it is activated. All the entities listed below have a
default value so that any existing map will still work as before.`

`There are two methods for changing the entity state and the first method
is an extra key on ``trigger`` entities (_once, _multi, _relay etc)`
  
`The second method is via a brand new set of entities which can affect 
multiple targets at once and are much easier (visually) to see what is
going on because most editors draw target lines.`

## Entity State Information Table
|Estate Action|Estate Condition Result|Description of Action|Description of State|
|---|---|---|---|
|Disable|DISABLED|Puts entity into DISABLED state.|Blocks any targeted ability or entity functionality and turns off any visual aids like animated textures.|
|Turn Off|OFF|Puts into OFF state|Block all of the designed functionality and hide the entity entirely from interaction with the player.|
|Enable|ON|Puts into ON state|(Default) Allows the entity to work as designed, be targeted and physically exist as per its setup|