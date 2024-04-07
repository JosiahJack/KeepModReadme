
The current game level, known as world or map, has many options specific to
that level.  This could be global effects such skybox and fog or could be
player specific such has starting items or item removal.

Please note that the entity name for the world is `worldspawn` and is itself
technically an entity whose model is the map bsp.

## General Options

### `worldtype`
* **Type:** integer
* **If Set:** This changes the types of keys and the models used for health pickups.
> * Use 0 for Medieval - changes health to jars and keys to spiked metal keys
> * 1 for Runic(metal) - runekeys for silver, gold keys
> * 2 for Present (base/tech) - standard tech health boxes, electronic keycards 
* **If Left Blank:** Defaults to Medieval

### `message`
* **Type:** string
* **If Set:** This is the name of the level. Name is displayed on the HUD while holding down the TAB key.
* **If Left Blank:** Map will have no name!  This is not expected and will appear to be a bug.

### `sounds`
* **Type:** integer
* **If Set:** Specifies the music track to be played.  Must be a simple number 2 through 99 with no fractional decimal portion.  The number corresponds to the music file to play located either within ID1/music/ or within keep/music/.  The music tracks must be named track##.mp3, the ## will be the number that corresponds to this `sounds` value.  For example, setting `sounds` to 43 will play and loop track43.mp3 during playtime of the level.  track1.mp3 is reserved by the game's CD to store the .iso file that holds all the game data.  Any track1.mp3's will be ignored even if you set `sounds` to 1.
* **If Left Blank:** Defaults to track00.mp3 which is reserved empty slot; actual tracks named track00.mp3 will not be played.  No music will play.

### `wad`
* **Type:** string
* **If Set:** EDITOR SET - do not change.  This tells the compiler what .wad files to load and use for textures.  Textures are embedded into the .bsp file during compile time.
* **If Left Blank:** Map will have no textures!

### `sky`
* **Type:** string
* **If Set:** Specifies the skybox name to load and use as an override to classic texture-based skies.  The name must be the full set of characters in the name that occurs before any of the directions.  Skyboxes typically are named with directions dn, lf, ft, rt, up, and bk at the end of the filenames to specify all 6 sides of the cube that is the sky.  So for instance, a sky named mysky will need 6 files named myskydn.tga, myskylf.tga, etc.  If the skybox name has an _ in the name, be sure to include it.  For instance, a sky named mysky_dn.tga, mysky_up.tga etc. will need to have `sky` set to `mysky_`.
* **If Left Blank:** Default fast scrolling sky texture will be used from the .wad.

### `_skyroom`
* **Type:** vector
* **If Set:** Specified as a vector like `0 0 0`. This sets the skyroom camera's center point for QSS/FTE engines for implementation of 3D skyboxes.  Note: if you have placed an `info_skyroom `, that entity's origin point will override this value.
* **If Left Blank:** Defaults to world `0 0 0`.

### `gravity`
* **Type:** integer
* **If Set:** Specifies an override for the level gravity.  Use values less than 800 for low-gravity and values higher than 800 for faster/heavier gravity (not recommended!).
* **If Left Blank:** Defaults to 800.

### `passive_state`
* **Type:** boolean (0 or 1)
* **If Set:** Sets up all monsters into a passive state regardless of their individual `passive_state` override values.
* **If Left Blank:** Monsters will default to normal behavior or use their individual `passive_state` override values.

### `no_trackondeath`
* **Type:** boolean (0 or 1)
* **If Set:** Homing projectiles will stop tracking players when monsters die and will continue straight on their current trajectory.
* **If Left Blank:** Homing projectiles will continue to track and follow the monster's enemy, which is usually the player.

### `hazard_dmg`
* **Type:** vector
* **If Set:** Overrides the default damages for liquid environmental damages.  Specified as 3 float values like `0 0 0` (x y z).
> * x = water drowning damage per gulp
> * y = slime damage per instance
> * z = lava damage per instance
* **If Left Blank:** Defaults to `2 4 10`.

### `no_item_offset`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Changes whether or not health and ammo items will use the bottom-left-corner offset which was default placement for many years.
> * Set to -1 to disable item offset and force to use the origin point as the item's center on all health and ammo items.
> * Set to 0 to default to item's origin point as the item's center on all health and ammo items.
> * Set to 1 to enable item offset and use the old default of the bottom left corner of the brush-based bsp health and ammo item models.
* **If Left Blank:** Defaults to 0.

