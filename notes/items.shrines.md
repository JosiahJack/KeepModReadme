---
id: tphzvgj738urcbgg96m6aof
title: Shrines
desc: ''
updated: 1657646657743
created: 1657646654633
---
The inhabitants of the world of Quake are not altogether unreligious.  There is a plenary collection of deities and household teraphim.  Travelers may choose to pay their respects by lighting a candle and thus receive a blessing.  It is important to distinguish between _teraphim_, who serve as physical representatives of deities and _idols_, who are treated as deities of themselves.  However, one may alternatively disregard such lesser deities and distinctions entirely and pay respects to a higher deity by counting these shrines as unholy, desecrating them by smashing them to receive an alternative blessing from an elder god.  What one does must be considered carefully, even atheistically ignoring shrines may have consequences.

### Benefits
These are the shrine benefits.  Detailed per `style` benefits given in the chart further down.

**Respects** are paid simply by walking up to a shrine's table structure.  The candle(s) will be lit by trigger.

**Desecration** is performed by destroying the shrine table.  Desecration after Respects will remove the respect blessing and may possibly be met with even stronger consequences.  Desecration affects all players in coop.

Blessings are only granted for that level.

### Construction Standards
All shrines must have at least one candle placed mostly centered on a 32 high table structure with a thin `trigger_once` that is sized 8x32x32, with the trigger thinnest at the table front, touching the table, trigger top surface flush with tabletop, and trigger centered with the table.  The candle should start off by setting `spawnflags` 1 and giving a `targetname`.

The `trigger_once` must target an `info_shrine` with a `style` type set, while the table shall be a `func_breakable` that targets the same `info_shrine`.  When an `info_shrine` is targeted, it checks if the target is a player for Respects, or a breakable for Desecration.

Shrine theming should be consistent with the guide in the chart below; arrangement, details, and shape at mapper discretion.  Use of a shrine prefabs as-is is fine, though `message` should be changed to suit your map's story.

`info_shrine` should be placed above the table, ideally in a place that makes sense as a point from which aura effects emanate.  This is the center of the aura, so place accordingly.

### Story Elements
Shrines have a god associated with them that a mapper specifies with `message`.  Associated `<blessing>` is in the chart below with a different blessing message for when a shrine is respected or desecrated. 
When blessed, the centerprint displayed will display a message like so:

```
<god>
of the <style> Shrine has blessed
you with <blessing> 
```

Or

```
<god>
of the <style> Shrine has lost influence,
the Elder God blesses with
<blessing> 
```

### Aura
Auras apply the effects in the chart below to any players within the aura.  The aura effects are applied once every `delay` seconds for an amount of `cnt`.  Any monsters who are not of EVIL `alignment` will always receive healing at the same rate as the `delay` and `cnt` and also receive an increase in their pain timer to 5 seconds past the current time, so they won't go into any pain flinch animations while within the aura and can continue to consistently help players.  Monster benefits are the same regardless of `style`.

### Blessings
Blessings are always the same according to below, but the response to actions is map specific based on the `target` set on the `info_shrine`.  Best practice is for desecration to target delay spawned monsters who have `nomonstercount` of 1 so that shrines who aren't desecrated still show all monsters have been killed.

