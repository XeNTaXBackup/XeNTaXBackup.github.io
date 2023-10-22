## Post #1
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-06-07T15:46:43+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

League of Legends (LoL   ) is a 3D game with character models in SKN file format, SKL is skeletal format and ANM is animation file format. I saw some tools for this game for importing models, but without animation. For example, script for Blender for import of SKN, or you can see SKN in 3D Object Convertr. And no tools for import model with animation for 3ds max.

Here rendered screen with converted to OBJ SKN-models.
[](http://xmages.net/show.php/2828782_lol1-png.html)

Can anybody make tool (script for MAX or plugin) to import animation? Here models from screen:
[http://www.multiupload.com/L5QL2WO25H](http://www.multiupload.com/L5QL2WO25H) (5Mb)
I hope this old tool to import animation from old format of this game could be useful - [http://www.multiupload.com/B5MZ844TKB](http://www.multiupload.com/B5MZ844TKB)
## Post #2
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-06-13T18:12:51+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

While a Noesis plugin for the format would be fun, the format is already fully supported in Maya 2010/2011/2012 courtesy of ThiSpawn: [http://forum.leaguecraft.com/index.php? ... 12-x86x64/](http://forum.leaguecraft.com/index.php?/topic/26258-riotfiletranslator-plugin-for-autodesk-maya-20112012-x86x64/)

It imports the models with skeletal rigging intact you can also import the animations etc. Just use Maya and then transfer to 3DS Max if you need to.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-12T01:51:43+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

Did he publish the format anywhere? Or does everyone just depend on the author lol
## Post #4
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-07-14T14:52:07+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

> Reply from finale00
>
> Did he publish the format anywhere? Or does everyone just depend on the author lol
If you can find it, there's an older tool for maya by renticletape, and he released it with the source. Then you can convert it into maxscript, like I did, but I didn't do bones or animation because I don't know how to yet.

I'm not sure if the format has change since I last made the script, which was near the start of this year.

```
League of Legends Maxscript Model Importer
by nightFlarer
A maxscript to import .skn files
*/

fname = getOpenFileName \ 
caption:"League of Legends Skin Model File" \
types:"League of Legends Skin Model File(*.skn)|*.skn" \
historyCategory:"LeagueofLegendsObjectPresets"
f = fopen fname "rb"
clearlistener()

fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
      str0 = ReadByte bstream #unsigned
     str+= bit.intAsChar str0
   )
   str
)

Face_array=#()
Vert_array=#()
UV_array=#()

--Structure for the Header in skn files
magic=readlong f #unsigned
numMat=readshort f #unsigned
numObj=readshort f #unsigned

--Structure for a material block in skn files
matInd=readlong f #unsigned
charName=ReadFixedString f 64
startVertex=readlong f #unsigned
numVertices=readlong f #unsigned
startIndex=readlong f #unsigned
numIndices=readlong f #unsigned

--data block in skn files
numIndices=readlong f #unsigned
numVertices=readlong f #unsigned

--read faces
for x = 1 to numIndices/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fc,fb,fa]
)
--read vertices
for x = 1 to numVertices do( -- vertex loop
vx=readfloat f
vy=readfloat f
vz=readfloat f
boneindex=readlong f #unsigned
w1=readfloat f
w2=readfloat f
w3=readfloat f
w4=readfloat f
nx=readfloat f
ny=readfloat f
nz=readfloat f
tu=readfloat f
tv=readfloat f
	
append Vert_array[vx,vz,vy]
append UV_array[tu,tv*-1+1,0]
)


msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
--convertTo msh PolyMeshObject
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
rotate msh (angleaxis -180 [0,0,1])

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-14T15:13:08+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

Alright thanks. I will use your script for reference 

EDIT: works for the provided samples. Guess I'll have to get the client to test some more.

 

Maybe I should actually start doing something about bones.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-16T12:18:54+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

I DL'd the client but it seems to pack everything into dat files using raf as some index thing.
What to use to unpack?
## Post #7
- Username: nightFlarer
- Rank: beginner
- Number of posts: 33
- Joined date: Thu May 13, 2010 3:25 pm
- Post datetime: 2011-07-16T14:40:08+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

When I last downloaded and installed LoL, the champions,etc. was in "C:\Riot Games\League of Legends\game\HeroPak_client.zip".

They don't use zips anymore?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-16T16:57:08+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

Hmm don't know all I see is a RADS folder with a bunch of different releases. Though, no zip archives.
Maybe I downloaded something different. I got it from

[http://signup.leagueoflegends.com/en/signup/redownload](http://signup.leagueoflegends.com/en/signup/redownload)
## Post #9
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-07-17T06:00:29+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

I have data in "HeroPak_client.zip" too. No "RADS" or same folders or archives.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-17T15:53:33+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

Hmm who knows I just went to their official forums to look around and found this 

ttp://76.73.13.30/Files/League%20of%20Legends/Game/

Maybe I missed a step or something lol

I also just downloaded the "maps" files, which seems to contain map assets (.SCB files). Sort of looks like there might be something there though it's not the most obvious.

Now...no items? lol
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-17T19:06:16+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

> Reply from nightFlarer
>
> When I last downloaded and installed LoL, the champions,etc. was in "C:\Riot Games\League of Legends\game\HeroPak_client.zip".

They don't use zips anymore?yes me too, I download from there and don't have nothing about zip files, maybe is different version, korean example.
## Post #12
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-10-08T18:42:02+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

The contents of this post was deleted because of possible forum rules violation.



Update 2014-11-28:

League of Legends importer for Blender version 249 and Python 26:
It supports:
- skn files - skinned meshes ( version 2 and 4 )
- anm files  - animation files ( with header r3d2anmd version 3, 4 and 5 and without header r3d2anmd )

files with header "r3d2canm" are not. For it use [viewtopic.php?p=101066#p101066](http://forum.xentax.com/viewtopic.php?p=101066#p101066)


[Blender249[LeagueOfLegends][skn][anm][2014-11-28].zip](https://xentaxbackup.github.io/file/8158_Blender249[LeagueOfLegends][skn][anm][2014-11-28].zip)
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-10-08T19:10:22+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

wow thanks a lot man, you are great, perfect support.
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-10-24T18:27:14+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-03-19T01:14:58+00:00
- Post Title: League of Legends .SKN, .SKL, .ANM

How can I use thisblender plug in to import the models? I have the blend file in the folder where the skn and skl are and when i click twice on the blend file i just got opened blender... no model imported...
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-19T02:03:44+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

Open the blend file in blender and you should get some sort of user interface for loading models.
## Post #17
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-08-17T12:13:41+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

Hey guys, I just replayed League Of Legends, but when I checked the download stuff, to look at the skn, ski and anm files, there were none, only *.raf and *.raf.dat files
?? Any idea?

After some looking into the files, I saw that the raf file contains the filenames and I think the offset/sizes of the actual files. The actual files can be found in the .dat file...

Maybe someone can make a little script to extract the files from it?

T.
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-08-17T18:44:04+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

[http://forum.leaguecraft.com/index.php? ... r-release/](http://forum.leaguecraft.com/index.php?/topic/31543-rafmanager-release/)
## Post #19
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-08-18T09:57:50+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

thnx Chrrox, I found it later yesterday evening, yet it still needs to extract each file one by one, so I hope to put something together that you just need to select your main folder and extract everything and it puts everything into one folder, or just a few folders depending on the extension.

T.
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2013-08-18T18:37:14+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

[out]
## Post #21
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2021-10-22T22:56:06+00:00
- Post Title: Re: League of Legends .SKN, .SKL, .ANM

i've tried on Wallace and Gromit models but this popped up.
[skl error.png](https://xentaxbackup.github.io/file/21065_skl error.png)