### `no_item_rotate`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Changes whether or not to randomly rotate items.
> * Set to -1 to disable randomized item rotation and respect the mapper's rotation.
> * Set to 0 to default to respecting the mapper's rotation.
> * Set to 1 to enable forced randomized rotation on all health and ammo items.
* **If Left Blank:** Defaults to 0.

### `no_zaware`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Overrides monsters' individual settings for whether to use Z-aware aiming for arced projectile attacks.
> * Set to -1 to force disable all z-aware and simply lob at the same angle regardless of targeted enemy's height.
> * Set to 0 to default to use z-aware projectile arcing where available on a monster.
> * Set to 1 to enable forced z-aware projectile arcing (lob) for all monsters who have such a projectile type.
* **If Left Blank:** Defaults to 0.

### `no_liquiddmg`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Overrides monsters' individual settings for whether liquid damages the monster, if said monster is normally damaged by liquids (e.g. zombies).  Does not affect drowning spawnflag.  Only affects slime and lava damaging monsters.
> * Set to -1 to force disable damage from liquids.
> * Set to 0 to default to damaging monsters by liquids on monsters who normally get damaged by liquids (e.g. zombies).  Does not affect drowning spawnflag.
> * Set to 1 to enable forced liquid damage to all monsters.
* **If Left Blank:** Defaults to 0.

### `knight_defskin`
* **Type:** integer
* **If Set:** Changes the monster_knight's default skin choice to better fit the level's theme.
> * Set to 0 for normal metal with red highlights.
> * Set to 1 for grey metal only, no colored highlights.
> * Set to 2 for grey metal with vertical stripe pattern.
> * Set to 3 for swampy green/red
* **If Left Blank:** Defaults to 0.

### `bodyflrcheck`
* **Type:** boolean (0 or 1)
* **If Set:** Check for monster dead body gravity.  Overrides all monsters' individual settings.
* **If Left Blank:** Defaults to not check gravity and respects monsters' individual settings.

### `bodyfadeaway`
* **Type:** float
* **If Set:** Overrides how long all monsters' individual body fade setting after death.  This forces the time the corpse will stay until it fades away to be 10 to 15 seconds for all corpses.
* **If Left Blank:** The enemy's body will fade after 999999 seconds (about 4.6 hours), unless overriden on an individual monster.

### `no_moncountdevmsg`
* **Type:** boolean (0 or 1)
* **If Set:** Disables developer messages about monsters that have `no_monstercount` set to 1 (true).  Only displays if `developer 1` is set.
* **If Left Blank:** Defaults to display notification messages about monsters that are set to not affect the monster count.  Please note that these monsters still affect the total monsters and total monsters killed at the end of the level.  The `no_monstercount` simply specifies not to affect the count until they have been killed.

### `sprite_particles`
* **Type:** boolean (0 or 1)
* **If Set:** Change particles to use sprites only instead of fancy engine particles (DP, QSS, FTE).  Does not affect other engines.
* **If Left Blank:** Default to using any available fancy engine particles in addition to sprites where used.

### `particlemax`
* **Type:** integer
* **If Set:** Change maximum available particles for sprite-based particles.
* **If Left Blank:** Default to 1024.

### `no_sgprojectile`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Changes the visibility of shotgun projectiles.  Only applicable
  if projectile shotguns are used in `temp1` variable (See
  [[general.config-and-settings]]).
> * Set to -1 to make projectiles invisible if used.
> * Set to 0 to use default of visible (if `temp1` has projectile shotguns enabled)
> * Set to 1 to force visible (if `temp1` has projectile shotguns enabled)
* **If Left Blank:** Defaults to 0.

### `no_sgcasing`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Disiable or enable dropping of casings, e.g. when firing shotguns.
  Only applicable if casings are enabled in `temp1` variable (See
  [[general.config-and-settings]]).
> * Set to -1 to disable all casings.
> * Set to 0 to use default of dropping casings (if `temp1` has casings enabled enabled)
> * Set to 1 to force dropping of casings (if `temp1` has casings enabled)
* **If Left Blank:** Defaults to 0.

