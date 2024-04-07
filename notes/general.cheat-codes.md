---
id: npfnt7xdwzmfzdrt59fbdue
title: Cheat Codes
desc: ''
updated: 1657647884875
created: 1657647882521
---
With great power comes great responsibility.  Use at your own risk!  Most of these will make the game not fun or unplayable with potential to break progression.  Some cheats are super useful for development though.  Some things listed here blur the line between cheat and feature such as `developer 1` and its host of "features".

|Cheat Console Command|Argument(s) (if any)|Description|
|---|---|---|
|developer|1|Enables `Developer Mode` in the engine.  Keep uses the many developer assistance additions added by AD: Arrows are placed on path_corners, Delay(64) spawn monsters and invisible info entities are marked with 3D diamond markers, entities with setup errors are marked with yellow diamonds, numerous messages are logged in the console about the level settings and any errors found in setup.|
|god||Toggles on/off with each use.  Player becomes invincible and pentagram protection sound plays when damage would have been dealt.|
|noclip||Toggles on/off with each use. Player becomes nonsolid and unaffected by gravity.  Used for flying through walls and outside the level.  Super helpful to skip sections to spotcheck areas of a level during testing of a map during development or to take screenshots from outside the level looking in.|
|notarget||Toggles on/off with each use.  Makes player invisible to enemies and triggers.  AD also prevented item pickup but I have reenabled the old vanilla behavior and let players still pick things up for testing.  Noclip can be used if you want to avoid picking something up during testing.|
|fly||Toggles on/off with each use.  Disables gravity for the player.  Player still collides with everything.  Useful flying through to test collisions in anticipation of enemy knockback or rocket jumping.|
|impulse|1 through 255|Used for switching weapons on weapon slots or direct to weapons within slots.  Also used with various numbers for special cheats.  See separate chart below.|

## Impulse Cheats

|Impulse Number|Cheat Description|
|---|---|
|9|CheatCommand. Grants all weapons excluding overrides (See Overrides here: [[weapons]]), and full ammo.|
|13|Legacy CheatCommand.  Kept from the age old days of early Keep when impulse 9 was assigned to the laser cannon prior to knowing you could bind the 9 key to a separate impulse.|
|145|Start intermission screen|
|182|Display Secrets.  Take a noclip tour through the map to the location of each secret trigger.  Some secret triggers are not touchable and will be placed by the mapper at their discretion (usually nearby but could be anywhere).|
|211|KillRay.  Initial mode is Instakill.  Anytime ths player attacks with this on will instantly kill the monster hitscanned in front of the player.  Activate again for Instagib mode to gib monsters when killed.  Fires every 1 second.  Consumes no ammo and does not fire your actual weapon.  Powered by lightning from on high. (NOTE: Intended for testing monsters and verifying gibs match skinned variants.... and for Qmaster's new Instakill speedrun type for those paying attention)|
|239|Jumpboots.  Grant yourself double jump.|
|249|CheatCommand. Gives all runes, full ammo of every type, full red armor, and all weapons except overrides.  Vanilla used `impulse 9` for this.|
