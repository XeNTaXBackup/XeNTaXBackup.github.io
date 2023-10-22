## Post #1
- Username: Rimbros
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-01T23:58:09+00:00
- Post Title: DK Online (XAC)

[http://www.dkonline.co.kr](http://www.dkonline.co.kr)
Client
[http://full-dkonlinedn.cdn.x-cdn.com/dk ... eSetup.zip](http://full-dkonlinedn.cdn.x-cdn.com/dkonline/DKOnlineSetup.zip) 
Quickbms script

```
math zsize - 4
goto zsize
get offset long
print "%offset%"
math offset - 4
goto offset
get files long
savepos offset
math zsize - offset
set size files
math size * 0x114
clog MEMORY_FILE offset zsize size
for i = 0 < files
getdstring name 0x104 MEMORY_FILE 
get size long MEMORY_FILE 
get zsize long MEMORY_FILE 
get offset long MEMORY_FILE 
get null long MEMORY_FILE 
clog name offset zsize size
next i
```

model converter here
[viewtopic.php?f=16&t=6348](http://forum.xentax.com/viewtopic.php?f=16&t=6348)

Edit.
It needs a few tweaks ill update it tomorrow.
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-02T09:55:37+00:00
- Post Title: DK Online (XAC)

I love this game, thanks chroxxx very good release.
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-11-02T21:17:16+00:00
- Post Title: DK Online (XAC)

very nice but it look like a L2+TERA copy  nice work chrox anyway.
## Post #4
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2011-11-07T20:45:41+00:00
- Post Title: DK Online (XAC)

I have to admit all these games are starting to merge into one for me. Can't help but feel that they all look completely alike.
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-11-08T01:32:26+00:00
- Post Title: DK Online (XAC)

hi chrox again, well you say need edit some tips, you finish it? because say tomorrow and after 7 days no news of you, anyway thanks a lot for all support in forum.

PD: trying import xac files and doesn't work I get it with 3D Studio Max 9.

```
-- Error occurred in anonymous codeblock
--  Frame:
--   size: undefined
--   type: undefined
--   type2: undefined
-- Error occurred during fileIn in <File:C:\Program Files (x86)\Autodesk\3ds Max 9\stdplugs\stdscripts\DK Online 3D Importer by chrox.ms>
>> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Integer <<
```


XAC Header

```
0000001F 00 00 00 00 00 2D 00 00 00 33 44 20 53 74 75 64 69 6F 20 4D 61 78 20 31 32 20 28 72 65 67 75 .....-...3D Studio Max 12 (regu
0000003E 6C 61 72 20 63 6F 6D 6D 65 72 63 69 61 6C 20 76 65 72 73 69 6F 6E 29 3A 00 00 00 44 3A 5C 50 lar commercial version):...D:\P
0000005D 72 6F 6A 65 63 74 20 41 47 20 53 56 4E 5C 47 72 61 70 68 69 63 5C 4D 6F 64 65 6C 5C 49 74 65 roject AG SVN\Graphic\Model\Ite
0000007C 6D 5C 49 74 65 6D 5F 44 69 6D 5C 44 69 6D 5F 30 30 30 31 2E 6D 61 78 0B 00 00 00 4A 75 6C 20 m\Item_Dim\Dim_0001.max....Jul 
0000009B 32 30 20 32 30 31 30 00 00 00 00 0B 00 00 00 57 01 00 00 01 00 00 00 02 00 00 00 02 00 00 00 20 2010........W...............
000000BA 00 00 00 80 00 00 00 80 00 00 00 80 00 00 80 3F 00 00 00 80 00 00 00 80 00 00 00 80 00 00 80 ...............?...............
000000D9 3F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 00 00 80 3F 00 00 80 3F 00 00 80 BF 00 00 ?...............?...?...?......
000000F8 80 BF 00 00 80 BF FF FF FF FF FF FF FF FF FF FF FF FF 00 00 00 00 F1 F4 B2 36 9D 06 7F 3F 00 .........................6...?.
00000117 00 00 00 B9 7E B2 BD 70 20 47 41 00 00 00 00 00 00 80 3F 00 00 00 00 E7 B7 1C 40 B9 7E B2 3D ....~..p GA.......?.......@.~.=
00000136 00 00 00 80 9D 06 7F 3F F9 61 31 42 51 A9 9A 3F 7F 3D 17 40 C6 FC EF 40 00 00 80 3F 00 00 80 .......?.a1BQ..?.=.@...@...?...
00000155 3F 08 00 00 00 44 69 6D 5F 30 30 30 31 00 00 00 80 00 00 00 80 00 00 00 80 00 00 80 3F 00 00 ?....Dim_0001...............?..

```
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-10T01:49:47+00:00
- Post Title: DK Online (XAC)

Well i tested too in max 2010 and its the same, the script for .xac files doesnt work, i think maybe chroxxx see its the same extension (.xac) and he asume the script work by defaulth. Its the same format in valiant, but valiant have 2 formats, .xac (decritped) and .xgeom (not decripted yet).
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-10T03:05:34+00:00
- Post Title: DK Online (XAC)

they changed one part of this format the mesh part is identical they changed the bones have not gotten to it yet i skipped the bones in my script and the model imported fine.
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-10T03:08:41+00:00
- Post Title: DK Online (XAC)

well if you can post the script with the bones excluded and this can import the meshes, its fine.
## Post #9
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-11-22T16:02:02+00:00
- Post Title: DK Online (XAC)

I have the same error inm Max 2011 --Unabe to convert:undefined to type:Integer
Is there plans to fix this?
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-22T17:23:03+00:00
- Post Title: DK Online (XAC)

Something advance in the chroxxx script?
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-01-15T12:27:25+00:00
- Post Title: DK Online (XAC)

Any news about import script? Can someone post modified max script without bones? This game looks very nice.
## Post #12
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-02-02T00:33:23+00:00
- Post Title: DK Online (XAC)

Any news about import script?
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-02T17:51:16+00:00
- Post Title: DK Online (XAC)

> Reply from logansan25
>
> Any news about import script?

script for .xac files doesnt work, its buged and have errors, maybe a error in the develop of the script, and btw i think chroxxx cant fix this coz 2 reasons, he not have time or its hard also for he fix this, the post its from november 2011, then start lost the hope.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-05T01:30:27+00:00
- Post Title: DK Online (XAC)

Post some samples I only have xac files for war of dragons and argos (I thought I already DL'd the game but guess not)

Plus I want to re-do the xac import script so it's not just jumping everywhere and looping all over the place and using breaks...
## Post #15
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-05T07:02:26+00:00
- Post Title: DK Online (XAC)

> Reply from finale00
>
> Post some samples I only have xac files for war of dragons and argos (I thought I already DL'd the game but guess not)

Plus I want to re-do the xac import script so it's not just jumping everywhere and looping all over the place and using breaks...ok here I upload files, thanks a lot for yout try and effort here, grateful for all your support.

[DK Online Samples](http://www.mediafire.com/?m666kgo6l35nbc3)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T23:32:39+00:00
- Post Title: Re: DK Online (XAC)

Nice.

Ok, I looked at the xac file using chrrox's maxscript for reference, and it's the typical chunk-based format.

One problem I see is the material chunk. There might be an extra struct afterwards which doesn't follow the proper chunk-based format for whatever reason (maybe they just hacked it in lol).

Anyways this is how I handled the materials in DK online:

```
        
        self.inFile.read('16f')
        power = self.inFile.readFloat()
        self.inFile.read('4f')
        matName = self.read_name()
        
        #stuff in DK online
        unk = self.inFile.readFloat()
        while unk == 1:
            self.parse_material_extra()
            unk = self.inFile.readFloat()
        else:
            self.inFile.seek(-4, 1)

```


There are several ways to deal with it, but considering the range of numbers used for chunks, if you don't get an integer less than 100 or something, then you know it's the extra data (and any float parsed as an integer will probably be much larger than 100 anyways)
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T00:22:10+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> Nice.

Ok, I looked at the xac file using chrrox's maxscript for reference, and it's the typical chunk-based format.

One problem I see is the material chunk. There might be an extra struct afterwards which doesn't follow the proper chunk-based format for whatever reason (maybe they just hacked it in lol).

Anyways this is how I handled the materials in DK online:
Code: Select alldef parse_material(self):
        
        self.inFile.read('16f')
        power = self.inFile.readFloat()
        self.inFile.read('4f')
        matName = self.read_name()
        
        #stuff in DK online
        unk = self.inFile.readFloat()
        while unk == 1:
            self.parse_material_extra()
            unk = self.inFile.readFloat()
        else:
            self.inFile.seek(-4, 1)


There are several ways to deal with it, but considering the range of numbers used for chunks, if you don't get an integer less than 100 or something, then you know it's the extra data (and any float parsed as an integer will probably be much larger than 100 anyways)
well great news so about chrox MaxScript not work, he say need be changed some in Importer but no respond anymore so maybe you can take a look and adapt it to Noesis, thanks finalle00, really you doing a great job in community, maybe you can promoved to Moderator
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T00:25:02+00:00
- Post Title: Re: DK Online (XAC)

Being a moderator probably means you might have to actually do some work like move topics that are in the wrong forum or listen to boring reports or to uphold some level of professionalism (eg: following the rules even more than a regular member)

I've been wanting to write a noesis plugin for the xac format but didn't really feel like it whenever I looked at the existing plugins where they were just jumping all over the places. But then if it's just a chunk-based format then it's easy. I'm not a big fan of offset seeking, but I think that is the only choice you have in maxscript.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T01:01:22+00:00
- Post Title: Re: DK Online (XAC)

k someone upload a couple models with their textures. I can't seem to find my samples for war of dragons or argo OR valiant.......
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T03:19:14+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> k someone upload a couple models with their textures. I can't seem to find my samples for war of dragons or argo OR valiant.......

Does the company have anymore games?ok here samples finale00, about others games well yes, they have a lot more games, here you have the web site.

[http://www.mgame.com/](http://www.mgame.com/)

[Valiant 3D Samples [Samples]](http://www.mediafire.com/?2qc0qtifi3zv72d)



[Argo 3D Samples [Samples]](http://www.mediafire.com/?m9uxp6mz667z4vd)
## Post #21
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T03:39:37+00:00
- Post Title: Re: DK Online (XAC)

Hmm, I don't really understand how the materials work.
One of the models is referencing material index 2 (so third material), but I have no clue which one that is.

Chunk 3 and chunk 4 are confusing.
Chunk 3 looks like material definitions, and chunk 4 defines which texture *some* material uses.

Several models may be using like 4-5 materials; it's not obvious which texture goes with which material.

Some models have less materials than textures, because there are normal and diffuse textures both assigned to a particular material.
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T04:23:51+00:00
- Post Title: Re: DK Online (XAC)

Ok I hacked around with some numbers in chunk 4 and it seems to work.
Mainly because I really can't follow what the other two scripts are doing...

Chunk 4 looks like this

```
int16 ?
int16 ?
texName

```


I took the first integer and used that as the material index. Sometimes it's greater than however many materials are defined, so I just skipped those.

I also had to check the texName because War of Dragons models use diffuse and normal texture maps, whereas Argos, Valiant, and DK Online don't.

[http://db.tt/WlwzHo43](http://db.tt/WlwzHo43)

Verify that the textures are applied properly.
Again, model loading config is at the top of the script.
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T05:34:25+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> Ok I hacked around with some numbers in chunk 4 and it seems to work.
Mainly because I really can't follow what the other two scripts are doing...

Chunk 4 looks like this
Code: Select allfloat[6] ?
int16 ?
int16 ?
texName


I took the first integer and used that as the material index. Sometimes it's greater than however many materials are defined, so I just skipped those.

I also had to check the texName because War of Dragons models use diffuse and normal texture maps, whereas Argos, Valiant, and DK Online don't.

http://db.tt/WlwzHo43

Verify that the textures are applied properly.
Again, model loading config is at the top of the script.cool work mate, thanks a lot for it, now I downloading others MMO of this company MGAME, anyway thanks again for your support, really gratefull.
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T06:49:47+00:00
- Post Title: Re: DK Online (XAC)

Here's the plugin for the textures.
It can probably be more efficient...

[http://db.tt/y25FyG9Z](http://db.tt/y25FyG9Z)
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T07:06:31+00:00
- Post Title: Re: DK Online (XAC)

yeah ofc this is better, is a pain ass convert all xtex to dds, with is think is more usefull , thanks a lot again for your great contributions, maybe you can take a look this topic, I read a topic you request for get Client Ilgh 

[[Request] Ilgh](http://forum.xentax.com/viewtopic.php?f=18&t=8263)
## Post #26
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-12T09:17:12+00:00
- Post Title: Re: DK Online (XAC)

maybe you can promoved to Moderator [/quote]

Not please, dont become moderator, if finale become moderator the users of this 3D models area like me are lost, coz same chroxxx i sure he not release good thinks this days because he its bussy checking all the treadhs and helping all the people, finale dont go to the heaven with this boys, continue here with the mortals bro.
## Post #27
- Username: archiryo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 15, 2012 11:47 pm
- Post datetime: 2012-02-15T16:36:47+00:00
- Post Title: Re: DK Online (XAC)

does any ones know how to download this game? (i can't download from offical web)
## Post #28
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-02-16T05:59:55+00:00
- Post Title: Re: DK Online (XAC)

> Reply from archiryo
>
> does any ones know how to download this game? (i can't download from offical web)
 
[http://full-dkonlinedn.cdn.x-cdn.com/dk ... ine_FT.exe](http://full-dkonlinedn.cdn.x-cdn.com/dkonline_exe/DKOnline_FT.exe)
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-02-16T15:06:50+00:00
- Post Title: Re: DK Online (XAC)

Models rly awesome 

[http://i42.tinypic.com/hwiyo2.png](http://i42.tinypic.com/hwiyo2.png)
[http://i42.tinypic.com/970bro.png](http://i42.tinypic.com/970bro.png)
[http://i42.tinypic.com/1qqyx2.png](http://i42.tinypic.com/1qqyx2.png)
[http://i43.tinypic.com/fxc5yv.png](http://i43.tinypic.com/fxc5yv.png)

But for some reason in the game does not display the models. I hope it affects ping. Somebody have same problem? 
[http://i40.tinypic.com/28a6mp4.png](http://i40.tinypic.com/28a6mp4.png)
## Post #30
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-02-17T08:32:42+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> k someone upload a couple models with their textures. I can't seem to find my samples for war of dragons or argo OR valiant.......

I find this.
for fatduck

```
byte[4]  Version
dword[5] ?
byte  numString
byte[3]  ?
dword  ?
struct Stg {
   dword Len
   char[Len] FileReference
}
dword[4] ?
dword  numBone
dword  ?
struct Bone {
   float[4] QuatXYZW
   float[4] QuatXYZW //animation reference
   float[3] PosXYZ
   float[3] ScaleXYZ
   float[3] ?  //inverse scale!?
   dword[2] ?
   dword ParentID
   dword numChild
   dword ?
   float[12] Matrix4X3 //Axis Matrix
   float[3] WorldPosXYZ
   float[2] ?
   dword Len
   char[Len] BoneName
}
dword[3] ?
dword  *numMaterial
dword  *numMaterial //same as about!?
dword  ?
struct Material {
   dword[3] ?
   float[4] ColorRGBA
   float[4] ColorRGBA
   float[4] ColorRGBA
   float[4] ColorRGBA
   float SpecularPower
   dword[3] ?
   byte[3] ?
   byte  numTexture
   dword Len
   char[Len] MaterialName
   struct Texture {
      float[6] ?
      word ?  
      word TextureType
      dword Len
      char[Len] TextureName   
   }
}

struct Mesh {
   dword BlockType //1
   dword[2] ?
   dword ParentID
   dword numSkinIndices
   dword numVerts
   dword numFaceIndices
   dword numFacePart
   dword numVertElement
   dword ?
   struct VertElement {
      dword elementType //0=coordinates, 1=Normals
      dword BytesPerElement //3=UVs, 5=Slinindices4
      word elementID
      word ?
      <Data>
   }
   struct Face {
      dword numPartIndices
      dword numPartVerts
      dword MaterialID
      dword numUsedBone
      <Data> 
   }
}
struct SkinData {
   dword BlockType //2
   dword[2] ?
   dword MeshID
   dword numwSkinIndices
   dword numWeightBonePair
   dword ?
   struct WeightBonePair {
      float Weight
      dword BoneID
   }
   struct SkinIndex {
      dword Index
      dword numSkinInPair
   } 
}
```
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-24T18:37:32+00:00
- Post Title: Re: DK Online (XAC)

Works amazing for .xac files how its posible load texture and model in Noesis preview to see the models?.
## Post #32
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-24T19:11:33+00:00
- Post Title: Re: DK Online (XAC)

> Reply from Rimbros
>
> Works amazing for .xac files how its posible load texture and model in Noesis preview to see the models?.here you have script for xtex.
[fmt_DKOnline_xtex by finale00.7z](https://xentaxbackup.github.io/file/5105_fmt_DKOnline_xtex by finale00.7z)
## Post #33
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-02-24T19:23:45+00:00
- Post Title: Re: DK Online (XAC)

Where are script for models? The scripts is for noesis?
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T22:33:37+00:00
- Post Title: Re: DK Online (XAC)

Scripts are in my dropbox folder.
All scripts that I write should be linked there because they may change whenever I feel like updating them.

It is clear that I've been very lazy and unmotivated and never went to look at how to add bones or animations or anything.
## Post #35
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-08-21T23:30:45+00:00
- Post Title: Re: DK Online (XAC)

I'm stuck on the texture part. I only have .xac files. Which package has the .xtex files?
## Post #36
- Username: SaintDaveUK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 06, 2012 10:03 pm
- Post datetime: 2012-09-07T09:43:37+00:00
- Post Title: Re: DK Online (XAC)

Hi, I've been trawling the web for ages for a way to open *.XAC models from Paradox games like Crusader Kings 2 and Europa Universalis 3. Then I came across this.

I can't get this script to work for these games, I presume they have different code depending on the developer, and it needs to be modified to be compatible?
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-07T16:55:20+00:00
- Post Title: Re: DK Online (XAC)

They might be two completely different formats.
If it isn't chunk-based (cause different XAC versions here are basically the same format, then it's likely something else.
## Post #38
- Username: SaintDaveUK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 06, 2012 10:03 pm
- Post datetime: 2012-09-07T17:23:39+00:00
- Post Title: Re: DK Online (XAC)

How would I go about checking whether it is chunk-based?
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-07T17:47:16+00:00
- Post Title: Re: DK Online (XAC)

Upload a sample.
## Post #40
- Username: SaintDaveUK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 06, 2012 10:03 pm
- Post datetime: 2012-09-08T11:55:44+00:00
- Post Title: Re: DK Online (XAC)

Here
[Western_Heavy_Infantry.zip](https://xentaxbackup.github.io/file/5781_Western_Heavy_Infantry.zip)
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-08T17:09:07+00:00
- Post Title: Re: DK Online (XAC)

Oh, it's the same format. Or at least, similar. And a lot of the games from that site have the same format?

I wonder what the XAC format is. At the top you can see it has export information describing what 3D software they used to create the model.

I might have to rename the plugin lol

Anyways there's some extra chunks in there. I'll need more samples to verify what they are.
## Post #42
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-22T17:19:26+00:00
- Post Title: Re: DK Online (XAC)

It looks like the 0xD chunk was there all along I just skipped it and never noticed.



cruskings.JPG (21.07 KiB) Viewed 182 times
## Post #43
- Username: SaintDaveUK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 06, 2012 10:03 pm
- Post datetime: 2012-09-23T11:40:50+00:00
- Post Title: Re: DK Online (XAC)

Wow excellent work mate.

So what can we do with this? Is it only possible to read and not write?
## Post #44
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-23T16:22:22+00:00
- Post Title: Re: DK Online (XAC)

You will need to write your own tools for that. Most of the format is still unknown.
## Post #45
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-10-14T10:08:10+00:00
- Post Title: Re: DK Online (XAC)

Can anyone pm me some DK online samples, Rimbros isn't responding.
## Post #46
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-14T15:48:06+00:00
- Post Title: Re: DK Online (XAC)

lol I was going to send something but then I realized the samples weren't on this computer.
And it looks like the model repository died lol

Let's use skydrive
## Post #47
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-10-14T16:17:19+00:00
- Post Title: Re: DK Online (XAC)

What in the world is skydrive.
## Post #48
- Username: peto1488
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Jan 28, 2012 7:26 am
- Post datetime: 2012-11-24T01:47:31+00:00
- Post Title: Re: DK Online (XAC)

DK online extract all pak files = msh and dds not xac...does anyone have script for msh?
## Post #49
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-24T04:21:51+00:00
- Post Title: Re: DK Online (XAC)

Send samples I don't have the client on me.
## Post #50
- Username: peto1488
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Jan 28, 2012 7:26 am
- Post datetime: 2012-11-24T17:47:16+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> Send samples I don't have the client on me.

Ok.

[http://www.2shared.com/file/l3G6x1wv/test.html](http://www.2shared.com/file/l3G6x1wv/test.html)
Virustotal:

[https://www.virustotal.com/file/a980b9c ... 353779151/](https://www.virustotal.com/file/a980b9ca775346aed093085ad2fb086cf122542cbac265f1ccf43d52715de4a6/analysis/1353779151/)
## Post #51
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-24T21:26:01+00:00
- Post Title: Re: DK Online (XAC)

There's a huge chunk of zlib compressed data somewhere in the middle. Not sure if I'm supposed to parse the stuff around it.
## Post #52
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-11-29T04:29:38+00:00
- Post Title: Re: DK Online (XAC)

Cmon, the last version of fathduck importer already have .XAC support.
## Post #53
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-11-29T18:52:17+00:00
- Post Title: Re: DK Online (XAC)

So? Not everyone wants to use 3ds max and I take writing these scripts as a learning opportunity.
Unless you have anything constructive to add it's time to butt out.
## Post #54
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-12-15T04:45:51+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> There's a huge chunk of zlib compressed data somewhere in the middle. Not sure if I'm supposed to parse the stuff around it.

chunryong (xac)

Site:[http://chunryong.wemade.com/main](http://chunryong.wemade.com/main)

Sample:[http://dl.dropbox.com/u/62180803/pcsw.rar](http://dl.dropbox.com/u/62180803/pcsw.rar)

Open Error

```
mat block
here, chunk 5 24267
Traceback (most recent call last):
  File "C:\noesis\plugins\python\fmt_DKOnline_xac.py", line 89, in noepyLoadModel
    load_single_model(data, mdlList)
  File "C:\noesis\plugins\python\fmt_DKOnline_xac.py", line 76, in load_single_model
    parser.parse_file(basename)
  File "C:\noesis\plugins\python\fmt_DKOnline_xac.py", line 390, in parse_file
    self.build_meshes()
  File "C:\noesis\plugins\python\fmt_DKOnline_xac.py", line 170, in build_meshes
    mat = self.matList[matNum]
IndexError: list index out of range
```
## Post #55
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-12-15T06:20:16+00:00
- Post Title: Re: DK Online (XAC)

I have updated the DK_Online script with revised parsing for material chunk 5.

I am not sure if this breaks support for yulgang 2 since I have added a couple values to read (no samples on me to check).

The UV's look a little messed up though not sure if it will look good.
## Post #56
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2012-12-15T09:09:30+00:00
- Post Title: Re: DK Online (XAC)

> Reply from finale00
>
> I have updated the DK_Online script with revised parsing for material chunk 5.

I am not sure if this breaks support for yulgang 2 since I have added a couple values to read (no samples on me to check).

The UV's look a little messed up though not sure if it will look good.



Material does not

chunryong sample:[http://dl.dropbox.com/u/62180803/pcsw_body_02.rar](http://dl.dropbox.com/u/62180803/pcsw_body_02.rar)
