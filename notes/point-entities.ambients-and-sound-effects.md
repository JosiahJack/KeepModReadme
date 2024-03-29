---
id: 2k24uzhmr4ibcm0cbuxnofv
title: Ambients and Sound Effects
desc: ''
updated: 1681958422034
created: 1657650227861
---
There are numerous looped sound effects, called ambients.  Most of them are the same and simply change the default sound file that is played.  Alternatively, `ambient_custom_looping` can be used in place of any of these so long as you know what sound file to specify.

Some sounds are looping, others are non-looped sounds played via trigger.  Some ambients play non-looped sounds that get played at randomized intervals.  Certain specialized ambients will play multiple different randomly picked non-looped sounds at randomized intervals; these are typically named `ambient_custom_` at the beginning of their name, such as `ambient_custom_wind` or `ambient_custom_wood`.  These features are extremely popular and have many different various implementations in almost all mods.

# Standard Ambient Noises
These are simply static location, looping sound effects that play the same sound file over and over indefinitely.  These can have their volume and falloff adjusted at map start but cannot be changed once the level has finished starting.

### All of the following entities in this table have these common attributes:
`spawnflags` - Set 8 Global to play this ambient sound everywhere all the time.  Not recommended unless for small maps in between larger levels.
`volume` - Set to a value from 0 to 1, 0 is silent, 1 is full volume. 0.5 is default for the ambients in the table below.
`speed` - Set to one of the following to specify the falloff attenuation.  This affects the distance the sound will be heard.
> * 0: Plays everywhere (same as setting `spawnflags` 8 above)
> * 1: Default
> * 2: Idle (not as noticeable)
> * 3: Static (bit shorter)
> * 4: Quiet (small radius, still barely audible at longer distances but fades out quicker)

.

|Entity Name|Sound File Used|Description|
|---|---|---|
|`ambient_bublfals`|ambience/bublfals.wav|Bubbly waterfall|
|`ambient_comp_hum`|ambience/comp1.wav|Computer beeping and fan noises, subtle|
|`ambient_drain`|ambience/drain.wav|Drain gargling|
|`ambient_drip`|ambience/drip1.wav|Ultra-classic echoey drip noise in a cave or on pipes or wherever|
|`ambient_drone`|ambience/drone6.wav|Engine/machinery sound, typically used on slipgates|
|`ambient_eerie`|ambience/rych1.wav|Eerie humming|
|`ambient_factory`|ambience/factory.wav|Factory type machinery noises|
|`ambient_fan_blowing`|ambience/fanblow.wav|Fan blowing|
|`ambient_flies`|ambience/bugs.wav|Nehahra flies buzzing|
|`ambient_flouro_buzz`|ambience/buzz1.wav|Fluorescent Light Buzzing Noise with pauses, yes fl**o**uro is a typo [sic]|
|`ambient_flys`|misc/flys.wav|Hipnotic flies buzzing|
|`ambient_grinder`|ambience/grinder.wav|Grinding churning noise|
|`ambient_hevifals`|ambience/hevifals.wav|Heavy waterfall|
|`ambient_highwind`|ambience/highwind.wav|Wind noise|
|`ambient_hum1`or `ambient_teleport`|ambience/hum1.wav|Teleporter noise, the breathy noise used by `trigger_teleport`|
|`ambient_humming`|ambience/humming.wav|`spawnflags` 4 changes to Nehahra's sound effect (ambience/maydn.wav) that it used on its `ambient_humming` entities.  Provided for completeness.|
|`ambient_lapping`|ambience/wat_amb.wav|Gentle water noise, useful for edges of pools or by dock posts.|
|`ambient_lapping2`|ambience/wat_cave.wav|Similar to lapping but more echoey as if in a cave.|
|`ambient_lavagurg`|ambience/lavagurg.wav|Lava Gurgling Noise, deeper pitched than water gurgling, sounds viscous|
|`ambient_light_buzz`|ambience/fl_hum1.wav|Steady fluorescent Light Buzzing Noise|
|`ambient_machines`|ambience/begths.wav|Loud Machines|
|`ambient_nehum`|ambience/filt.wav|Humming|
|`ambient_rain`|ambience/rain.wav|Change `count` to 0 for Rain Runoff (default), 1 for Steady Rain (ambience/rain3.wav), or 2 for Heavy Rain (ambience/rain2.wav).  Uses ambience/rain3.wav if count is higher than 2 or lower than 0.|
|`ambient_riftpower`|ambience/riftpowr.wav|Riftpower|
|`ambient_running_lava`|ambience/runlava.wav|Lava river|
|`ambient_running_water`|ambience/runwater.wav|Water river|
|`ambient_rushing`|ambience/rushing.wav|Whirring|
|`ambient_sizzle`|ambience/amsizl.wav|Cooking sizzle|
|`ambient_stargate_hum`|ambience/sgatehum.wav|Stargate humming|
|`ambient_suck_wind`|ambience/suck1.wav|Classic sky wind noise used outdoors|
|`ambient_swamp1`|ambience/swamp1.wav|Frogs croaking|
|`ambient_swamp2`|ambience/swamp2.wav|Frogs croaking B|
|`ambient_swamp3`|ambience/swamp3.wav|Frogs croaking C|
|`ambient_teeth`|ambience/teeth.wav|Teeth chomp chomp chomp|
|`ambient_thrum`|ambience/thrum.wav|Thrum|
|`ambient_thunder`|ambience/thunder1.wav|Constant Thundering|
|`ambient_waterfall`|ambience/waterfal.wav|Waterfall|
|`ambient_water_fall`|ambience/wat_fall.wav|Waterfall B|
|`ambient_whnoise`|ambience/whn.wav|Weird Humming|
|`ambient_zzxzz`|ambience/flash.wav|Strange Machinery|

