## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-30T02:56:50+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Well folks, here's nearing the finals of my extensive project, and as such, things get much more complex. We're down to the 3d files. In question are the 3D models of the Overlord series. The format remains consistet through the series as "PRP". I have no reason to believe the format varies between the games, as they all run on the same engine. The only thing is, I'm not sure if they contain the required textures for the models or not. Anyway, I'd like to see a model viewer for these, possibly with animations, but if that's too much to ask, I'll settle for a simple model viewer with textures or a method to export them into something more universal. Hopefully they won't be as difficult to unravel as some of the other files my project has demanded.

Also, I'm aware there is an Overlord series topic in game archive research, however, I believe these to purely be model files and not straight-up archives.

And so we continue on.
Here is a link for the prp files I need most decoded.
[http://www.sendspace.com/file/chbqhn](http://www.sendspace.com/file/chbqhn)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-31T01:37:30+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

[http://ps23dformat.wikispaces.com/file/view/olelf.blend](http://ps23dformat.wikispaces.com/file/view/olelf.blend)

In the files you uploaded the meshes are named in the files and always begin with:
"MESH\" followed by a number and then a few rows of hex followed by
4Byte Integer--The Number of Vertexes
53ByteArrays--4ByteFloatVertexes(X,Y,Z) 4ByteFloatNormalMappings(X,Y,Z) 4ByteFloatTextureMappings(U,V) Unknown4ByteInteger#1 Unknown4ByteInteger#2 Unknown1ByteInteger Unknown4ByteFloat#1 Unknown4ByteFloat#2 Unknown4ByteFloat#3 
.......
"MAT\"
.....
2ByteIntegerTristrips
## Post #3
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-31T02:34:30+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Oh thank you for your reply.

Just note these are for the PC versions.

Is there any way to view them with textures?

I assume what you've supplied is one of the files exported in the format of blender?
## Post #4
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-31T10:57:55+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

The model I uploaded will display with textures (it is the elf warrior body) and normal mapping, but you have to export it to 3d studio max, or Ogre3d because my models I extract with a hex editor do not display right in Blender for some reason.
I'm not a programmer at all, I might learn this summer so I can make a proper script, the way I do it right now is using Microsoft Excel and Microsoft Word, with the Find and Replace and function from the Hex models from the files.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-31T19:27:09+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

> Reply from FurryFan
>
> The model I uploaded will display with textures (it is the elf warrior body) and normal mapping, but you have to export it to 3d studio max, or Ogre3d because my models I extract with a hex editor do not display right in Blender for some reason.
I'm not a programmer at all, I might learn this summer so I can make a proper script, the way I do it right now is using Microsoft Excel and Microsoft Word, with the Find and Replace and function from the Hex models from the files.
Oh, just grate news. So maybe weight data support in plans?
## Post #6
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-31T20:17:59+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Perhaps you could ask one of the fellows her to assist you in making a conversion script if you're willing to divulge your methods. I'd like to know a detailed process of conversion so I can convert these models to be properly displayed, since my project requires 360 reference. Particularly of the wizard ones. If you could find the time, would you mind converting the ones labeled with 'wizard' for me so I can stop harassing you? Lol, anyway, thanks a lot for the help that you've supplied already.
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-06T18:02:25+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Hi 
Here is importer for models from Overlord I i II.
It requires Blender249 and Python26.
How use:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-prp - for textured meshes, skeletons and unpacked animations
-anim - animation file from new created 'animfiles' folder. It works only with Overlord II. 

For animation select first armature object and than import anim file.
Script is not perfect. There is still many works on it.

Updated 2015-02-27:
Overold I:
- added import more materials
- fixed crashes for some files
[Blender249[Overlord][PC][prp][anim][2015-02-27].zip](https://xentaxbackup.github.io/file/8769_Blender249[Overlord][PC][prp][anim][2015-02-27].zip)
## Post #8
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-06T19:50:27+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

HI Szkaradek123，My friend, thank you very much for the great work, the script runs perfectly.
[BaiduShurufa_2015-2-7_3-34-28.jpg](https://xentaxbackup.github.io/file/8615_BaiduShurufa_2015-2-7_3-34-28.jpg)
## Post #9
- Username: MultiCore
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 02, 2014 4:45 am
- Post datetime: 2015-03-14T18:36:00+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Thank you for creating this plugin. However I am a little lost in blender. Can you explain a little more in dept how this plugin works? Im a modo guy and know nothing about blender 

Particular what you mean with blender text.

EDIT:

ok got it working. Had to copy the plugin into the blender directory. Now I was able to import empire citizen. 

However. How the hell can I export it correctly? I try FBX but max 2015 and Modo both crash on import.

EDIT EDIT  Seems like it works for other models. Must be a blender thing. Thanks again. Great plugin.
## Post #10
- Username: MultiCore
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 02, 2014 4:45 am
- Post datetime: 2015-03-14T21:44:31+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Ok the problem is still not resolved. Exporting the models to FBX works fine in blender but half of the files cant be imported into max or modo. 

For example: 

Char Empire - Regular.prp can be exported as FBX. Max and Modo will load them no with no problem. 

Char Empire - Skinny.prp can be exported as FBX but Max and Modo will crash on import. Doesn't mater how many times I export it and what settings I change in the exporter. 

This happens for about 50% of the files I try to convert. Is there a difference in the prb file?
## Post #11
- Username: MultiCore
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 02, 2014 4:45 am
- Post datetime: 2015-03-14T21:56:05+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Also what format are the .anim files in? can they be used outside of blender or do I have to convert them with blender?
## Post #12
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2015-07-11T00:02:18+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

Any way to easily extract the textures?
## Post #13
- Username: Jack Greed
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 29, 2018 12:47 am
- Post datetime: 2018-08-28T17:28:18+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

> Reply from Szkaradek123
>
> Hi 
Here is importer for models from Overlord I i II.
It requires Blender249 and Python26.
How use:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p and select:
-prp - for textured meshes, skeletons and unpacked animations
-anim - animation file from new created 'animfiles' folder. It works only with Overlord II. 

For animation select first armature object and than import anim file.
Script is not perfect. There is still many works on it.

Updated 2015-02-27:
Overold I:
- added import more materials
- fixed crashes for some files

Is there a way to run this with modern software? Blender279 is giving me a Python error, but I have Python26 so I'm assuming is a Blender thing.

(Sorry for the necromancy, this is the only place I have found where I think I can obtain 3D models from Overlord 1)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-28T20:26:34+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

> Reply from Jack Greed
>
> Is there a way to run this with modern software?No. You need to use Blender 2.49(b)

> Blender279 is giving me a Python error, but I have Python26 so I'm assuming is a Blender thing.With Blender 2.5 they changed to python 3.0 which is no compatible with python 2.6.x.
## Post #15
- Username: Jack Greed
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 29, 2018 12:47 am
- Post datetime: 2018-08-28T20:41:52+00:00
- Post Title: Overlord, Overlord: Raising Hell, Overlord II models

> Reply from shakotay2
>
> Jack Greed wrote:Is there a way to run this with modern software?No. You need to use Blender 2.49(b)
Blender279 is giving me a Python error, but I have Python26 so I'm assuming is a Blender thing.With Blender 2.5 they changed to python 3.0 which is no compatible with python 2.6.x.

Ok, thank you for the quick response. I'll download the correct Blender version then.
## Post #16
- Username: id104335409
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 01, 2018 4:58 pm
- Post datetime: 2018-12-01T09:28:56+00:00
- Post Title: Re: Overlord, Overlord: Raising Hell, Overlord II models

Hi, trying to rip Environment Nordberg.prp (this is where the town map model is, right?) from Overlord 2.
Long story short I got nostalgic and played Overlord 1 and 2 again and I got really excited over the beautiful Nordberg Christmas town. I can't recall anyone doing such a beautiful snowy town in any game. Gotta appreciate how they did the Overlord games so pretty. So anyways, I got this 3d printer and I want to print out and decorate these snow covered villas and make my own Christmas village for the holidays. This got me to XeNTaX and this thread.
So I downloaded Blender 249b and Python 263 (didn't know which one is going to work) and ran the script, but I get this message SyntaxError Missing parentheses in call to "Print"
What am I doing wrong?
BTW I already tried Ninja Ripper on this game, but I only get log files and no rips (I don't think F10 registers, ingame I can't even go to Windows unless I use the game menus or CtrlAltDel). And if anyone has the houses that I need, I would be grateful if you can share them with me. Thanks.

Oh, there we go! I managed to get ninja ripper to work. Just a question of running the right ver.32bit plus directx9 and push ctrl F10 - NOT just F10. Easy as pie. Noesis sees the mesh after a little plugin copy paste that comes with the ninja. Then convert rip files to obj files and done!
## Post #17
- Username: DouggietheWalker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 27, 2023 4:32 pm
- Post datetime: 2023-04-09T22:32:28+00:00
- Post Title: Re: Overlord, Overlord: Raising Hell, Overlord II models

I know this is a bit of a older topic thread, but I have been trying to document and upload all the Overlord 2 models but have encountered a massive road block, The Battle Rock DLC. Most of the files (including the Phoenix and Battle Rock itself) is on disk, but the Empire General and Saytr models are only found in the dlc. I was able to recover the dlc files since they were pulled from Xbox live, but can't for the life of me look through the files with the old script because they are in a weird xrp.lzx file format.... I've no idea what to do and to make matters worse there is hardly any info about this format on the internet. I'll likely make another thread about this odd ass format to see if anyone know anything about it
## Post #18
- Username: miinecraft5
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 12, 2023 2:11 am
- Post datetime: 2023-06-11T18:15:49+00:00
- Post Title: Re: Overlord, Overlord: Raising Hell, Overlord II models

Can someone tell me where the skin colors are located in the game's hex files? I'm trying to change the dark fay skin to queen fay's
## Post #19
- Username: EXdreams
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 20, 2022 2:11 am
- Post datetime: 2023-07-30T09:26:54+00:00
- Post Title: Re: Overlord, Overlord: Raising Hell, Overlord II models

Animation data have half float type.
