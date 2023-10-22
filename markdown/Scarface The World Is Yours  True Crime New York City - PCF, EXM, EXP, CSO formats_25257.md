## Post #1
- Username: WDMv2
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 26, 2018 11:41 am
- Post datetime: 2022-04-15T21:51:07+00:00
- Post Title: Scarface: The World Is Yours / True Crime: New York City - PCF, EXM, EXP, CSO formats

I'm asking for assistance on the following file formats:

a) .PCF
b) .EXM
c) .EXP
d) .CSO

The two games that peaked my interest are:

1) Scarface: The World Is Yours (PC)
2) True Crime: New York City (PC)

A) I cannot find much of anything useful on .PCF file formats. Only thing I can take from them is that they control the models of the game as swapping the file's name will replace the player character with the one associated to that file name. I've tried exploring with a hex editor but to no avail. Nothing helpful.

B) .EXM and .EXP are complete mysteries. I see someone tried to ask about this particular question once before on XENTAX but the thread went dead. Hopefully someone can provide me with some info and I can make something of it. I found them in the VEH folder of TC: NYC (PC). They are found with a .H header file so they may have some connection.

C) Lastly, .CSO. This is located in the folder of SCRIPTC under the Scarface: TWIY (PC) game archive, specifically, CEMENT.RCF. Observation using a hex editor reveals some readable ASCII lines but other than that, it's a mystery. May have something to do with the game's internal scripts.



What I would like is any information or links that can help me either edit these files or view them more clearly. All I have to go by now is unintelligible computer babble. Appreciate any help anyone can give me. IK that these are very old games but I tend to revisit older games I've previously enjoyed playing to hone my RE and modding skills.

FILES (All File Extensions Failed to Attach):
[.PCF] (TC: NYC) ([police_upgrades.pcf](https://www.mediafire.com/file/4933dgez4p6qysb/police_upgrades.pcf/file))
[.EXM] (TC: NYC) ([Vehicles.exm](https://www.mediafire.com/file/auu7jotl8t4hbnq/Vehicles.exm/file))
[.EXP] (TC: NYC) ([Vehicles.exp](https://www.mediafire.com/file/hw89t07m3ia5r4n/Vehicles.exp/file))
[SOLVED][.CSO] (Scarface: TWIY) ([character.cso](https://www.mediafire.com/file/c362ylrcc70oujh/character.cso/file))



EDIT #1:
-thanks to one user on Xentax, I now know what .CSO is. It's related to Torque3D game engine. It is indeed a compiled script. You must use BrokenFace to decompile it. Even then, the functions are obfuscated. Your best bet afterwards is to use a de-obfuscator or you're mostly SOoL. I will update as I find more info. Since I can't do "strikethrough", I'm leaving it anyways, but it's been solved.

[BrokenFace .CSO Decompiler](https://github.com/sulzbals/BrokenFace)
[.CSO Reference](http://wiki.xentax.com/index.php/Scarface:_The_World_is_Yours_CSO)