# Specialty Ambient Noises

### `ambient_custom_chime`
Randomly plays chime sounds at randomized intervals.  Can be enabled or
disabled using the [[point-entities.logic-and-entity-state-system]].
|Key|Type|Default|Description|
|---|---|---|---|
|`noise`|string|ad171/ambience/chimes.wav|Set to the sound file to play.  Do not include quotation marks.|
|`wait`|integer|10|Maximum interval time.|
|`delay`|integer|10|Minimum interval time.|
|`waitmin`|integer|10-20|Initial minimum interval time before first playing sound after enabling.|
|`waitmin2`|boolean (0 or 1)|-1|Set to 1 to prevent from turning off on subsequent targeting.|
|`spawnflags`|2|0|Play only once when targeted|
||64|0|Starts off.  Must have `targetname` set!|

.

### `ambient_custom_loop` or `ambient_generalpurpose` or `ambient_custom_water`
Useful to set a custom looping ambient noise.
|Key|Type|Default|Description|
|---|---|---|---|
|`noise`|string||Set to the sound file to play, for example `ambient/demonwind.wav`.  Do not include quotation marks.|
|`volume`|integer|1|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|

.

### `ambient_custom_rain`
Plays one of 3 different rain types looping.  **Must** be targeted to start.
|Key|Type|Default|Description|
|---|---|---|---|
|`count`|integer|0|Default Rain|
|||1|Fast Dripping|
|||2|Downpour|
|`volume`|integer|1|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|
|`impulse`|integer|0|The sound channel to use; must be in the range 0 - 7.|
|`speed`|integer|1|Set normal falloff attenuation.  This affects the distance the sound will be heard.|
|||0|Plays everwhere|
|||2|Idle (not as noticeable)|
|||3|Static (bit shorter)|
|||4|Quiet (small radius, still barely audible at longer distances but fades out quicker)|
|`delay`|integer|2|Minimum interval time.|
|`spawnflags`|integer|64|Always starts off.  Cannot be changed.|

Sounds to play:
> * ad171/ambience/rain1_nl.wav
> * ad171/ambience/rain2_nl.wav

.

### `ambient_custom_rumble`
Randomly plays low rumbling sounds at randomized intervals.  Can be enabled or disabled using the [[point-entities.logic-and-entity-state-system]].
|Key|Type|Default|Description|
|---|---|---|---|
|`count`|integer|0|Pick different sound to start random seed from, 0 through 2|
|`volume`|integer|0.5|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|
|`speed`|integer|1|Set normal falloff attenuation.  This affects the distance the sound will be heard.|
|||0|Plays everwhere|
|||2|Idle (not as noticeable)|
|||3|Static (bit shorter)|
|||4|Quiet (small radius, still barely audible at longer distances but fades out quicker)|
|`wait`|integer|20|Maximum interval time.|
|`delay`|integer|20|Minimum interval time.|
|`waitmin`|integer|6-12|Initial start time.|
|`spawnflags`|2|0|Play only once when targeted|
||64|0|Starts off.  Must have `targetname` set!|

