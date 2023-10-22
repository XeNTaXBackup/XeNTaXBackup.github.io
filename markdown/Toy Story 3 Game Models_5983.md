## Post #1
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-04T01:11:26+00:00
- Post Title: Toy Story 3 Game Models

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-05T00:48:32+00:00
- Post Title: Toy Story 3 Game Models

its gonna be great if we can extract the model
## Post #3
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-06T05:41:24+00:00
- Post Title: Toy Story 3 Game Models

Alright, so I believe the .bent files are the models and the .oct files are something that I don't know of. I did the basic part of the header which is the same for both .bent and .oct. I think the other files, aside from the .dbl uses the same header.

```
x08 - Header (29 76 01 45 CD CC 8C 3F)
x35 - Unknown (Come back to)
Starts "Compiler?" information
```

It follows that format for each .bent and .oct file. I don't know anything else at this current time. Hopefully this'll help anyone who looks into this format later on.
## Post #4
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-09T01:52:29+00:00
- Post Title: Toy Story 3 Game Models

> Reply from ItsEasyActually
>
> 
It follows that format for each .bent and .oct file. I don't know anything else at this current time. Hopefully this'll help anyone who looks into this format later on.

Something tells me that Avalanche made that format on purpose so people like us couldn't crack it so easily. And before anyone says "OH USE 3D RIPPER DX LOLOLOLOL", it does not work with the game. And even if it did, LuigiMario on facepunch would've had them ripped ages ago.
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-09T04:47:47+00:00
- Post Title: Toy Story 3 Game Models

I've been using 3dripperdx for years.. 
I've never encountered a dx9 game that wasn't possible to capture with 3dripperdx or another dx9 debugger.

I'm sure luigi would take my word for it too, I was involved with ripping when I was at FP and I stand by 3dripperDX.

anyways, the format was super easy. so I wrote up a simple maxscript to import the model. 
use nova extract on the oct files to dump the textures. the OCT files hold DDS textures, nova extract scans for the dds headers and dumps them accordingly

 

```
caption:"ToyStory3AssRaper" \
types: "Vertex Binary (*.vbuf)|*.VBUF|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fpath=          getFilenamePath fsource
fname=  getFilenameFile fsource
if (doesFileExist (fpath+fname+".ibuf"))==true do(
g = fopen (fpath+fname+".ibuf") "rb"
gsize=getFileSize (fpath+fname+".ibuf")
st = timestamp() --get start time in milliseconds
clearlistener()
print (fname+"\n"+localTime+"\n")
--===========================================================================
undo off(
with redraw off (
while (ftell f)!=fsize AND check!=-1 do(
if keyboard.escPressed then exit
	Vert_array=#()
	Face_array=#()
	UV_array=#()
check=readlong f;fseek f -4 #seek_cur
Counter=0	
do(
tv=readfloat f
tu=(readfloat f*-1)+1
tw=readfloat f
vx=readfloat f*39.34
vy=readfloat f*39.34
vz=readfloat f*-39.34
w1=readbyte f #unsigned
w2=readbyte f #unsigned
w3=readbyte f #unsigned
w4=readbyte f #unsigned
weight=w1+w2+w3+w4
if weight==0xFF do(
Counter+=1
append Vert_array[vx,vz,vy]
append UV_array[tv,tu,0]
)) while weight==0xFF
fseek f -28 #seek_cur
Print ("Vert Read @ 0x"+((bit.intAsHex(ftell f))as string))
Print Counter
for x = 1 to Counter do(
nx=readfloat f
ny=readfloat f
nz=readfloat f
un=readfloat f
))
while (ftell g)!=gsize 
do(
fa=readshort g #unsigned+1
fb=readshort g #unsigned+1
fc=readshort g #unsigned+1
append Face_array[fa,fb,fc]
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name=fname
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
--===========================================================================
gc()
fclose f
fclose g
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
)))) else (Print "Aborted.")

```
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-09T12:31:13+00:00
- Post Title: Toy Story 3 Game Models

That was fantastic mario
Thanks for the script
## Post #7
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-09T21:38:56+00:00
- Post Title: Toy Story 3 Game Models

MK64N, you're my freaking hero! Thank you for contributing to the thread. I am surprised someone was able to do this so quickly too. Again, I cannot thank you enough.
## Post #8
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-09T21:46:39+00:00
- Post Title: Toy Story 3 Game Models

chrrox noticed that my script doesnt work on all the submeshes 

if you get an error, all you can do is move the arrays above the "while statement" to get the meshes correct we'd need to crack the other index files.. which is too much work for me
## Post #9
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-02-10T00:47:21+00:00
- Post Title: Toy Story 3 Game Models

> Reply from mariokart64n
>
> chrrox noticed that my script doesnt work on all the submeshes 