|Shrine Type|`style`|Rune Sign|Respect Blessing|Desecration Blessing|Theme Requirements|Recommended Decorations|
|---|---|---|---|---|---|---|
|Earth|0|Green|"Aura of Earth Magick,\nbecome as stone." Grants aura that rapidly provides armor to nearby players and player followers and removes poison buffs, 1 armor per every 0.3 secs.  Prevents and removes curse buffs.  Reduces damage from slime and poison attacks by 75%.|"Poison Protection!" Gives full red armor and map lasting environmental protection against slime and poison.  Aura lost.|Dirt and stone|Wood crates, barrels, mushrooms, slime|
|Water|1|Blue|"Aura of Water Magick,\flow as water." Grants aura that recharges shells 1 per 0.5secs.  Prevents and removes fire buffs.  Reduces damage from fire and lava attacks by 75%.|"Swimfall Prowess!" Grants speed swimming (same effect as wetsuit) for duration of map.  Refills shells to max and increases max shells by 100.  Drowning damage reduced by 50% and fall damage reduced to zero for duration of map.  Aura lost.|Grass and stone, must have pool|Vines, drips, pots|
|Air|2|White|"Aura of Air Magick,\ninhale deeply." Grants aura of breath allowing indefinite underwater swimming, aura recharges nails ammo 1 per 0.5secs.|"Breath of Uplifting!" Refills nails to max and increases max nails by 100.  Grants breath healing after resurfacing for any lost health due to drowning that lasts for duration of map.  Increase jump count by 1. Aura lost.|Wood|Incense smoke, bowls|
|Fire|3|Lit Red|"Aura of Fire Magick,\nburst with rage." Grants aura that recharges lava nails, rockets, and multi-rockets 1 per 0.5 secs, reduces ice and cold creature (e.g. snowmen) damage by 75%.|"Fire and Power!" Refills lava nails, rockets, and multi-rockets to max ammo.  Boosts rocket and multi-rocket max ammo by 50, and boosts lava-nails max ammo by 100.|Metal, lava pool|flames and braziers, but not on table structure|
|Blood|4|Dark Red|"Aura of Blood Magik,\nblood of the ancients courses\nthrough you!" Rapid healing aura. Heals nearby players and player followers 1 health every 0.3 secs. Recharges bloodcrystals ammo 1 oer 0.5secs.  Prevents and removes bleeding buffs.|"Overheal Bloodlust!" Grants maximum overhealth of 300, rots down like megahealth. Increases max normal health by 25.  Refills bloodcrystals ammo to max. Aura lost.|City floor and bricks, blood trough|Spikes and gibs|
|Spirit|5|Purple|"Aura of Spirit Magik,\nthe angels watch over you." Aura granted that recharges all mana rapidly, 1 per 0.2 secs for wand mana and elemental mana ammo.  Angelic protection, all damage taken reduced by 50% within aura.|"Protection of the Watchers!" 25% damage reduction for map duration|Marble, stainglass, purple pool|purple smoke, magic glitter, bubbles|

.

### `info_shrine`
Grants blessing when used and runs targets.
#### `style`
* **Type:** integer
* **If Set:** Choice between 0 through 5.  This changes the blessing granted according to the chart here.
* * 0 Earth
* * 1 Water
* * 2 Air
* * 3 Fire
* * 4 Blood
* * 5 Spirit
* **If Left Blank:** Defaults to Earth type.

#### `proj_limit`
* **Type:** float
* **If Set:** Specifies override projection radial distance for aura effects, magic sparkles will shoot at the player to form a sort of beam.  Only affects blessings that have an aura.
* **If Left Blank:** Defaults to 384.

#### `message`
* **Type:** string
* **If Set:** Specifies god name.
* **If Left Blank:** Defaults to `Cthulhu`.

#### `delay`
* **Type:** float
* **If Set:** Specifies time between aura effects taking place, such as healing.  Each instance applies effects by the amount of `cnt`.
* **If Left Blank:** Defaults to the following based on the `style` chosen.  Ideally, leave at the defaults since the effects are not customizable.
* * Earth: 0.3
* * Water: 0.5
* * Air: 0.5
* * Fire: 0.5
* * Blood: 0.3
* * Spirit: 0.2

#### `cnt`
* **Type:** integer
* **If Set:** Specifies amount to apply for each effect at each instance every `delay` seconds.  For example, healing effects will add `cnt` + `target.health` every `delay` seconds.  Only applies to entities affected by the aura.
* **If Left Blank:** Defaults to the following based on the `style` chosen.  Ideally, leave at the defaults since the effects are not customizable.
* * Earth: 1
* * Water: 1
* * Air: 1
* * Fire: 1
* * Blood: 1
* * Spirit: 1