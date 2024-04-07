>Moving water volumes - honest and for true.  --extras_r4

A brush entity that behaves like normal water.  Has capability of acting like a
func_door and draining or flooding an area with complete swimmability and any
liquid effects if it is slime or lava.

Capable of having a current.  If brush is very shallow, may need spawnflag 16
or the current will be too weak.  Set current by using `mangle`.

>"An easy way to make rising/falling water, but
[[point-entities.func_watertrain]] is much more flexible (it can do anything
func_water can do, and then some, but it's more work to setup)"

|Key|Description|
|---|---|
|"watertype"|-3 = water, -4 = slime, -5 = lava
|"height"|Number of units to move (negative is down).
|"speed"|Speed used when it moves to "height" position.
|"speed2"|Speed used when moving back to original position (pos1). Same as "speed" if not defined.			
|"wait"|Wait before returning to original position -1 = stay at pos2 until triggered again.
|"noise"|Path to the WAV played when the water moves from pos1 to pos2 (should be looped).
|"noise1"|Path to the WAV played when the water moves back to pos1 from pos2 (should be looped).
|"noise2"|Path to the WAV played when the water stops moving.
|"mangle"|Direction & speed of current.  E.g. `100 0 0` would be in positive x direction with speed of 100.
|"drag"|Drag on player when water is moving (0 is no drag, 100 if full drag)
|"cshift"|Custom RGB+I colour shift. Automatically set by watertype to match normal liquids if ommited.
|"targetname"|Can be triggered (just keeps bobbing between pos1 & pos2 otherwise).
|"target"|Activate this entity after moving (top and bottom)

.

|Spawnflag|Name|Description|
|---|---|---|
|16|Ease Undercurrent|Normally, the deeper you are, the more you are affected by current.  This reverses that, making current is stronger at the surface.|

.


## GETTING THE INSIDE FACES TO DRAW PROPERLY:

### METHOD 1:
Use a custom QBSP util with func_water support (this does NOT require an 
engine mod). Just use ericw's [qbsp](https://ericwa.github.io/ericw-tools/)
with _mirrorinside 1.

eQBSP v1.0b for MacOS supports this - [eQuake Utils (852kb, MacOS 9 & MacOS X (PPC) compatible)](http://quake.chaoticbox.com/downloads/equakeutils.sit).  

### METHOD 2 (hackaround):
Add thin (1 unit) brushes for visible edges, but make sure these brushes
DON'T touch the main volume (1 unit away), or the face will be consumed by
QBSP!  You can disable mirroring in eQBSP per-entity by setting
the "_nomirror" key to a non-zero value, and use "METHOD 2" to backface the
problem brush.  Skip textured surfaces may help in some cases.  Older compilers
may need *waterskip.  This whole method of course assumes it doesn't move,
though so usually just use method 1 and ericw's
[compilers](https://ericwa.github.io/ericw-tools/).

### Other Notes
Avoid butting func_water surfaces right up against solid geometry or you'll get
z-fighting artifacts where real water wouldn't (extend "hidden" edges into a
solid wall).

Unavoidable differences between func_water and real water:
1. Underwater surfaces don't warp
2. Surface is always opaque

See credits folder for extras_r4 original docs if interested in a bit of history.