Sounds to play:
> * ad171/ambience/rumble1.wav
> * ad171/ambience/rumble2.wav
> * ad171/ambience/rumble3.wav

.

### `ambient_custom_sound `
Plays one of 3 different sounds at randomized interval.  Can be enabled or disabled using the [[point-entities.logic-and-entity-state-system]].
|Key|Type|Default|Description|
|---|---|---|---|
|`target`|string|2|If set, will run targets when making noise, useful for lights, sparks, etc.|
|`noise`|string||Set to the 1st sound file to play, for example `ambient/demonwind.wav`.  Do not include quotation marks.|
|`noise1`|string||Set to the 1st sound file to play, for example `ambient/demonwind.wav`.  Do not include quotation marks.|
|`noise2`|string||Set to the 1st sound file to play, for example `ambient/demonwind.wav`.  Do not include quotation marks.|
|`volume`|integer|1|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|
|`impulse`|integer|0|The sound channel to use; must be in the range 0 - 7.|
|`speed`|integer|1|Set normal falloff attenuation.  This affects the distance the sound will be heard.|
|||0|Plays everwhere|
|||2|Idle (not as noticeable)|
|||3|Static (bit shorter)|
|||4|Quiet (small radius, still barely audible at longer distances but fades out quicker)|
|`wait`|integer|20|Maximum interval time.|
|`delay`|integer|2|Minimum interval time.|
|`waitmin`|integer|2|Initial minimum interval time before first playing sound after enabling.|
|`waitmin2`|boolean (0 or 1)|2|Set to 1 to prevent from turning off on subsequent targeting.|
|`spawnflags`|2|0|Play only once when targeted|
||64|0|Starts off.  Must have `targetname` set!|

.

### `ambient_custom_wind`
Randomly plays wind gust sounds at randomized intervals.  Can be enabled or disabled using the [[point-entities.logic-and-entity-state-system]].
|Key|Type|Default|Description|
|---|---|---|---|
|`count`|integer|0|Pick different sound to start random seed from, 0 through 5|
|`volume`|integer|1|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|
|`speed`|integer|1|Set normal falloff attenuation.  This affects the distance the sound will be heard.|
|||0|Plays everwhere|
|||2|Idle (not as noticeable)|
|||3|Static (bit shorter)|
|||4|Quiet (small radius, still barely audible at longer distances but fades out quicker)|
|`wait`|integer|10|Maximum interval time.|
|`delay`|integer|10|Minimum interval time.|
|`waitmin`|integer|4-8|Initial start time.|
|`spawnflags`|2|0|Play only once when targeted|
||64|0|Starts off.  Must have `targetname` set!|

Sounds to play:
> * ad171/ambience/windgust1.wav
> * ad171/ambience/windgust2.wav
> * ad171/ambience/windgust3.wav
> * ad171/ambience/windgust4.wav
> * ad171/ambience/windgust5.wav
> * ad171/ambience/windgust6.wav

.

### `ambient_custom_wood`
Randomly plays wood creaking sounds at randomized intervals.  Can be enabled or disabled using the [[point-entities.logic-and-entity-state-system]].
|Key|Type|Default|Description|
|---|---|---|---|
|`count`|integer|0|Pick different sound to start random seed from, 0 through 3|
|`volume`|integer|1|Set to a value from 0 to 1, 0 is silent, 1 is full volume.|
|`speed`|integer|2|Set normal falloff attenuation.  This affects the distance the sound will be heard.|
|||0|Plays everwhere|
|||2|Idle (not as noticeable)|
|||3|Static (bit shorter)|
|||4|Quiet (small radius, still barely audible at longer distances but fades out quicker)|
|`wait`|integer|30|Maximum interval time.|
|`delay`|integer|15|Minimum interval time.|
|`waitmin`|integer|8-16|Initial start time.|
|`spawnflags`|2|0|Play only once when targeted|
||64|0|Starts off.  Must have `targetname` set!|

Sounds to play:
> * ad171/ambience/woodcreak2a.wav
> * ad171/ambience/woodcreak2b.wav
> * ad171/ambience/woodcreak2c.wav
> * ad171/ambience/woodcreak2d.wav