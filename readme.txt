By Hyphen-ated
version 0.2

This is a patch to remove music from The Legend of Zelda: A Link to the Past.
It was developed for the Japanese 1.0 version, and has also been tested to 
work on the USA version. The CRC32 checksum of the base ROM should be 3322EFFC
or 777AAC2F.

This patch was added to the randomizer at https://alttpr.com/, so
if you're playing rando, you can just use the option there for no music;
you don't need to apply this patch yourself.

How to use: apply the .ips file to your rom using the program "Lunar IPS"
(or another IPS patcher of your choice). Then when you play, there will be
no music.

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

