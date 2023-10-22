## Post #1
- Username: Yretenai
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Jan 28, 2020 11:39 pm
- Post datetime: 2020-06-13T22:35:57+00:00
- Post Title: Lumberyard ACTOR/MOTION Plugin for Noesis

Loads .ACTOR and .MOTION files.

You can set the extracted game folder in the tools submenu. When you have an actor model loaded, you can right click a motion file to load it to the current actor. When double clicking a motion file, it'll ask you for the actor file. It'll also ask you for the material file when you have the extracted game directory set. 

Current Version: 1.0.6 (Dragon 1.0.3)
Download here: https://github.com/yretenai/dragon_noes ... yard-1.0.6
Shatterline: https://github.com/yretenai/dragon_noes ... ard-1.0.6b

Place the dragon_lumberyard.dll in noesis/plugins.

It also loads streamed DDS textures and CGF models, so there's that. 
I might disable CGF loading eventually, if anyone ever makes a CE3/CE4 CGF loader.

If Noesis crashes while loading a model, don't send an error report as it's a crash with the native plugin and not Noesis.

Tested with:

 Crucible (RIP)


There is a chance a game would compile materials to binary, rather than an XML file. But right now the only game that uses "new" Lumberyard features is Crucible which uses XML files.

Sidenote: PAK files are zip files with extra data, you can just open them like normal zip files though.

This is kinda useless now lol.
