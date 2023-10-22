## Post #1
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-07-12T15:08:32+00:00
- Post Title: Shaiya Online [Solved]

Hey to all,

I was able to find an extractor for Shaiya Online and extracted most of the archive (700MB out of 2GB - seems it has some kind of issue) but anyhow, I think I might have found the 3D models from the game.

I uploaded a sample below.

Cheers to all, and ciao.
[Shaiya.rar](https://xentaxbackup.github.io/file/2187_Shaiya.rar)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-08T08:15:58+00:00
- Post Title: Shaiya Online [Solved]

This is a very very simple format! Here you go.

```
dword       numBones
struct Bone {
   float_16 Matrix4X4   
}
dword       numVerts
struct Vert {
   float_3  CoordXYZ
   float    Weight
   byte     BoneID01
   byte     BoneID02
   float_3  NormalXYZ
   float_2  TexCoordUV
}
dword       numFaces
struct Face {
   word_3   FaceIndices123
}
```
## Post #3
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-08-08T20:33:35+00:00
- Post Title: Shaiya Online [Solved]

Thank you for the time!

I don't know anything about coding and rather stupid, so what can I do with this code?
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-06T12:48:36+00:00
- Post Title: Shaiya Online [Solved]

Did you see this gallery ?
[http://web.t-online.hu/karpo/gallery_shaiya_online.html](http://web.t-online.hu/karpo/gallery_shaiya_online.html)
## Post #5
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2009-11-06T12:56:33+00:00
- Post Title: Shaiya Online [Solved]

I note my program supports the following formats:

Shaiya Online	*.3DC	Load
Shaiya Online	*.3DO	Load
Shaiya Online	*.SMOD	Load
## Post #6
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2010-09-28T13:01:22+00:00
- Post Title: Shaiya Online [Solved]

anybody knows the format of the *.ani files?
i have a sample mesh (mesh, texture, animation file) attached. perhaps anyone can find out the format of it...

btw, the 3dc format that posted by fatduck is still up to date.
[cow.zip](https://xentaxbackup.github.io/file/3486_cow.zip)
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-10-03T18:50:14+00:00
- Post Title: Shaiya Online [Solved]

This is blend file (Blender249) for import Character from Shaiya game.
It import:
- geometry
- uvmapping
- texture and material

How use:
- extract all files from game
- paste file in folder - Shaiya/Character/DeathEater or Elf or Human or Vile
- open blend and run script
- clik on MANUAL than each body part you must select
- clik on RANDOM than character is making full random.
[shaiya importer.rar](https://xentaxbackup.github.io/file/3493_shaiya importer.rar)
## Post #8
- Username: hopeloz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 28, 2010 7:44 am
- Post datetime: 2010-10-28T11:54:53+00:00
- Post Title: Shaiya Online [Solved]

Sorry if im ressurecting a thread, but when i try to run this script, it gives me an error on the line:
    Draw.PupBlock("HEROES",block) 
In the console tells me:
10/28/10 9:54:10 AM	[0x0-0x32032].org.blenderfoundation.blender[404]	Traceback (most recent call last):
10/28/10 9:54:10 AM	[0x0-0x32032].org.blenderfoundation.blender[404]	  File "import 3dc.py", line 217, in <module>
10/28/10 9:54:10 AM	[0x0-0x32032].org.blenderfoundation.blender[404]	  File "import 3dc.py", line 125, in choicerheroes
10/28/10 9:54:10 AM	[0x0-0x32032].org.blenderfoundation.blender[404]	ValueError: expected a string and a non-empty sequence.

Btw, im using MAC OSX Snow Leop.
## Post #9
- Username: jamessimpler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 02, 2010 12:42 pm
- Post datetime: 2010-12-17T15:59:29+00:00
- Post Title: Shaiya Online [Solved]

> Reply from delium
>
> anybody knows the format of the *.ani files?

Hopefully someone could manage to figure out the *.ani files format is.  I convert it to bvh but it didn't work. Sorry I am pretty new to all these too. Please anyone could help?
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T02:56:24+00:00
- Post Title: Shaiya Online [Solved]

lol, the first 3D format that got me started on the whole reversing thing. Mainly cause chrrox used it for his tutorial. And I realized there were two 3DC formats, but from the file alone you won't know until you crash.

First type has the numBones + bone Structs
Second type doesn't. I think only the mantles exhibit this behavior.

There's also no way to determine whether the format you're working with is actually a Shaiya Online model or not inside the file so it's purely based on the extension (I mean I guess you could check that the first 4 bytes is 0 but how accurate is that...?)



[http://xtsukihime.webs.com/Noesis%20Plu ... aOnline.py](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_ShaiyaOnline.py)

Spent 2 mins to write a noesis plugin for those SMOD, 3DO, and 3DC formats.

Not as cool as the blender script, but it can be refined.
Now to figure out how the functions for bones and stuff.........
## Post #11
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-15T15:55:10+00:00
- Post Title: Shaiya Online [Solved]

Nice! I like seing more maps not just models...witch maybe is the same thing in the end
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-15T16:12:19+00:00
- Post Title: Shaiya Online [Solved]

my zlib tutorial imports a model with bones.
also bullet witch does.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T20:20:48+00:00
- Post Title: Shaiya Online [Solved]

> Reply from pixellegolas
>
> Nice! I like seing more maps not just models...witch maybe is the same thing in the end

Usually the same format with some variations.
Though there are games that store them completely different.
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-01-17T02:55:04+00:00
- Post Title: Shaiya Online [Solved]

> Reply from fatduck
>
> This is a very very simple format! Here you go.
Code: Select alldword       constant00
dword       numBones
struct Bone {
   float_16 Matrix4X4   
}
dword       numVerts
struct Vert {
   float_3  CoordXYZ
   float    Weight
   byte     BoneID01
   byte     BoneID02
   float_3  NormalXYZ
   float_2  TexCoordUV
}
dword       numFaces
struct Face {
   word_3   FaceIndices123
}

Shaiya its amazing game, also someone made this amazing tools to mode the game:

[http://www.elitepvpers.com/forum/shaiya ... ditor.html](http://www.elitepvpers.com/forum/shaiya-pserver-development/1063024-release-shstudio-multi-purposes-editor.html)

But the last frontier its made the mod tool to mode the models, in other words made something script or tool to put back the models formats, if its really simple format like you tell, its posible send back the format?.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-17T04:06:41+00:00
- Post Title: Shaiya Online [Solved]

Doesn't the tool do all of that?
It looks like it's supposed to be a modding tool.
## Post #16
- Username: Reign
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Feb 23, 2012 4:22 am
- Post datetime: 2012-02-22T20:59:23+00:00
- Post Title: Re: Shaiya Online [Solved]

I too, am interested in a way that enables me to save the models after modified . Or to Import other  models ( Aion) nd be able to import them into Shaiya . For this  , I will even pay $$$$ .
