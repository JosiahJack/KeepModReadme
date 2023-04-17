---
id: df4dfow551m8x65aulz8u4r
title: Requirements
desc: ''
updated: 1657648142499
created: 1657647917022
---
This lists the requirements that this mod aims to fulfill.  Anything that does not meet these requirements is a bug to be fixed at some point.

* Load original maps from included mod without any listed errors in the console.
* Have original maps from included mods playable from start to finish without any noticeable errors.  Minor console prints, warnings, and errors during playthrough are acceptable so long as the map is playable without any noticeable negative consequences by the player.
* Have all conflicting features from multiple mods that include same named entities as settable options.
* Any conflicts in naming are resolved without errors or warnings.
* A suitable default for any conflicting features or named entities, e.g. monsters with same names, shall be chosen with deference to the most recent mod unless an older mod is more fun or more feature complete, then it shall be the default.
* Have all settable options from mods available, except where such is impossible to do at scale for all monsters or would be impossible to be consistent at scale or would be unnoticeable by most players if implemented or not.
* All monsters should be placeable as-is without needing special setups.  A special setup would be requiring a monster to be targeted, requiring any helper entities such as paths or teleport locations or precaching minion setup entities.
* Any incorrectly set variables shall fail gracefully, printing a warning without crashing, without exiting to console, and without deleting the entity.  If an entity would have been removed in an error state in other mods, here Keep shall preserve the entity and set it up in a default state rather than remove it.
* All variable ranges shall be given in the documentation (this wiki).
* All variable types shall be given in the documentation.
* All variables' defaults shall be listed in the documentation.  If a default is not listed, it shall be assumed to be 0.
* Any time the phrase "not set" or "off" is used, it is assumed to have value 0 unless otherwise specified, and any otherwise cases shall be listed specifically.
* Where helpful or useful, even if default is a standard engine default such as 0, a description shall be given for what that default does.
* Full credit shall be given for each included mod.  This shall be done at a minimum by including the readme as it was previously included within the credits folder.
* Trivial single file readmes will be renamed to "readme_modname" replacing the 'modname' portion with the actual name of the mod for organizational purposes.  Any mod with nontrivial readme shall have such go, unmodified and not renamed inside a folder named with the mod's name and inside credits folder.
* Mods who were only ever included with maps shall have the particular release package's readme included and renamed acording to the above method.  Mods without specified names will default to the release package's name.