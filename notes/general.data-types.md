---
id: 7qxoxks6btlctd9mkuf8ao4
title: Data Types
desc: ''
updated: 1657650316662
created: 1657650293018
---
Data types are handled somewhat oddly by the game code written in QuakeC.  Since these values matter when entering numbers or text onto `key|value`s in a map editor, I am providing this for reference and to help avoid typical pitfalls. Please note that the Readme Data type is how the variable is intended to be used and now how it is actually handled by the code.  Most of these can have floating point values assigned to them, but the behavior is undefined and is not recommended.

|Readme Data Type|QuakeC Type|Initial Value|Range/Values|Notes|
|------------|-----------|-----|-------|-----|
|boolean|float|0|0,1|Only 0 is false, any other value, including negatives is true and treated as a value of 1 in QuakeC|
|trilean|float|0|-1,0,1|This is not technically a data type as far as the QC is concerned.  Merely an integer used like a 3 value variable as an aid to the mapper to force certain conditions by using -1.|
|integer|float|0|-8388608 to 8388608|Whole numbers used for countable quantities or for bitmasks.  Assigning a fractional value is possible, but would mess up the bits on a bit mask and might provide a wrong count, such as for `trigger_counter` which could break map progression.|
|float|float|0|-8388608.0 to 8388608.0|Numbers capable of having fractional portions after the decimal separator.  Technically should be able to go higher in maximum value using exponents, but QuakeC isn't exposed to the exponent portion of floats.|
|string|string|""|abc...123...etc.|These characters require backslashes before them: `\n` for newline, `\'` for single quote, `\b` for "bold" orange text.|