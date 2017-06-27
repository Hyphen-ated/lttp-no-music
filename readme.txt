By Hyphen-ated
version 0.2

This is a patch to remove music from the 1.0 japanese version of Zelda LTTP.
It's compatible with the randomizer at http://vt.alttp.run/

How to use: get a randomized rom, then use the program "Lunar IPS" (or another
IPS patcher of your choice) to apply this .ips file to the rom. Then when you
play the rom, it will have no music.

It works by editing the song data files that are interpreted by the SPC700
sound coprocessor. Wherever there is a "volume" (ED byte) or "volume ramp" (EE
byte) instruction, it changes it to set the volume to zero.

It would be more clever to make one small change to the code that runs on the
SPC, but I struggled to figure out that code, and making this data change was
not too difficult. The music editor in Hyrule Magic was very helpful for
figuring out what to change.

In the 0.1 version of this project, it worked by a completely different
mechanism: the main SNES CPU was prevented from sending "start new song"
messages to the SPC. This had a major problem in that it saved several seconds
every time you picked up a crystal, because the length of the crystal pickup
song defined how long you were frozen in place holding the crystal.

The current version does not have this crystal timing defect, nor any other
problems that I know of.

