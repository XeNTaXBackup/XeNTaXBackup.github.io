## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-04-19T11:14:39+00:00
- Post Title: el matador

Recently I got into el matador files and wanted to play with models. Can anyone check the files? Here's some samples:
[http://www.mediafire.com/download/1ldmt ... /Agents.7z](http://www.mediafire.com/download/1ldmtqzlu4e5ayf/Agents.7z)
also here's animation samples:
[http://www.mediafire.com/download/d8c1h ... MATIONS.7z](http://www.mediafire.com/download/d8c1hd635x3g7qs/ANIMATIONS.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-19T12:00:41+00:00
- Post Title: el matador

weird format, the vertices look like x 02 y 02 z 02, FVF size is 55 for  civil_woman.mdl_bin;
in the upper left corner it looks like the shape of the head:



civil_woman-mdl_bin.jpg (45.95 KiB) Viewed 240 times
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-04-19T13:11:12+00:00
- Post Title: el matador

> Reply from shakotay2
>
> weird format, the vertices look like x 02 y 02 z 02, FVF size is 55 for  civil_woman.mdl_bin;
in the upper left corner it looks like the shape of the head:
civil_woman-mdl_bin.jpgthanks for your attention! is there any chance to compile this info into noesis script or something? ripper can't rip this game in t-pose unfortunately.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-21T18:15:11+00:00
- Post Title: el matador

I don't see a reason why not. For python script u just need to skip one byte each after reading the x, y, z components of a vertex as floats. The problem is to find the suiting face indices.

well, when I spoke about python, I obviously meant blender python, because Noesis uses rapi.rpgBindPositionBufferOfs() 
for example which needs a continuous vertex buffer and I don't have a clue how to provide it by easy means when there's a byte (02) inserted after each float.

But you could modify the maxscript sample I uploaded for L.A. Noir, using readFloat for the vertices and
fSeek stream (1) #seek_cur
to skip the annoying 02 byte.
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-25T10:56:13+00:00
- Post Title: el matador

Hi
Here is blend file for import models and animations.
It requires to install Blender version 249b (32 bit) and Python 2.6.6.(32 bit).
Doubleclick file "Blender249.blend" and in Text Window press alt+p to run script.
Select file with *.mdl_bin to import model and for animation select file with *.anim_bin.
[Blender249[El Matador][PC][mdl_bin][anim_bin][2016-04-25].zip](https://xentaxbackup.github.io/file/10833_Blender249[El Matador][PC][mdl_bin][anim_bin][2016-04-25].zip)
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-04-29T21:07:37+00:00
- Post Title: el matador

Szkaradek123, appreciate for your work!
please explane what need to change in the script to flip bones, meshes and animation by X axis on load into blender? right now left arm and its bone are on the right side and same with everything else.
thank you
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-30T04:24:05+00:00
- Post Title: el matador

Hi
In 3D View Window select object "armature" and press ctrl+m and next key x .
Or from menu this window press Object=>Mirror=>X Local
## Post #8
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-04-30T18:56:31+00:00
- Post Title: el matador

Szkaradek123, most part of models, expecially static from "missions' models folder, not loading with: 

"TypeError: range<> integer and argument expected, got NoneType", or "got str".
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-04-30T19:21:36+00:00
- Post Title: el matador

Hi
If you send not working files i can  look at.
## Post #10
- Username: StreamThread
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Mar 22, 2016 4:58 am
- Post datetime: 2016-05-01T11:25:37+00:00
- Post Title: el matador

> Reply from Szkaradek123
>
> Hi
If you send not working files i can  look at.
[http://www.mediafire.com/download/vaw0p ... /MODELS.7z](http://www.mediafire.com/download/vaw0pp2m2c6vp53/MODELS.7z)
Not loading almost all static models.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-01-11T10:57:05+00:00
- Post Title: el matador

Szkaradek123, can you still look into static models?
