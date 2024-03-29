---
id: ytz7elozzr8x1p6yvxte4iv
title: Health and Damage
desc: ''
updated: 1681958009010
created: 1657647630774
---
# Player Health
## Player Health Overview
Player health starts at 100.  Death occurs when reaching 0 health and a message
displays at the top of tue screen for why you died; useful to see the name of
what killed you.

`TIP: Press console key (default is tilde ~, but may be ^ ° on German
keyboards) to access the console to read messages that you may have missed.`

Maximum player health is typically 100.  There are exceptions:
* The megahealth powerup raises health over the normal maximum up to a
  _megamax_ value of 250.
* Evil Mode lowers max health to 50 but does not affect megamax.

## Damage to Player
Typically damage dealt is one for one:  1 damage removes 1 health.  Damage is
calculated internally as a fractional floating point value subtracted from
health and the resultant health is rounded up to the nearest whole value. The
reason for fractional calculations is due to armor resistance being calculated
as a percentage.

Players can receive various other items in addition to armor that affect how or
if they are damaged and by what kinds of damage.  See [[items.protection]] for
more details.  Damage from environmental sources will ignore armor, for
instance lava, slime, and drowning will affect only a player's health and not
their armor.