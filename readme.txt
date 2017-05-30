By Hyphen-ated
version 0.1

This is a patch to remove music from the 1.0 japanese version of Zelda LTTP.

How it was made:
The addresses $0132 and $012C are involved with controlling the music.
Anywhere that the game was setting a value to one of those addresses,
I changed it to set it to zero instead, by doing the following 
byte pattern search & replace operations:

8d 2c 01 -> 9c 2c 01
8e 2c 01 -> 9c 2c 01
8d 32 01 -> 9c 32 01
8e 32 01 -> 9c 32 01