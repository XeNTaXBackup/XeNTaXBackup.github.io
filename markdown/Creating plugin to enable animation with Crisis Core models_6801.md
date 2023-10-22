## Post #1
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-06-18T09:58:00+00:00
- Post Title: Creating plugin to enable animation with Crisis Core models?

While I presently don't have the skill, or know-how to do so, does anyone here want to work on creating a plugin that would allow Noesis to understand the animation data in Crisis Core, so that models (and perhaps any map/level animations, unless that's handled by the game exclusively) could go through their various animations like the Dissidia models can?

[viewtopic.php?p=50780#p50780](http://forum.xentax.com/viewtopic.php?p=50780#p50780)

> Reply from MrAdults
>
> Well, most likely that data is in the mot files that Noesis extracts from the game's package. I haven't even looked at them myself yet, so I have no idea how hard it would be to get at the data. But if you are not familiar with the process of reverse-engineering animation data, you probably aren't going to have any luck with it. If you are, well, you can get a copy of Microsoft Visual Studio 2005 Express Edition, load up a Noesis plugin (solutions and projects are included with Noesis in pluginsource.zip) and modify it to do what you want. The IQM plugin demonstrates how to get animation data to Noesis, although it does it in a somewhat unusual manner. If you wanted to feed pure animation data back from your plugin instead of model+animation data, you would use rapi->Noesis_AllocModelContainer(NULL, animData, 1); instead of the typical rpgConstructModel interface.
## Post #2
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2014-06-13T01:18:24+00:00
- Post Title: Creating plugin to enable animation with Crisis Core models?

So with the trailer for FFVII G-Bike ([http://www.youtube.com/watch?v=C3KKH9zB59Y](http://www.youtube.com/watch?v=C3KKH9zB59Y)) clearly using a bunch of Crisis Core assets, I figure now is a good time to bump this topic in hopes someone might be interested?
## Post #3
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-06-20T19:29:03+00:00
- Post Title: Creating plugin to enable animation with Crisis Core models?

Since the original filenames are lost, it's hard to tell what goes with what, which is probably why nobody has ever looked into it.

The animations appear to be in the .mot files that noesis outputs, but they aren't specifically for animation. There's sound effects in there as well, in the SCD format. If you have a look at file8623.mot, that's one for Zack. Contained in there is sound effects (probably footsteps) lang (subtitles?) and what looks like 2 animations. Even then they are inside ATEL files.

I don't see anything in there for cutscene models though, everything just seems to be playable only, so Zack, monsters, bosses and magic are the only things there.

Actually, looking at a memory dump, the original names may be able to be dumped. I'm seeing lines of text like:

host0://crisis/proj/chr/bin/motion/zack_s12/sp_angeal1_a.mot
host0://crisis/proj/chr/bin/motion/zack_s12/sp_tian1_a.mot
(These are not links, don't click them)

They could easily just be hashed in a similar way to dissidia's filenames.
