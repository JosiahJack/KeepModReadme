Triggers are brush based entities that are invisible and non-solid as far as
allowing all objects to pass through them.  Whenever an entity would have
touched it if it were solid, then it causes its `touch` function to run.  This
is used to trigger events.  This could be as mundane as the typical target IO,
perform a special action, or acting upon the entities that touched it.

There is no real limit to what behavior a trigger can have or on who or what
can trigger it.  Different triggers are normally configured to be either player
only, monster only, projectile only, or some combination.

---

## Extras Emitters

> Attributions: Frank Condello (aka pOx), Khreathor for the extras_r5 update

Specialty particles and emitters that react to physics, and their affectors.

Particle systems with QuakeC - packet overflows made easy!
These were modeled after particle systems in high-end 3D apps, they are not
the most user friendly entities around...

EMITTER ENTITIES: func_emitter, func_emitter_volume
EFFECTOR TRIGGERS: t_effector_destroy, t_effector_push, t_effector_gravity,
t_effector_trubulence, t_effector_attract, t_effector_friction

Emitters generate a "particle" (either a .spr, .mdl or .bsp) and toss it in
a direction between the set angle limits. They can use an optional "death"
model to simulate anything from rain, falling rubble, blasts of flames,
forcefields, whatever...

Effectors change the behaviour of particles that touch them (the emitter 
must have the "USEEFFECTORS" spawnflag set).  Emitters can be attached to a 
func_train_ext, for some really neat crap :)

Don't go too nuts with these, stay away from the built-in sounds for high
frequency emitters (use fx_sound instead) and just use common sense (you 
don't need a gib fountain around every corner!).  Fine Tronyn...do whatever!

There are a LOT of options - these are really generic and need to be
tailored to specifc purposes.

The lifespan of animated particles may not be exact - it will always fall on
a multiple of the framerate (this usually isn't a problem, since framerates
are typically much smaller than lifespans) but you should be aware of this
limitation.

Particles won't "die" when they hit another particle - this is on purpose.

Particles don't register a touch on water, but a t_effector_destroy trigger 
can be used to simulate this. Set KILLINFWATER to have them die in 
func_water volumes.

ANGLES EXPLAINED:
The angle limits may take a while to get used to, but it's a really powerful
way to control the direction and spread. Start by setting just v1 and h1 to
get a tight stream in the general direction, then adjust v1/v2 and h1/h2 to
within a few degrees (plus and minus) of the original value to increase the
spread for a cone-shaped fountain. Ommit either h2 or v2 for a fan shaped
emission, or set v1=1 v2=360 h1=1 h2=360 for a fire-works style spherical
burst.

The following diagram visualizes the horizontal and vertical angle relationship.

![Emitter Angles](assets/img/emitter_angles.gif)

When viewing a map from the top, an H angle value of 270 points up, and
moves clockwise, making right 360 (or 0), down 90 and left 180. Same goes
for the V angle when viewed from the front.

The particle spread is always contained from the first angle (h1/v1) to the
second angle (h2/v2), going clockwise. So h1=10 h2=350 is NOT the same as 
h1=350 h2=10. (the first is a near circular spread, while the second is a
tight 20º fan shaped spread).

Also note that although 0 would normally be a valid replacement for 360, you
should use a range of 1 - 360 as a value of 0 is simply ignored (though this
may be desirable in certain situations).