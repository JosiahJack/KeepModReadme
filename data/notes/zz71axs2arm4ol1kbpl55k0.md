
These items provide protection to the player of various sorts, whether by replenishing health and armor, or providing some other protective ability against attacks or the environment.

### `item_health`
Adds to player's health up to max health.  Normal max health is 100, unless in Evil Mode which derives from Copper mod's modified Nightmare skill and has a limit of 50 max health.
* 25 normal if no spawnflag is set.
* 15 rotten if spawnflag 1 is set.
* 100 megahealth if spawnflag 2 is set.  Only megahealth can over-heal player past normal max health, up to 250 mega max heslth for multiple megahealths.  Rots down to normal health by losing 1 health per second.


### `item_healthvial`
Adds to player's health randomized 2 to 5 health.
The following entities redirect to this entity type:
* `item_healthgem`
* `item_health_potion`


### `item_armor1`
armorvalue: 100

armortype: 0.3

Green armor that provides 100 armor points (armorvalue) and protects against 30% damage (armortype).  The damage that would have been subtracted from health is what is subtracted from the player's armor points.  E.g., protects against 10 damage, lose 10 armor points instead of 10 health.  Formula: save = ceil(armortype * damage) in other words, 'health saved' = 'rounded up'(0.3 * damage).  Armor is reduced by up to the amount of armor left but no more.


### `item_armor2`
armorvalue: 150

armortype: 0.6

Yellow armor.  Set spawnflag 2 to use Blue model instead.


### `item_armorInv`
armorvalue: 200

armortype: 0.8

Red armor.  Contrary to what the "Inv" might make you believe, this armor does not provide "Invulnerability" but is close.