> Attributions: Frank Condello (aka pOx), Khreathor for the extras_r5 update

Applies friction to particles, slowing them down (negative values speed
particles up).

Since this is a part of the extras_r5 Emitters system, please refer to system
detail here: [[brush-entities.triggers]]

### Key/Values
- "speed"		Amount of Friction (max 100 = dead stop, negative values can go
                further though -200 etc.)
- "count"		Override the default 100% of particles affected (valid: 1-99
                i.e 50 affects roughly 50% of the particles)
- "targetname"	Can be enabled/disabled

### Spawnflags
-  1 - "START_ON"......Start in enabled state even if targeted