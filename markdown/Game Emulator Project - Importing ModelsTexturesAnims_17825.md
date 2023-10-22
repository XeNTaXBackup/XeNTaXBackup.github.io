## Post #1
- Username: hanman5000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 15, 2018 10:49 pm
- Post datetime: 2018-03-15T15:16:32+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

Hi guys,

New member here, hope everyone is doing well. This looks like a really nice community!

I'm posting here because I'm working with a team to create an emulator for the popular game Dekaron. Unfortunately the official version is dying due to neglect, but there are many people who really love this game and don't want it to die. 

We're building the emulator in Unity and have a bunch of basic stuff done (chat, NPCs, quests, character stats, item equips, party, and guilds). 

We need help with is imorting Dekaron's models/textures/texturepacks/animations into a Unity-compatible format. 

I read this post and was able to eventually import the 3D model but had no idea on how to get the textures/animations imported: [viewtopic.php?f=16&t=9947&view=previous](http://forum.xentax.com/viewtopic.php?f=16&t=9947&view=previous)


Info
[*].mesh -- Dekaron uses .mesh for 3D models
[*].anim -- these are the animation files
[*].tpack -- these are a text file that has a list of textures for a specific model 
[*].dds -- these are the textures, they can be easily renamed to .png 
[*].skel -- skeleton

DOWNLOAD EXAMPLE FILES (.mesh, .skel, .tpack, .dds, .anim): [https://drive.google.com/file/d/1P1-09S ... sp=sharing](https://drive.google.com/file/d/1P1-09S-buQhcUrFSINX668gY7eeK0mAR/view?usp=sharing)

Any help at all is appreciated. If you think that this is something that you can do, we are looking for someone and will pay well for time spent helping us with this project.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-15T16:02:29+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

Wait, you are trying to create the game on Unity from ground up? That is insane imo.

Normally mmo emulators are network emulation. You would keep the client of the game, and just code the server which will receive/send packets from/to the game client. Maybe you would need to modify the client a little to make it connect to your server but that is all.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-15T16:54:21+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

> Reply from hanman5000
>
> We need help with is imorting Dekaron's models/textures/texturepacks/animations into a Unity-compatible format.before you transform any 3D format into another u usually need to understand your source format, especially for anims it's hard to do.

You should start with getting the skeleton (bone names, matrices (rot, trans) ).
Looks doable, since alo.skel is small and has about 23 bones only (plus weapon "attachments?").

> I read this post and was able to eventually import the 3D model but had no idea on how to get the textures/animations imported:As I said, amins is the harder part; deal with the skeleton first.
For the texture; I don't know what you're talking about. drag the dds onto Noesis and you're done:



alo_equ_c007-mesh.jpg (73.05 KiB) Viewed 107 times


There's some superfluous faces, though, so the python script might need some correction.
## Post #4
- Username: hanman5000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 15, 2018 10:49 pm
- Post datetime: 2018-03-15T17:42:56+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

> Reply from akderebur
>
> Wait, you are trying to create the game on Unity from ground up? That is insane imo.

Normally mmo emulators are network emulation. You would keep the client of the game, and just code the server which will receive/send packets from/to the game client. Maybe you would need to modify the client a little to make it connect to your server but that is all.

Yes, we are trying to create the game on Unity from the ground up. I know it sounds a bit farfetched, but we already have the hard stuff down and the base is already built. 


> Reply from shakotay2
>
> hanman5000 wrote:We need help with is imorting Dekaron's models/textures/texturepacks/animations into a Unity-compatible format.before you transform any 3D format into another u usually need to understand your source format, especially for anims it's hard to do.

You should start with getting the skeleton (bone names, matrices (rot, trans) ).
Looks doable, since alo.skel is small and has about 23 bones only (plus weapon "attachments?").
I read this post and was able to eventually import the 3D model but had no idea on how to get the textures/animations imported:As I said, amins is the harder part; deal with the skeleton first.
For the texture; I don't know what you're talking about. drag the dds onto Noesis and you're done:
alo_equ_c007-mesh.jpg
There's some superfluous faces, though, so the python script might need some correction.

Thank you for the informative response. Which python script did you use with Noesis? 

Also, as for animations, the game has CSV files for animations, perhaps they can be some help? Example for that same character: [https://pastebin.com/fZPu6kDA](https://pastebin.com/fZPu6kDA)
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-15T17:55:43+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

Have you tried szkaradek's blender script ([viewtopic.php?p=100000#p100000](http://forum.xentax.com/viewtopic.php?p=100000#p100000))?

He wrote that it supports skeleton and animation.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-15T18:31:48+00:00
- Post Title: Game Emulator Project - Importing Models/Textures/Anims

> Reply from hanman5000
>
> Which python script did you use with Noesis?the one from deltaone which is based as he stated on the blender script from Szkaradek123

This is how it's looks when using Mariusz' script:



aol_equ.jpg (225.63 KiB) Viewed 92 times


(yeah, pretty much less skin, this is like proper girls cloth themselves  )
Though I'm a little bit confused. Is this really the same texture?
