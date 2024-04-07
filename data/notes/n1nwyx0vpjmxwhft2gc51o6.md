
There are two types of entities in Quake, brush based and point based.  Point entities are placed as empty point objects in the level editor and compiled into the map with nothing more than the data about them.  These entities, like all entities, are actually code functions of this form:

`void() entity_name_here = {  //Code to make things happen };`

When placing an entity in the level editor of the same name as the function, `entity_name_here`, then this function will have its code executed when the level starts.

Anything the QuakeC code can do, an entity can do, because they are essentially one and the same.  This leads to powerful applications for good by following documentation and properly applying .fgd values and specified ranges, but also powerful applications for evil by doing _maphacks_ by treating unexpected functions as entities.  If you use a maphack, you do so with no support for resulting bugs or unexpected behavior, fun or otherwise.

> Technical Note: The normal world is itself a point entity called `worldspawn`.
(See [[general.world]]).

* [[point-entities.ambients-and-sound-effects]]
* [[point-entities.effects-and-decorations]]
* [[point-entities.logic-and-entity-state-system]]