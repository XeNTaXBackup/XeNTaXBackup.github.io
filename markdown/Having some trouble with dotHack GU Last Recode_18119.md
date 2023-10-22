## Post #1
- Username: hi im daft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 21, 2018 7:13 am
- Post datetime: 2018-05-20T23:19:02+00:00
- Post Title: Having some trouble with dotHack GU Last Recode

Currently, I'm trying to rip some texture files from Last Recode to do an upres on them (they look like poop for a current-day PC release, they make it clear they just ripped the textures from the PS2 version without doing anything to them). Thanks to [a thread made last year](http://forum.xentax.com/viewtopic.php?f=16&t=16010&hilit=+css), I was able to find SOME tools that KIND OF work on Last Recode, but don't seem to be able to do exactly what I need.

Well, to start (if you're not familiar with the game), there are clusters of VERY large .cpk files that contain all the models/textures/meshes/etc for the game. Using CriPakTools, I was able to extract the contents of the cpk files, and in turn got .CCS files. Using the tools from the thread I linked above, I'm able to read the CCS files, but it all looks like model and animation data, no actual textures or other images, which is a problem. I'm not sure if it's the fault with CriPakTools not decompressing the CPK files properly, or if it's the CCS tools here that aren't able to read the textures because of some file format change.

Either way, I would very much like some assistance from anyone that can help. I've spent a couple days digging into this already, so if you need any additional info, lemme know.

EDIT: A bit of additional clarification, again for those that may not be familiar with the games, the tools from the other thread were made for the PS2 release of this game. However, much later last year, the game got an updated re-release on PC, which is what I'm trying to crack open and modify.

EDIT2: Actually, after playing with the tools a bit more, I was able to find (some of) what I needed. Turns out some of the CCS files ONLY contain animations and model info, while others contain textures and such, I just had to find which is which. I get the feeling that some stuff may still be hidden though, as so far I've only been able to find textures for the party characters. As for terrain, monsters, NPCs, etc., I still haven't found any for those, so they might be in a different file structure maybe?

EDIT3: OK, progress log, those textures I found earlier seem to be for the main characters in in-engine cutscenes only, not their standard models. Certain cutscenes use more detailed posing and facial animation, so they have separate files for those apparently. OK. Well, at least it's something. Going to try to find the standard model textures now, if I can.
