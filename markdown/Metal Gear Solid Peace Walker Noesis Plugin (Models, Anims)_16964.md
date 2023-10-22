## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2017-09-03T00:05:38+00:00
- Post Title: Metal Gear Solid: Peace Walker Noesis Plugin (Models, Anims)

I've made a noesis plugin to can be used to view models and animations from the game Metal Gear Solid: Peace Walker. Textures will be applied automatically given that the TXP files are in the same directory as the MDP file that needs them. If you have extracted the game files properly it should already be set up this way. There are some models that don't have a vertex buffer and I haven't figured out how to parse those yet, an error will be shown if you run into one of them. Source code is also available.

[https://github.com/Jayveer/MGS-MDP-Noesis/releases](https://github.com/Jayveer/MGS-MDP-Noesis/releases)

In order to view animations you must select (Prompt for Motion Archive) in the menu, when you select a model file after this it will ask to open an accompanying mtar file. If anyone has made a C++ Noesis plugin before and knows of a better way to do this that would be great.

To get to the model files you can use the Archive Extractor I posted here [viewtopic.php?f=10&t=23344](https://forum.xentax.com/viewtopic.php?f=10&t=23344)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-09-06T19:44:58+00:00
- Post Title: Metal Gear Solid: Peace Walker Noesis Plugin (Models, Anims)

> Reply from JayK
>
> I've made a maxscript to import models from the Portable Metal Gear titles into 3ds max. Supports mesh,bones,skinning and applys textures if you have the textures with their hashed name in a 'textures' folder. Some files seem to be using a compressed vertex buffer and there isn't support for that yet. If anyone can contribute that'd be good.

https://github.com/Jayveerk/Metal-Gear- ... table-MDP-thanks a lot, JayK. I'll try it out
## Post #3
- Username: Casedey
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Aug 20, 2011 1:27 pm
- Post datetime: 2017-09-10T16:04:56+00:00
- Post Title: Metal Gear Solid: Peace Walker Noesis Plugin (Models, Anims)

But how can i get to the .MDP files?
Is there a tool to extract them?
## Post #4
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-02-13T17:09:18+00:00
- Post Title: Metal Gear Solid: Peace Walker Noesis Plugin (Models, Anims)

I've updated this to a Noesis plugin which can be used to view models and animations.
