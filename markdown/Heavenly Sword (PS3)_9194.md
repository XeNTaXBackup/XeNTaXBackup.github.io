## Post #1
- Username: dragbody
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-03T01:33:56+00:00
- Post Title: Heavenly Sword (PS3)

Noesis importer for heavenly sword.
Supported
30s and 40s
imports
verts
uv's
faces
not imported
bones
weights
materials


[fmt_HeavenlySword_V1.rar](https://xentaxbackup.github.io/file/5533_fmt_HeavenlySword_V1.rar)
## Post #2
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-03T03:35:28+00:00
- Post Title: Heavenly Sword (PS3)

Thanks chrrox this is really awesome.
## Post #3
- Username: Jodan
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Jul 02, 2010 11:12 am
- Post datetime: 2012-07-03T07:02:18+00:00
- Post Title: Heavenly Sword (PS3)

Chrrox really appreciate this importer and all you do for this site; I just have a question what do we need to do to extract the data from the wad files?
---------------------
I saw a older post by Aluigi who had written a BMS script to extract from a wad file, (it seems to work )but the output consists of a file with a gwg extension and several miscellaneous dat files. These files are named with numbers and usually with one or two letters at the end ("000000a.dat" for example) and as a result I am at a loss as to the next step. 
---------------------

Would appreciate any help you can offer to get these files from wad to looking like the renders you posted.

Thank you for your time,

Jodan
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-03T08:54:54+00:00
- Post Title: Heavenly Sword (PS3)

extractor.
[viewtopic.php?f=10&t=6215](http://forum.xentax.com/viewtopic.php?f=10&t=6215)
if you look at the output folder the files will have names ignore the text.
## Post #5
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-03T19:33:53+00:00
- Post Title: Heavenly Sword (PS3)

Great work chrrox, finally Heavenly Sword models, Thank you.
I'm just having some problems with Kai's UV

I already did the obvious and resized it but it doesn't fit right even if I try to manually place it, some parts fits and some don't
Looks like it's slightly rotated?
It's an .obj export Noesis>Blender.
Model from folder fort_global file 00000864.30s.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-03T19:35:57+00:00
- Post Title: Heavenly Sword (PS3)

click on flip uv's

and the scale i think is in th ematerials but if you flip them you can place them correctly.
## Post #7
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-03T19:46:27+00:00
- Post Title: Heavenly Sword (PS3)

> Reply from chrrox
>
> click on flip uv's

and the scale i think is in th ematerials but if you flip them you can place them correctly.
I exported with the UV flipped.
Here:

Resized it, see how some parts fits and some don't? the legs are worse with black seams.
Exporting normally (without the flip UV option) and then flipping the UV gives the same result.
You need to manually place every parts separated, trying to position the whole UV fix one part and breaks other.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-03T19:51:41+00:00
- Post Title: Heavenly Sword (PS3)

i only had one model to work with as all i had was the demo
you can try editing the script
change the lines
				tu = bs.readShort() / 0xFFFF + .5
				tv = bs.readShort() / 0xFFFF + .5
into
				tu = bs.readShort() / 0x7FFF + .5
				tv = bs.readShort() / 0x7FFF + .5
## Post #9
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-03T20:17:57+00:00
- Post Title: Heavenly Sword (PS3)

It's better but doesn't fit yet. I'll PM it to you so you can look into it better.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-03T20:29:28+00:00
- Post Title: Heavenly Sword (PS3)

your texture looks wrong.
## Post #11
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-03T20:34:09+00:00
- Post Title: Heavenly Sword (PS3)

> Reply from chrrox
>
> your texture looks wrong.

Oh, noticed that now that you said /face palm.
Meh a part of the right is on the left u.u
 At lest it's solved xD 
My bad.
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-07-04T00:21:26+00:00
- Post Title: Heavenly Sword (PS3)

Hey rexil let me know if you find a cinematic model.. so far the mesh we found is the ingame one.. and doesnt reflect what is seen in the games stunning cutscenes.. 
but it is possible that they are all pre-rendered however
## Post #13
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-04T05:05:51+00:00
- Post Title: Heavenly Sword (PS3)

> Reply from mariokart64n
>
> Hey rexil let me know if you find a cinematic model.. so far the mesh we found is the ingame one.. and doesnt reflect what is seen in the games stunning cutscenes.. 
but it is possible that they are all pre-rendered however
I didn't look over everything yet but the best Nariko I found so far has 14~k verts/ 19~k tris without hair, sleeve and eyes. I'm trying to find Kai with unposed fingers   
I'll let you know if I find something better.
## Post #14
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2012-07-04T05:15:10+00:00
- Post Title: Heavenly Sword (PS3)

which format for textures?
## Post #15
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-07-04T14:57:44+00:00
- Post Title: Heavenly Sword (PS3)

> Reply from 652845095
>
> which format for textures?

They are DDS but they inside of the .dat files
## Post #16
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-04T17:28:21+00:00
- Post Title: Re: Heavenly Sword (PS3)

Is it possible for someone to make a script to convert the .dat's? I wanted some scenaries but they have many textures and doing it manually is very boring.
## Post #17
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-07-05T10:36:32+00:00
- Post Title: Re: Heavenly Sword (PS3)

> Reply from rexil
>
> Is it possible for someone to make a script to convert the .dat's? I wanted some scenaries but they have many textures and doing it manually is very boring.
I have  a cmd based One thatz working quite good i guess...didn't have enough .dats for testing it further.
It only works for one type and One size at a time. Wasnt able to make it defined by File size yet and also i doubt itz the best method.
## Post #18
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-09T14:37:00+00:00
- Post Title: Re: Heavenly Sword (PS3)

I have been trying to correct the problem with the textures but I can't get the then right.
What's the correct way to convert them to dds. The way I'm doing it the images get a part from the right showing in the left or the colors are all wrong :\
If anyone can give me some directions.
Thank you.
