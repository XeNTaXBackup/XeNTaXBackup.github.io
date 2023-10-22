## Post #1
- Username: JackParadigm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 17, 2020 8:32 am
- Post datetime: 2020-04-17T18:35:45+00:00
- Post Title: How to Rip Models (with their Animations) from Console Game Roms/Isos

I'm working on making a small fan game project that involves certain videogame characters.

Although there are a few [now old-ish] programs I've come across from Googling that are capable of ripping 3D models from roms/isos via emulators, the problem is that I want those models' animations too. For example, although I can use a program to rip a model of Claude from GTA3, I also want to rip his animations for walking, running, etc.

To be more specific, I'm focusing on ripping models & animations just from Playstation games (PS1, PS2, PS3, etc.)

If this is possible, how do I go about doing this?
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-04-17T20:23:20+00:00
- Post Title: How to Rip Models (with their Animations) from Console Game Roms/Isos

> Reply from JackParadigm ↑Sat Apr 18, 2020 2:35 am at Sat Apr 18, 2020 2:35 am
>
> 
I'm working on making a small fan game project that involves certain videogame characters.

Although there are a few [now old-ish] programs I've come across from Googling that are capable of ripping 3D models from roms/isos via emulators, the problem is that I want those models' animations too. For example, although I can use a program to rip a model of Claude from GTA3, I also want to rip his animations for walking, running, etc.

To be more specific, I'm focusing on ripping models & animations just from Playstation games (PS1, PS2, PS3, etc.)

If this is possible, how do I go about doing this?

Models are possible by ripping with Emulators but animations are a much more difficult task, it depends on each and every single game.
For each of these:
PS1: ripping from this is fairly tricky because of the Z-Buffer issue present in Emulators, so unless you can find a workaround for it (I haven't personally) then it's totally possible to rip from it. 
PS2: ripping from PS2 is possible but it can bring some issues depending on your Rendering method: OpenGL, DirectX, etc. and the game itself.
For games such as Splinter Cell Double Agent on the PS2, the models and textures are ripped however they are slightly slanted or deformed, being ripped EXACTLY from the perspective of your camera ingame, forcing you to waste time repairing each individual mesh.
PS3: I haven't tried ripping from PS3 yet, but I assume it's alot more reliable than the other two. Ripping models from Emulators is pretty crappy.
Dolphin: The best emulator for ripping meshes: the UV's will be preserved and the models are not deformed!
CX-BX Reloaded: Depending on the title you're ripping from or rendering method, you can get models in T-pose most of the time, however the UV's are corrupted in most cases.

If you want to rip models straight from the game files you're going to need help with scripts to rip the models from said files. 
(Which can be insanely difficult for some games as there is no documentation on their file extensions and some are very lengthy tasks - decompressing level files, decompiling those files and barely then can you get the models/anims then you need to write the script for importing the mesh/bone data and animation data.)
## Post #3
- Username: JackParadigm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 17, 2020 8:32 am
- Post datetime: 2020-04-30T21:11:26+00:00
- Post Title: How to Rip Models (with their Animations) from Console Game Roms/Isos

I see. I'll still try to see how far I can go in ripping and fixing models via programs like Blender or Maya once I've ripped them. However, what program is best for ripping models from each of these Playstation emulators?

In addition, is it possible to rip models from PS4 games? I know PS4 emulators are still in experimental stages, so it won't be as simple as the previous console emulators, but is there a way to decompile the game file (I.E. iso/rom/etc) and find the model I need without needing an emulator?
