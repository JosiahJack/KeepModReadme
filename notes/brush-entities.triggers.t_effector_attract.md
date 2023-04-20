---
id: ldln4vkmzi2jnnqt2b6yhfj
title: T_effector_attract
desc: ''
updated: 1681956463333
created: 1681955027634
---
> Attributions: Frank Condello (aka pOx), Khreathor for the extras_r5 update

Particles touching this trigger are attracted to it's center. Can also repel
particles with negative strength. This works best with particles that have a
low gravity setting.

Since this is a part of the extras_r5 Emitters system, please refer to system
detail here: [[brush-entities.triggers]]

### Key/Values
- "speed"...Strength of the attraction
- "cnt".....Percentage of original particle velocity to diminish
- "count"...Override the default 100% of particles affected (valid: 1-99 i.e 50
            affects roughly 50% of the particles)
- "targetname"	Can be enabled/disabled

### Spawnflags
-  1 - "START_ON"......Start in enabled state even if targeted

- 16 - "TANGENTIAL"...Particles turn to face new direction