### `no_bigprojectiles`
* **Type:** boolean (0 or 1)
* **If Set:** Force use of larger more easily visible shotgun projectiles. 
  Only applicable if projectile shotguns are used in `temp1` variable (See
  [[general.config-and-settings]])
* **If Left Blank:** Default to using smaller projectiles (if `temp1` has projectile shotguns enabled).

### `mapvar_update`
* **Type:** vector
* **If Set:** Change Map Variables at level start to force certain states on/off.  Specified as a vector like `0 0 0` (x y z).
> * x = start of range to change (integer 0 through 132 available)
> * y = end of range to change (integer 0 through 132 available). Must be larger than x.
> * z = boolean value to change all within the range to (0 or 1)
* **If Left Blank:** Default to using smaller projectiles (if `temp1` has projectile shotguns enabled).

### `fog`
* **Type:** vector4
* **If Set:** Changes the fog density and color.  Specified as a vector like `0 0 0 0` (d r g b for density red green blue).  If you plan to use `trigger_fog`, you must also set `fog_density` and `fog_colour` values below for the trigger to be able to transition between fog values properly.
> * d = fog density 0 to 1.0.  Low values work best for larger view distances. 1.0 will make it hard to see anything past the player's nose.  Recommend 0.02.
> * r = red value 0 to 1.0
> * g = green value 0 to 1.0
> * b = blue value 0 to 1.0
* **If Left Blank:** Default to `0 0 0 0`, no density, no fog.

### `fog_density`
* **Type:** float
* **If Set:** Changes the fog density 0 to 1.0.  Low values below 0.10 work best.  This should match the fog density paramater in `fog` to work properly with `trigger_fog` changes.
* **If Left Blank:** Default to 0, no fog.

### `fog_colour`
* **Type:** vector
* **If Set:** Changes the fog color.  Specified as a vector like `0 0 0` (r g b for red green blue).  This should match the fog density paramater in `fog` to work properly with `trigger_fog` changes.
> * r = red value 0 to 1.0
> * g = green value 0 to 1.0
> * b = blue value 0 to 1.0
* **If Left Blank:** Default to `0 0 0`, black.

### `fog_dpextra`
* **Type:** vector4
* **If Set:** Changes the specialty fog settings used by the DarkPlaces engine.  Specified as a vector like `0 0 0 0` (a s e h f for alpha start end height fadedepth).  These get added to the full `fog` command after `d r g b` like so: `d r g b a s e h f`.  Most engines will ignore these values.
> * a = alpha, modifies overall transparency of the fog (best to leave this at 1 and modify density instead)
> * s = start, changes the start radius distance from the player camera before fog starts to increase in density from 0 to `density`.
> * e = end, radius distance from the player camera before fog is full `density`.  Density will taper linearly in between s and e.
> * h = height, height below which fog will work normally and above which fog is not present.
> * f = fadedepth, the distance below height before fog transitions into normal effect.  Tapers linearly from no fog to normal fog in between.
* **If Left Blank:** Default to `1 0 8192 1024 32`, no alpha adjustment, start at player camera center, 8192 distance from player for full fog `density`, 1024 height above world `0 0 0` for fog to start - above which density is always 0, and 32 for depth into the fog to transition to normal density (i.e. 1024 - 32 = 992 and below for fog to behave fully normally, above 1024 fog is gone, transitions in between)

### `skyfog_density`
* **Type:** float
* **If Set:** Changes the starting `_skyfog` value for `trigger_skyfog`.  Set to match `_skyfog`.
* **If Left Blank:** Default to 0.5.  Overrides `_skyfog` if greater than 0! Value linearly transitions from `_skyfog` to the this value as an inbetween and then to the new density specified on the trigger.

### `_skyfog`
* **Type:** float
* **If Set:** Changes the fog color overlay on the skybox or sky textures only, 0 to 1.0.  1.0 causes sky to be **only** the color of the fog.
* **If Left Blank:** Default to 0, fog does not change the appearance of the sky or skybox.  This gets overriden by `skyfog_density`!  Set to match!

### `water_alpha`
* **Type:** float
* **If Set:** Changes the transparency of all normal *water brushes (texture names that start with `*`), 0 to 1.0.  1.0 is classic ID1 non-transparent water.  Must be greater than 0 to affect transparency.  Affects all liquids including *slime and *lava and *tele unless the engine supports the other individual values below.  Overrides `r_wateralpha` console variable.
* **If Left Blank:** Default to 0.  All water is non-transparent and cannot be seen through, unless the engine's `r_wateralpha` value is set.