if you get an error, all you can do is move the arrays above the "while statement" to get the meshes correct we'd need to crack the other index files.. which is too much work for me

Well, I'm getting such errors, too, when I try to import some of the meshes ingame.
## Post #10
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-02-10T00:50:23+00:00
- Post Title: Toy Story 3 Game Models

I have Wii version of game, some file are the "same", but I can't extract dds or open 3D models.
Here Buzz and Woody!

[http://hotfile.com/dl/103296319/502cb3d ... i.rar.html](http://hotfile.com/dl/103296319/502cb3d/BuzzWoodyWii.rar.html)

With the 2 models in first post, the script crash in 3dsmax 2011 (I try both "high" version)
## Post #11
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-10T01:40:50+00:00
- Post Title: Toy Story 3 Game Models

> Reply from grotesque
>
> I have Wii version of game, some file are the "same", but I can't extract dds or open 3D models.
Here Buzz and Woody!

http://hotfile.com/dl/103296319/502cb3d ... i.rar.html

With the 2 models in first post, the script crash in 3dsmax 2011 (I try both "high" version)
 The "High" models do not work from my experience, I believe Buzz will only extract (darkspines being the one who ripped him recently), but we'll keep trying until they work, now I'm gonna look into rigging for the source engine, because I plan to port these like I said before.

By the way, hilarious humor MK64n. I laughed when I say "Ass Raper" in your MAXscript.

Edit: Seems that there's a vertex error upon importing the High Buzz model with the script, otherwise no other models will import.
## Post #12
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-10T02:18:44+00:00
- Post Title: Toy Story 3 Game Models

i think the script only work for pc version
Not the wii version,i think
## Post #13
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2011-02-10T02:24:08+00:00
- Post Title: Toy Story 3 Game Models

> Reply from jaden
>
> i think the script only work for pc version
Not the wii version,i think

Probably due to endianness and other platform-specific quirks.
## Post #14
- Username: ItsEasyActually
- Rank: n00b
- Number of posts: 18
- Joined date: Fri Dec 17, 2010 7:49 am
- Post datetime: 2011-02-10T02:25:28+00:00
- Post Title: Toy Story 3 Game Models

Anyone know where this Nova program can be found? A quick Google search gave me shit. A search on these boards resulted in dead links. So...anyone got a mirror of it somewhere?
## Post #15
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-10T02:26:34+00:00
- Post Title: Toy Story 3 Game Models

> Reply from huckleberrypie
>
> 
Probably due to endianness and other platform-specific quirks.
Sounds about right. I guess whenever I get bored I'll look at the Wii and PC versions of the models in Notepad++ or some sort of Hex editor.
I second what Easy said. I can't find nothing but crap with keygens.
## Post #16
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T03:13:40+00:00
- Post Title: Re: Toy Story 3 Game Models

buzz worked out ok for me, though you can see his visor is missing.



also the Wii format is different, the faces and verts are defined in different sizes. its more compact then before, maybe they written in triStrips now
## Post #17
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-02-10T13:48:39+00:00
- Post Title: Re: Toy Story 3 Game Models

What version of buzz you use (high, ecc), mariokart64n?
## Post #18
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-10T21:39:32+00:00
- Post Title: Re: Toy Story 3 Game Models

> Reply from mariokart64n
>
> buzz worked out ok for me, though you can see his visor is missing.
 Odd, he still doesn't import for me, and I've done everything correctly, maybe a list of working models would help?
## Post #19
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T21:50:14+00:00
- Post Title: Re: Toy Story 3 Game Models

the error is cause by too many faces. cause I dont read the subMesh info, I read the files as one HUGE model.. but the face's go from say 1,2,3,4,5...200 etc.. then reset again to 1,2,3,... so the script I made only imports the first mesh. if there are more then one mesh, then it won't work.

however I stated a couple posts ago, just to move the arrays past the loop. that'll cause it to import the final mesh regardless.. of he face reseting

I'll just repost the script with that line swap

also keep in mind the other submeshes will be missing, like buzz's visor. so you'll have to get parts from the lowpoly models. which do not have submeshs

```
fsource = GetOpenFileName \
caption:"ToyStory3 Importer" \
types: "Vertex Binary (*.vbuf)|*.VBUF|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fsize=			getFileSize fsource
fname=  		getFilenameFile fsource
if (doesFileExist (fpath+fname+".ibuf"))==true do(
g = fopen (fpath+fname+".ibuf") "rb"
gsize=getFileSize (fpath+fname+".ibuf")
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(
with redraw off (
	Face_array=#()	
		Vert_array=#()

	UV_array=#()

while (ftell f)!=fsize AND check!=-1 do(
if keyboard.escPressed then exit





check=readlong f;fseek f -4 #seek_cur
Counter=0	
do(
tv=readfloat f
tu=(readfloat f*-1)+1
tw=readfloat f
vx=readfloat f*39.34
vy=readfloat f*39.34
vz=readfloat f*-39.34
w1=readbyte f #unsigned
w2=readbyte f #unsigned
w3=readbyte f #unsigned
w4=readbyte f #unsigned
weight=w1+w2+w3+w4
if weight==0xFF do(
Counter+=1
append Vert_array[vx,vz,vy]
append UV_array[tv,tu,0]
)) while weight==0xFF
fseek f -28 #seek_cur
Print ("Vert Read @ 0x"+((bit.intAsHex(ftell f))as string))
Print Counter
for x = 1 to Counter do(
nx=readfloat f
ny=readfloat f
nz=readfloat f
un=readfloat f
))
while (ftell g)!=gsize 
do(
fa=readshort g #unsigned+1
fb=readshort g #unsigned+1
fc=readshort g #unsigned+1
append Face_array[fa,fb,fc]
)
msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name=fname
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
fclose g
fclose s
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
)))) else (Print "Aborted.")

```
## Post #20
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-10T22:01:50+00:00
- Post Title: Re: Toy Story 3 Game Models

Thanks MK64, though there are some bugs. High Woody does import but...


Woody is now eh... Well he's not Woody XD. Buzz imports fine though, but the parts of his backpack are a little... Fucked should I say?


Also, I've been looking for the Nova Extractor, all I get is dead links. MarioKart, if you don't mind, could you please upload Nova somewhere?
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-10T22:41:16+00:00
- Post Title: Re: Toy Story 3 Game Models

yeah I know, I just said above that it reads too many face.. and you can see there that those extra faces still get drawn.

theres nothing I can do, unless I decipher the other files for the submesh info.


if your good with 3d editing, fixing the back shouldnt be too hard
## Post #22
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2011-02-10T22:54:36+00:00
- Post Title: Re: Toy Story 3 Game Models

How do you have that perfect texture?
You separate manually mesh?
## Post #23
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-10T22:57:38+00:00
- Post Title: Re: Toy Story 3 Game Models

But still thanks mario
## Post #24
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-10T23:29:59+00:00
- Post Title: Re: Toy Story 3 Game Models

> Reply from grotesque
>
> How do you have that perfect texture?
You separate manually mesh?
You have to select the polygons manually, it's an ass, but it's well worth it.
## Post #25
- Username: SoapyLemons
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Feb 04, 2011 9:01 am
- Post datetime: 2011-02-12T06:09:54+00:00
- Post Title: Re: Toy Story 3 Game Models

I don't mean to double post...

update though, I ripped several models from MK64's script.

Here is what I ripped.








I gotta fix up some models, like Bo and Jessie for example 

Anyways, thanks again MK64, you're a big help.
## Post #26
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2011-04-12T18:18:54+00:00
- Post Title: Re: Toy Story 3 Game Models

as it does to view or convert obj
## Post #27
- Username: KaLaC
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 18, 2010 11:12 pm
- Post datetime: 2011-04-18T15:29:26+00:00
- Post Title: Re: Toy Story 3 Game Models

@SoapyLemons: Can you plz send me the models? Because I don't know how to extract the textures from the OCT files.
If you can send me, I will appericate.

And also thanks mario for the code!!
## Post #28
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-01T13:05:34+00:00
- Post Title: Re: Toy Story 3 Game Models

Hello

Here is importer for models from PC . 

It requires Blender version 249 and Python 2.6. 

I use scene format research done by zzh8829 from  [viewtopic.php?p=93154#p93154](http://forum.xentax.com/viewtopic.php?p=93154#p93154)

It works with .oct files from Toy Story 3 for PC.

It imports:
- models with weights and textures
- armature

After importing please rotate meshes along Z-axis ( key R and Z)
Because Blender use only 16 materials per mesh, importer split each mesh into many submeshes.


Example:
[http://www.mediafire.com/download/o7tjd ... /model.zip](http://www.mediafire.com/download/o7tjdejphdwaqvo/model.zip)
[Blender249[ToyStory3][PC][oct][2014-12-01].zip](https://xentaxbackup.github.io/file/8177_Blender249[ToyStory3][PC][oct][2014-12-01].zip)
## Post #29
- Username: shoopdahoop22
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 28, 2016 1:16 am
- Post datetime: 2016-08-05T03:35:45+00:00
- Post Title: Re: Toy Story 3 Game Models

I hate to be bumping an old thread but...

are there any download links for Nova Extractor anywhere?
## Post #30
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2016-08-05T11:43:45+00:00
- Post Title: Re: Toy Story 3 Game Models

using szkaradek123' importer, you don't need nova extractor to get the textures
## Post #31
- Username: SNES Gary
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 29, 2019 12:35 am
- Post datetime: 2019-07-30T07:11:49+00:00
- Post Title: Re: Toy Story 3 Game Models

Hey. Sorry to open this thread 3 years later, but how do I use the blender importer posted above?
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-08-05T08:03:12+00:00
- Post Title: Re: Toy Story 3 Game Models

Read this post: 
> Reply from Szkaradek123 ↑Mon Dec 01, 2014 9:05 pm at Mon Dec 01, 2014 9:05 pm
>
> 
- open .blend file from appended zip in blender 2.49b.
- in the leftmost (text/script) window press ctrl-p
- import .oct file
.



ToyStory3-blender 2.49b.png (22.67 KiB) Viewed 166 times



(For Win7 and higher read here: [viewtopic.php?f=16&t=12153&p=99990&hili ... lib#p99990](https://forum.xentax.com/viewtopic.php?f=16&t=12153&p=99990&hilit=newgamelib#p99990))
## Post #33
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T02:35:08+00:00
- Post Title: Re: Toy Story 3 Game Models

Is this updated?
## Post #34
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-09-10T07:53:14+00:00
- Post Title: Re: Toy Story 3 Game Models

> Reply from lkw019 ↑Tue Sep 10, 2019 10:35 am at Tue Sep 10, 2019 10:35 am
>
> 
Is this updated?
It's the same old script for old version of Blender, nothing has been updated, I wish.
## Post #35
- Username: TheBlackSpider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 06, 2021 3:53 am
- Post datetime: 2022-01-16T10:15:03+00:00
- Post Title: Re: Toy Story 3 Game Models

Hi I know it's old but I can't find a few high poly models in the game files like bo peep and zurg. I also looked on the Xbox version. Can anyone help?
## Post #36
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2023-01-01T20:16:06+00:00
- Post Title: Re: Toy Story 3 Game Models

I Have Noesis and Blender 2.79, But Nothing has opened OCT Files, Because i Need someone to help make a python to help me support Toy Story 3 Models for Source Filmmaker and Models Resource, But there's No SMD Support for Blender 2.4.9.
Contact Me if there's a Solution.
## Post #37
- Username: CameronWren
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 06, 2023 11:06 pm
- Post datetime: 2023-09-06T15:12:18+00:00
- Post Title: Re: Toy Story 3 Game Models

> Reply from Szkaradek123 ↑Mon Dec 01, 2014 9:05 pm at Mon Dec 01, 2014 9:05 pm
>
> 
Hello

Here is importer for models from PC . 

It requires Blender version 249 and Python 2.6. 

I use scene format research done by zzh8829 from  http://forum.xentax.com/viewtopic.php?p=93154#p93154

It works with .oct files from Toy Story 3 for PC.

It imports:
- models with weights and textures
- armature

After importing please rotate meshes along Z-axis ( key R and Z)
Because Blender use only 16 materials per mesh, importer split each mesh into many submeshes.


Example:
http://www.mediafire.com/download/o7tjd ... /model.zip

Hey,

Know this might be a bit of a long shot seeing as though it's been 9 years but do you have any more information on how to extract these files? Unless I'm reading this wrong your message reads like there should be something attached that would help me extract the files from Toy Story 3 but all I see is an example of Jessie. Any help would be appreciated as I'm trying to recreate Toy Story 3 in Unreal Engine 5 as a personal project.

Thanks
## Post #38
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2023-09-06T15:15:41+00:00
- Post Title: Re: Toy Story 3 Game Models

It's Too Late to talk about it.
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-09-06T16:20:26+00:00
- Post Title: Re: Toy Story 3 Game Models

> Reply from CameronWren ↑Wed Sep 06, 2023 11:12 pm at Wed Sep 06, 2023 11:12 pm
>
> 
Szkaradek123 wrote: ↑Mon Dec 01, 2014 9:05 pm
Hello

Here is importer for models from PC . 

It requires Blender version 249 and Python 2.6. 

I use scene format research done by zzh8829 from  http://forum.xentax.com/viewtopic.php?p=93154#p93154

It works with .oct files from Toy Story 3 for PC.

It imports:
- models with weights and textures
- armature

After importing please rotate meshes along Z-axis ( key R and Z)
Because Blender use only 16 materials per mesh, importer split each mesh into many submeshes.


Example:
http://www.mediafire.com/download/o7tjd ... /model.zip


Hey,

... Unless I'm reading this wrong your message reads like there should be something attached that would help me extract the files from Toy Story 3 but all I see is an example of Jessie.

ThanksHey, just unzip the attachment (Blender249[ToyStory3][PC][oct][2014-12-01].zip) from the post you've quoted. It contains a python script to get meshes from .oct files. Just saying.
