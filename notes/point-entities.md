---
id: n1nwyx0vpjmxwhft2gc51o6
title: Point Entities
desc: ''
updated: 1657648164216
created: 1657648161875
---
There are two types of entities in Quake, brush based and point based.  Point entities are placed as empty point objects in the level editor and compiled into the map with nothing more than the data about them.  These entities, like all entities, are actually code functions of this form:

`void() entity_name_here = {  //Code to make things happen };`

When placing an entity in the level editor of the same name as the function, `entity_name_here`, then this function will have its code executed when the level starts.

Anything the QuakeC code can do, an entity can do, because they are essentially one and the same.  This leads to powerful applications for good by following documentation and properly applying .fgd values and specified ranges, but also powerful applications for evil by doing _maphacks_ by treating unexpected functions as entities.  If you use a maphack, you do so with no support for resulting bugs or unexpected behavior, fun or otherwise.

* [Ambients and Sound Effects](https://github.com/JosiahJack/KeepModReadme/wiki/Point-Entities:-Ambients-and-Sound-Effects)
* Decorations and Visual Effects
* [Logic and Entity State System](https://github.com/JosiahJack/KeepModReadme/wiki/Point-Entities:-Logic-and-Entity-State-System)
* Specialty