### `lavaalpha`
* **Type:** float
* **If Set:** Changes the transparency of all normal *lava brushes (texture names that start with `*` and `lava`), 0 to 1.0.  1.0 is classic ID1 non-transparent lava (recommended for lava!).  Must be greater than 0 to affect transparency.
* **If Left Blank:** Default to 0.  All lava is non-transparent and cannot be seen through, unless the engine's `r_wateralpha` value is set.

### `slimealpha`
* **Type:** float
* **If Set:** Changes the transparency of all normal *slime brushes (texture names that start with `*` and `slime`), 0 to 1.0.  1.0 is classic ID1 non-transparent slime.  Must be greater than 0 to affect transparency.
* **If Left Blank:** Default to 0.  All slime is non-transparent and cannot be seen through, unless the engine's `r_wateralpha` value is set.

### `telealpha`
* **Type:** float
* **If Set:** Changes the transparency of all normal *tele brushes (texture names that start with `*` and `tele`), 0 to 1.0.  1.0 is classic ID1 non-transparent teleporter starfluid (recommended for teleports!).  Must be greater than 0 to affect transparency.
* **If Left Blank:** Default to 0.  All teleport startfluid is non-transparent and cannot be seen through, unless the engine's `r_wateralpha` value is set.

.

.

.

## Player Affecting Options

### `playerweather`
* **Type:** string
* **If Set:** Specifies the weather effect to play above the player's head, e.g. rain, snow.
* **If Left Blank:** No added weather effects.

### `plasmagun_dmg`
* **Type:** vector
* **If Set:** Changes the impact damage and splash damage of the AD plasmagun (the _override_ weapon that replaces the thunderbolt).  Specified as a vector like `0 0 0` (x y z).  Changing the z value allows for easier plasmagun-jumping like rocket-jumping.
> * x = direct damage minimum
> * y = random additional damage.  For instance x of 45 and a y of 10 would do damage of 45-55.
> * z = splash damage radius, typically I denote this by putting the value in () in tables within this readme.
* **If Left Blank:** Defaults to standard plasmagun damage of `45 0 20` for a damage of 45(20).

### `ckeyhint`
* **Type:** boolean (0 or 1)
* **If Set:** Disables message that displays "Press [I] to display Arcane Key inventory" on picking up a custom key (`item_keyx`).
* **If Left Blank:** Defaults to 0, will normally display a message on custom key pickup specifying that by pressing [I] you can see a list of custom keys that you have picked up.

### `upgrade_axe`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Chooses whether to remove or leave the upgrade _override_ weapon Shadow Axe from player's inventory when the level starts.
> * Set to -1 Remove the Shadow Axe from the player at level start.
> * Set to 0 leave the Shadow Axe inventory as is.  If the player has it, keep it.  If the player doesn't have it, they still won't have it.
> * Set to 1 to force give the player the Shadow Axe at the beginning of the level whether they had the axe before or not.
* **If Left Blank:** Defaults to 0.

### `upgrade_ssg`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Chooses whether to remove or leave the upgrade _override_ weapon Widowmaker (Triple Shotgun) from player's inventory when the level starts.
> * Set to -1 Remove the Widowmaker (Triple Shotgun) from the player at level start.
> * Set to 0 leave the Widowmaker (Triple Shotgun) inventory as is.  If the player has it, keep it.  If the player doesn't have it, they still won't have it.
> * Set to 1 to force give the player the Widowmaker (Triple Shotgun) at the beginning of the level whether they had the axe before or not.
* **If Left Blank:** Defaults to 0.

### `upgrade_lg`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Chooses whether to remove or leave the upgrade _override_ weapon Plasmagun (AD) from player's inventory when the level starts.
> * Set to -1 Remove the Plasmagun (AD) from the player at level start.
> * Set to 0 leave the Plasmagun (AD) inventory as is.  If the player has it, keep it.  If the player doesn't have it, they still won't have it.
> * Set to 1 to force give the player the Plasmagun (AD) at the beginning of the level whether they had the axe before or not.
* **If Left Blank:** Defaults to 0.

### `give_weapons`
* **Type:** integer
* **If Set:** Specify which `items` to give at level start.  Add any bitmask
  values together from the table on [[weapons]] page to create the value to add
  to the player's inventory.  This only affects `items` and not `items2`,
  `moditems`, or `perms`.
* **If Left Blank:** Leaves inventory `items` untouched.

### `take_weapons`
* **Type:** integer
* **If Set:** Specify which `items` to take away at level start.  Add any
  bitmask values together from the table on [[weapons]] page to create the
  value to take away from the player's inventory.  This only affects `items`
  and not `items2`, `moditems`, or `perms`.
* **If Left Blank:** Leaves inventory `items` untouched.

### `take_perms`
* **Type:** integer
* **If Set:** Specify which `perms` to take away at level start.  This only affects `perms` and not `items`, `items2`, or `moditems`.
* **If Left Blank:** Leaves inventory `perms` untouched.

### `useold_axe`
* **Type:** boolean (0 or 1)
* **If Set:** Use AD style axe for weapon_axe and view model.
* **If Left Blank:** Use classic original ID1 axe (uses dwere's subtly enhanced models).

### `max_health`
* **Type:** integer
* **If Set:** Specifies minimum starting health.  If players' health was below this value at the end of the previous level, the players' health will be raised to this value.
* **If Left Blank:** Default is 50.

### `reset_health`
* **Type:** boolean (0 or 1)
* **If Set:** Force players' health to this value at level load.
* **If Left Blank:** Leave players' health where it is at, with respect to `max_health` value above.

### `currentammo`
* **Type:** boolean (0 or 1)
* **If Set:** Change players' ammo to be one of the `ammo_*` quantities below.
* **If Left Blank:** Leave players' ammo alone.

### `ammo_shells`
* **Type:** integer
* **If Set:** Specifies starting shells ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_nails`
* **Type:** integer
* **If Set:** Specifies starting nails ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_rockets`
* **Type:** integer
* **If Set:** Specifies starting rockets ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_cells`
* **Type:** integer
* **If Set:** Specifies starting cells ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_bolts`
* **Type:** integer
* **If Set:** Specifies starting bolts ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_poison`
* **Type:** integer
* **If Set:** Specifies starting poison ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_lava_nails`
* **Type:** integer
* **If Set:** Specifies starting lava nails ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_multi_rockets`
* **Type:** integer
* **If Set:** Specifies starting multi-rockets ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_plasma`
* **Type:** integer
* **If Set:** Specifies starting plasma ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_bloodcrystals`
* **Type:** integer
* **If Set:** Specifies starting blood crystals ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_voidshards`
* **Type:** integer
* **If Set:** Specifies starting void shards ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `ammo_elemental`
* **Type:** integer
* **If Set:** Specifies starting elemental mana ammo.  Only works if `currentammo` is true (1).
* **If Left Blank:** Default is 0.

### `armortype`
* **Type:** integer
* **If Set:** Changes which armor type the player has.
> * Set to 0 for does not affect current armor type
> * Set to 1 for green armor, 30% protection
> * Set to 2 for yellow/blue armor, 60% protection
> * Set to 3 for red armor, 80% protection
* **If Left Blank:** Default is 0.

### `armourvalue`
* **Type:** integer
* **If Set:** Changes how much armor the player has to this value.  Must be greater than 0.  Recommend not setting above 999.
* **If Left Blank:** Default is to leave armor alone.

### `no_axestart`
* **Type:** boolean (0 or 1)
* **If Set:** Start with nothing!  No axe, no weapons, no ammo.
* **If Left Blank:** Leave players' inventory alone.

### `jump_height`
* **Type:** integer
* **If Set:** Changes jump boots velocity to be this value.  Must be greater than 0.  Only affects jump boots subsequent jumps; does not affect first or any normal jumps.
* **If Left Blank:** Defaults to 270 for normal jump impulse velocity on subsequent double, triple, etc. jumps.

### `fall_dmg`
* **Type:** integer (negatable)
* **If Set:** Changes the damage received when falling too far to be this value.  Set to -1 in order to do no fall damage or pain sound (same effect as having Ninja Armor).
* **If Left Blank:** Defaults to normal fall damage of 5.

### `fall_dmgwater`
* **Type:** integer
* **If Set:** Changes the damage received when falling too far into a water surface to be this value.  Must be greater than 0 to cause pain sound and damage.
* **If Left Blank:** Defaults to 0.  Falling into water from a great height does not hurt.

### `fall_heightlow`
* **Type:** integer (negatable)
* **If Set:** Changes the height value above which the player will make an "oof!" sound when hitting the ground.  Any higher lower than this and player will land softly and silently.
* **If Left Blank:** Defaults to normal safe fall distance of 300.

### `fall_heighthigh`
* **Type:** integer (negatable)
* **If Set:** Changes the height value above which the player will make a pain sound and take damage when hitting the ground.  Any lower than this and the player will land without getting hurt.
* **If Left Blank:** Defaults to normal danger fall distance of 650.

### `fall_speeddebug`
* **Type:** boolean (0 or 1)
* **If Set:** Displays fall velocity on player ground impact in the console.
* **If Left Blank:** Does not display fall velocity on impact.

.

.

.

## World Lighting Options
These values are used by the compiler during compile time to affect various attributes of the level's light.  Please refer to [ericw Light](https://ericwa.github.io/ericw-tools/doc/light.html) for more details and up-to-date compiler documentation.

### General Lighting
### `_minlight`
* **Type:** float (0 to 255)
* **If Set:** Specifies the minimum overall light value to apply to **all** surfaces in the level.  255 is fully lit same as if you entered `r_fullbright 1` in the console.  Removes all deep dark shadows and pure black areas.  Use with caution.
* **If Left Blank:** Defaults to 0, if there is no light entity placed near a surface, the surface will be pure black and provide maximum contrast.

### `_minlight_color`
* **Type:** vector (0 to 255)
* **If Set:** Specifies the color for the minimum overall light value that is applied to **all** surfaces in the level.  Specified as 3 values like `0 0 0` (r g b for red green blue).  Useful for tinting the entire level to a certain color. `_minlight` must be greater than 0 to take any effect.  Removes all deep dark shadows and pure black areas.  Dramatically changes the colors of the level.  Use with caution.  Subtle colors tend towards better results and aesthetic. 
* **If Left Blank:** Defaults to `255 255 255` for normal white colored light.

### `_minlight_dirt`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Affects dirtmapping for `_minlight`.  `_minlight` must be greater than 0 to take any effect.
> * Set to -1 to disable and override all `_minlight_dirt` settings on individual brush entities.  Disables **all** dirt from `_minlight`.
> * Set to 0 to use default of no dirt for the world and specific dirt for brush entities as specified individually by `_minlight_dirt` on each brush entity, if specified.
> * Set to 1 to enable and use dirt mapping on **all** world surfaces.
* **If Left Blank:** Defaults to 0.

### `_range`
* **Type:** float
* **If Set:** Multiplies all lights' brightness (`light`) to scale the brightness for each light entity up or down.  Set to less than 0.5 for reduced brightness (darker) and to more than 0.5 for increased brightness (brighter).  Does not affect distance so may look odd if set too high.  Affects **all** lights.  Use with caution!
* **If Left Blank:** Defaults to 0.5 (normal).

### `_dist`
* **Type:** float
* **If Set:** Multiplies all lights' distance to scale the distance light will travel from each light entity up or down (behaves similar to `wait`).  Set to less than 1 for reduced distance (darker) and to more than 1 for increased distance (brighter).  Affects **all** lights.  Use with caution!
* **If Left Blank:** Defaults to 1.0 (normal).

### `_gamma`
* **Type:** float
* **If Set:** Multiplies all the full lightmap's brightness by this value.  Greater than 1 will increase the overall map brightness, less than 1 will reduce overall brightness.  Use with caution!
* **If Left Blank:** Defaults to 1.0 (normal).

### `_spotlightautofalloff`
* **Type:** float
* **If Set:** Changes default spotlight falloff distance to instead use the distance from the light to a targeted `info_null` (or other entity)'s center.  This only affects lights whose `_falloff` override is left blank (set to 0).  Light must have a `target`.
* **If Left Blank:** Defaults to 0.  Light will use default spotlight settings to generate a spotlight when a light has a `target`.

### `_dirt`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Affects dirtmapping for all surfaces.  Dirt adds less brightness along edges between faces depending on how acute the angle is between the face normals.  You can override the global setting for specific lights with the `_dirt` key, for point light entities, and the `_sunlight_dirt`, `_sunlight2_dirt`, `_minlight_dirt` keys, in `worldspawn`.
> * Set to -1 to disable dirtmapping globally, including disabling entity dirt overrides.
> * Set to 0 to use default value specified by `_dirt` on entities, but otherwise not use dirtmapping.
> * Set to 1 to enable and use dirtmapping on all surfaces affected by lights except on brush entities or lights that disable it.

### `_dirtmode`
* **Type:** boolean (0 or 1)
* **If Set:** Randomized dirtmapping.  Sometimes darkness (dirt) will not be applied to an edge. `_dirt` must be enabled.
* **If Left Blank:** Normal dirtmapping.  `_dirt` must be enabled.

### `_dirtscale`
* **Type:** float
* **If Set:** Scale the darkness of dirt.  Lower values reduce the dirt darkness while larger values make dirt shadowing darker and more noticeable.
* **If Left Blank:** Defaults to 1.0

### `_dirtgain`
* **Type:** float
* **If Set:** Modifies the exponental falloff for dirt attenuation.  Low values make shadows darker and stretch further from edges/corners.  High values make dirt taper off faster and therefore be less dark and go shorter distance from edges/corners.
* **If Left Blank:** Defaults to 1.0

### `_dirtdepth`
* **Type:** float
* **If Set:** Maximum depth in units for checking for and applying dirtmapping.
* **If Left Blank:** Defaults to 128

### `_dirtangle`
* **Type:** float
* **If Set:** Cone angle in degree for occlusion testing, 1 to 90.  Lower values might help remove unwanted dirt on the inside of arches, pipes, etc.
* **If Left Blank:** Defaults to 88.

### `_bounce`
* **Type:** boolean (0 or 1)
* **If Set:** Enables bounce lighting.  This adds extra light by using world surfaces as light sources to "bounce" more light from based on their brightness value from normal lighting.  Useful for softer shadows, no need for extra `light` entities, and more realistic lighting behavior (aka simulates global illumination, true global illumination uses color from the surfaces, see `_bouncecolorscale` below for affecting bounce color)
* **If Left Blank:** Normal lighting, no added bounce.  Useful for darker shadows, more contrast, and oldschool appearance.

### `_bouncescale`
* **Type:** float
* **If Set:** Scale factor to multiply the overall bounce brightness by.  Higher values increase brightness while lower reduces it.
* **If Left Blank:** Defaults to 1.

### `_bouncecolorscale`
* **Type:** float
* **If Set:** Scale factor to use the texture color to affect the color of bounce lighting, 0 to 1.0,  Higher values copy texture color more exactly.  Mimics global illumination by turning all world level surfaces into light sources (mimics real life in this way).
* **If Left Blank:** Defaults to 0, preserves `color` from the light source exactly.

### `_bouncestyled`
* **Type:** boolean (0 or 1)
* **If Set:** Enables bounce lighting for lights with styles.  This makes flickering, switchable, and glowing lights also have bounce and thereby affect more surfaces.  Useful for them to have more impact on the scene and to increase surprise for switched lights.
* **If Left Blank:** Normal lighting, no added bounce for lights with styles.

.

### Sunlight / Environment Lighting
### `_sunlight`
* **Type:** float
* **If Set:** Set the brightness of the sunlight.  Sun's light comes from worldspawn surfaces textured with sky and comes at the level at a particular angle to mimic a sun in the sky.  Does not emit from brush entities textured with sky textures.  Set to greater than 0 to have any effect.  255 is full brightness, but not overbright.  This adds light to the world without needing to place added `light` entities.
* **If Left Blank:** Defaults to 0.  No extra light will be added as though from a sun.

### `_sunlight_color`
* **Type:** vector (0 to 255)
* **If Set:** Specifies the color for the sun's light.  Specified as 3 values like `0 0 0` (r g b for red green blue).  Useful for having different colored sun or to simulate different times of day such as orange colored sunset.
* **If Left Blank:** Defaults to `255 255 255` for normal white colored light.

### `_sunlight_mangle` (alternatively `_sun_mangle` for same effect)
* **Type:** vector
* **If Set:** Specifies the direction mangle of the sun's rays.  Specified as 3 values like `0 0 0` (x y z for yaw pitch roll in that order (yes it's an odd order, because it's mangle not angles)).  Useful for having low angled sunlight for sunset/sunrise or other times of day or to have up-angled sunlight for upside-down hanging levels.
> * x (yaw) = set for the compass direction of the sun's angle.  90 points from south towards **north**, 270 from north towards **south**, 0 from west towards **east**, 180 from east towards **west**.  Pick the value desired for the direction your sunlight comes from.  Recommend using a value that is different than these cardinal directions otherwise you might have odd or unnatural lighting on parallel walls.
> * y (pitch) = the up/down angle of the sun.  Negative values angle down towards the ground, positive values angle up towards the sky.  -90 is straight down (high noon), 90 is straight up.  Most maps use a negative value for realistic sun angling.  Values close to 0 will simulate sunset/sunrise, e.g. -10.
> * z (roll) = the twist of the sunlight angle.  Not useful and does nothing..
* **If Left Blank:** Defaults to `0 -90 0' straight down high noon.

### `_anglescale`
* **Type:** float
* **If Set:** Sunlight angle scale for how much the brightness changes with the difference in sunlight angle and surface normal.  Must be between 0 and 1.0.  Closer to 1 will be brighter at sharper angle and closer to 0 will mean the angle difference has no effect.
* **If Left Blank:** Defaults to 0.5.

### `_minlight_dirt`
* **Type:** trilean (-1, 0, or 1)
* **If Set:** Affects dirtmapping for any surfaces affected by `_sunlight`.  Dirt adds less brightness along edges between faces depending on how acute the angle is between the face normals.  If `_sunlight` is 0, this has no affect.
> * Set to -1 to disable dirt within `_sunlight`, causes acute corners/edges to be as bright as surrounding surfaces.
> * Set to 0 to use default value specified by `_dirt`.
> * Set to 1 to enable and use dirt mapping on surfaces affected by `_sunlight`.

### `_sunlight_penumbra`
* **Type:** float
* **If Set:** How wide, in degrees, the `_sunlight` edge is for transition from bright to dark areas where sun cannot reach.  Larger values provide softer edges.  3-4 is a gentle but still distinct edge, 10-20 or more is diffuse like on cloudy/foggy days.
* **If Left Blank:** Defaults to 0, crisp edged shadows.

### `_sunlight2`
* **Type:** float
* **If Set:** Set the brightness of the upper ambient environment light from all directions.  `_sunlight2` light comes from all worldspawn surfaces textured with sky from every angle.  Does not emit from brush entities textured with sky textures.  Set to greater than 0 to have any effect.  255 is full brightness, but not overbright.  This adds light to the world without needing to place added `light` entities.  Useful for blue contrast lighting from the sky along with orange/yellow `_sunlight` for the sun.  Only affects the top half of the map.
* **If Left Blank:** Defaults to 0.  No extra light will be added as though from a sun.

### `_sunlight2_color`
* **Type:** vector (0 to 255)
* **If Set:** Specifies the color for the upper ambient environment light.  Specified as 3 values like `0 0 0` (r g b for red green blue).  Recommend picking a color that is complementary (opposite) of the `_sunlight_color`.  Typically a pale blue to simulate sky.  Works best if it matches the skybox average color.  Only affects the top half of the map.
* **If Left Blank:** Defaults to `255 255 255` for normal white colored light.

### `_sunlight3`
* **Type:** float
* **If Set:** Set the brightness of the lower ambient environment light from all directions.  `_sunlight2` light comes from all worldspawn surfaces textured with sky from every angle.  Does not emit from brush entities textured with sky textures.  Set to greater than 0 to have any effect.  255 is full brightness, but not overbright.  This adds light to the world without needing to place added `light` entities.  Useful for blue contrast lighting from the sky along with orange/yellow `_sunlight` for the sun.  Only affects the bottom half of the map.
* **If Left Blank:** Defaults to 0.  No extra light will be added as though from a sun.

### `_sunlight3_color`
* **Type:** vector (0 to 255)
* **If Set:** Specifies the color for the lower ambient environment light.  Specified as 3 values like `0 0 0` (r g b for red green blue).  Recommend picking a color that is complementary (opposite) of the `_sunlight_color`.  Typically a pale blue to simulate sky.  Works best if it matches the skybox average color.  Only affects the bottom half of the map.
* **If Left Blank:** Defaults to `255 255 255` for normal white colored light.