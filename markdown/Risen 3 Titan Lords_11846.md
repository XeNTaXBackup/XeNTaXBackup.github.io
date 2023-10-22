## Post #1
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-26T13:57:06+00:00
- Post Title: Risen 3 Titan Lords

Started playing this game a few days ago.  Decided to take it apart.

Really simple format, but it looks like some of the uv didn't read correctly.  Anyone seen uv results like this before?
Its like they put 2 textures side by side, and 1 uv map for both textures.  
The other odd thing is that it seems like the arms are part of the body mesh, but the uv and texture say no.

EDIT:  I think I see what's wrong now.  Looks like more than 1 mesh in the model file, but the header only has 1 size for the vertex block?
## Post #2
- Username: EcheloCross
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-26T15:23:24+00:00
- Post Title: Risen 3 Titan Lords

> EDIT: I think I see what's wrong now. Looks like more than 1 mesh in the model file, but the header only has 1 size for the vertex block?

I had the same issue with Tomb Raider. What they did was they specified 1 block of vertices and a block of face indices. You could just build the whole mesh out of this but the UVs were all overlapped and it wouldn't be suitable since the meshes consisted of multiple textures not one for the whole model.

They specified additional info related to smaller faces. These were just start indexes into the face indices. This made it simple, basically rather than reading all the face indices at once. You have to read them into smaller groups which should result in multiple meshes. I have seen this done with a couple of games but it sounds like that is your issue.

If this is the issue it should be stored in a small table somewhere... You could just add up all the face counts for the smaller meshes and it will match the overall count which you seem to have found.

Hope it makes sense!
## Post #3
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-26T16:28:31+00:00
- Post Title: Risen 3 Titan Lords

I see a little fvf table similar to the one in Risen 2.  
Not sure how to relate the data to the vertices and faces blocks though.

```

facesSize 
0000E86E 00000000 
vertsSize  vertsStride
0002D004 0000001C 

         partCount
00000000 00000005 
p1   p2   p3   p4
0000 0000 0200 0000 
0000 000C 0500 0200 
0000 0010 1000 0100 
0000 0018 0F00 0500 
00FF 0000 1100 0000 

unkSize  unkStride
00013494 0000000C

         unkCount
00000000 00000004 
up1  up2  up3  up4
0001 0000 1300 0300 
0001 0004 1300 0600 
0001 0008 0400 0A00 
00FF 0000 1100 0000 

0000 0000 0000 0000 
00000000

...some more examples from other files below
0001 0000 00000065 000023AC 00000000 

00006FC8 0000001C 

00000000 00000005 
0000 0000 0200 0000 
0000 000C 0500 0200 
0000 0010 1000 0100 
0000 0018 0F00 0500 
00FF 0000 1100 0000 

00002FE8 0000000C 

00000000 00000004 
0001 0000 1300 0300 
0001 0004 1300 0600 
0001 0008 0400 0A00 
00FF 0000 1100 0000 

0000 0000 0000 0000 
00000000


0001 0000 00000065 000516D2 00000000 

00116454 0000001C 

00000000 00000004 
0000 0000 0200 0000 
0000 000C 0100 0500 
0000 0014 0100 0501 
00FF 0000 1100 0000 

00077424 0000000C 

00000000 00000004 
0001 0000 1300 0300 
0001 0004 0400 0A00 
0001 0008 1300 0600 
00FF 0000 1100 0000 

0000 0000 0000 0000 
00000000

```
## Post #4
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2014-08-26T16:37:58+00:00
- Post Title: Risen 3 Titan Lords

Well I had similar problems with models from GTA:Sa and GTA IV, it's something wrong with the definitions of the meshes in the max script. Since my problem was only with few of the models, and all I did was to took them to editable mesh in 3d max and separate the two meshes. Btw.. I'm sure the character you showed has more textures, not just one. Another solution could be the use of multimaterials in 3d max (I didn't got it to work). 

Oh, I also have one stupid question, you're working on the new Risen game, how about the old one? Is it possible to get something from it?
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-26T16:40:46+00:00
- Post Title: Risen 3 Titan Lords

Multiple types of vertices is fairly common these days. It is normally controlled by a flag. I assume referred to as FVF? Just basic type info really. It's useful in some games for distinguishing what part of the buffer does what and can also be size related so you know the exact sizes you need to read, what each vert consists of ie, UVs, weights, normals etc. 

It seems like you know what you're doing. If you get stuck just ask me with a sample and I'll try help.

Cheers.
## Post #6
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-26T16:42:12+00:00
- Post Title: Risen 3 Titan Lords

> Reply from napoleon321
>
> 
Oh, I also have one stupid question, you're working on the new Risen game, how about the old one? Is it possible to get something from it?

chrrox wrote a python script for noesis for Risen 2.
[viewtopic.php?p=69140#p69140](http://forum.xentax.com/viewtopic.php?p=69140#p69140)
## Post #7
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-26T17:01:29+00:00
- Post Title: Risen 3 Titan Lords

For the ones with a vertex stride of 0x1C, the entries look like this.
I'm wondering if these u1 to u4 bytes are a mesh part flag?

```
C176EDFA 42A5276D C11EE9E2 00 01 00 02 2492 373A 383E 0000 3BA0 3898 
4163758E 42A8AEE6 41218A09 00 00 04 03 36D7 3894 0000 0000 3BC6 38DD
41521E4F 42B9E8F6 C11FFB16 00 04 03 02 2D0F 3AC1 2CE3 0000 3AF5 3899
41841D15 422EE546 40172FED 00 00 06 05 3B91 2AE7 0000 0000 3B35 2C31
41AB18C8 4181CE70 BD172474 00 06 07 05 3676 2250 38AB 0000 3B35 35AF

```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-26T22:22:42+00:00
- Post Title: Risen 3 Titan Lords

Is the model format similar to Risen 2 *._xskn?

For R2 Venturo I imported the obj separated by groups.
Groups created by inserting "g Mesh.00x" lines when creating the obj, x= 1..4 for Venturo xskn.

This is the loop for inserting grouping lines into an obj:

```
...
if ( (k==0)||(k==0xF66)||(k==0x24CC)||(k==0x4DB8) ) {   // manually because of *), see below
      fprintf( stream, "g Mesh.") ; fprintf( stream, szCnt) ; fprintf( stream, "\n") ;}
... // print faceindices
}
```


0xF66 for example is an index  defining the start of a new submesh.
Here's how to find them in R2 xskn:

```

000070  17 61 3E A8 15 C4 DF 15  23 00 00 00 21 00 41 6E   .a>¨.Äß.#...!.An
000080  69 5F 48 75 6D 5F 56 65  6E 74 75 72 6F 5F 42 6F   i_Hum_Venturo_Bo
000090  64 79 5F 48 61 6E 64 5F  31 2E 5F 78 6D 61 74 89   dy_Hand_1._xmat‰
0000A0  31 94 5D E0 66 89 E3 18  00 00 00 37 BC 7E C2 04
0000B0  65 BA 42 4C C8 A5 C0 61  54 7D 42 2D B2 F4 42 23
0000C0  B9 66 41 CD 93 3C B2 E5  6C 53 F5 04 00 00 00 00
0000D0  00 00 00 CD 93 3C B2 C6  43 81 2F 04 00 00 00>66
0000E0  0F 00 00<CD 93 3C B2 4B  28 79 BD 04 00 00 00 00

from '.' of ._xmat +54 bytes -> 00 00 00 00, fst submesh

009C1 Ani_Hum_Venturo_Body_Leather_1._xmat
from '.' of ._xmat +54 bytes -> 66 0F 00 00, 2nd submesh

Offset   0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

001E60  15 24 00 00 00 22 00 41  6E 69 5F 48 75 6D 5F 56   .$...".Ani_Hum_V
001E70  65 6E 74 75 72 6F 5F 42  6F 64 79 5F 43 6C 6F 74   enturo_Body_Clot
001E80  68 5F 31 2E 5F 78 6D 61  74 89 31 94 5D E0 66 89   h_1._xmat‰1”]àf‰
001E90  E3 18 00 00 00 08 3D 76  C2 0F DC 25 42 22 8E A3
001EA0  C1 08 3D 76 42 67 06 37  43 3B 5F A0 41 CD 93 3C
001EB0  B2 E5 6C 53 F5 04 00 00  00>CC 24 00 00<CD 93 3C

from '.' of ._xmat +54 bytes -> CC 24 00 00, 3rd submesh


Offset   0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

004520  A8 15 C4 DF 15 24 00 00  00 22 00 41 6E 69 5F 48   ¨.Äß.$...".Ani_H
004530  75 6D 5F 56 65 6E 74 75  72 6F 5F 42 6F 64 79 5F   um_Venturo_Body_
004540  4D 65 74 61 6C 5F 31 2E  5F 78 6D 61 74 89 31 94   Metal_1._xmat‰1”
004550  5D E0 66 89 E3 18 00 00  00 37 DA 73 C2 BE 9F DA
004560  42 D3 CD 98 C1 37 DA 73  42 66 66 39 43 76 71 9C
004570  41 CD 93 3C B2 E5 6C 53  F5 04 00 00 00>B8 4D 00
004580  00<                                                .

from '.' of ._xmat +54 bytes -> B8 4D 00 00, 4th submesh
```


(Normally you would search for "._xmat" in the xskn then add 54 to find the indices.
But I took care of Venturo and shani only so I didn't bother to check the +70 problem.)
edit: +70 was nonsense, it's +54 for all submeshes and the fst one starts at index 0



R2_Venturo.JPG (184.29 KiB) Viewed 342 times
## Post #9
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-27T01:31:10+00:00
- Post Title: Risen 3 Titan Lords

Still looking for info about the mesh parts, I see the addresses like you explained in the mat files
The entries that look similar to your info are the 0x6C880000 ones.  This is the size of the vertex buffer to use?

```
F44B34DE A3784BF9 B3827713 88250E57 00000031 0001A83E 61170D65 6C880000 0023 0021 : Hum_F_Body_Main_Patty_Fabric_1_Nm
C6CA9A00 F3BB4943 B48A477F 746B605B 00000031 0001A83E 61170D65 6C880000 0023 0021 : Hum_F_Body_Main_Patty_Fabric_1_Co
B7D0C9A8 4B224234 BC50F246 0FCB24E4 0000002A 00027AD5 03150CFA 22240000 000C3F4C ... no more strings in the mat file

```


also, looking through clo files, it looks like bones and other info are stored in the clo
in the entries below, I havent tested the ushorts yet for relations to the vertices and faces blocks, but the indices after the ushorts may point to another table with the info

```
00000132 00000000 00000001 257D A323 0000002B 00000001 01000000 : SEMANTIC_NORMAL
00000142 00000000 00000002 47A2 C413 0000002C 00000001 01000000 : SEMANTIC_TANGENT
00000153 00000000 00000005 4941 F51C 0000002A 00000000 01000000 : SEMANTIC_TEXCOORD0
00000166 00000000 00000009 10EF 7257 00000008 00000000 01000000 : SEMANTIC_BONE_INDEX
0000017A 00000000 0000000A 7CAE 59C9 0000002C 00000000 01000000 : SEMANTIC_BONE_WEIGHT
0000018F 00000000 FFFFFFFF D70C D6C0 0000000D 00000000 01000000 00000000 00000020 : DCC_INDEX

```


for bones, the joints are pointed to by table1 near the end of the clo file
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-27T01:58:50+00:00
- Post Title: Risen 3 Titan Lords

> Reply from EcheloCross
>
> Still looking for info about the mesh parts, I see the addresses like you explained in the mat files
The entries that look similar to your info are the 0x6C880000 ones.  This is the size of the vertex buffer to use?So the (x)mat strings are not contained in the model file? I could try to answer your question if you sent me a model sample.
The info where the submeshes to start should be contained in the model file.
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-27T13:05:39+00:00
- Post Title: Risen 3 Titan Lords

I looked at this format  yesterday, so I wrote script for it - but! I can't find counts/offsets for sub-meshes too. If we will find them, we are cool. Cuz everything else seems to work fine lol
[Girl.jpg](https://xentaxbackup.github.io/file/7752_Girl.jpg)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-27T13:19:17+00:00
- Post Title: Risen 3 Titan Lords

We might be required to have a look at the PhysX 3.2 SDK which was used to create the clo files.

While you can get the "transission" between submeshes for R2 xskn manually by just deleting enough face lines (f f1 f2 f3) from the end of the obj file this doesn't work for R3 skn:



Patty_fst_SM.JPG (150.3 KiB) Viewed 302 times
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-27T13:35:59+00:00
- Post Title: Risen 3 Titan Lords

Yeah, I did something similar with hat mesh, since it's easier lol. I divided mesh by sub-mesh referencing to game textures+unwrap Uvs and it looks right
[Girls.jpg](https://xentaxbackup.github.io/file/7754_Girls.jpg)
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-27T15:04:54+00:00
- Post Title: Risen 3 Titan Lords

Well I took a quick look. Doesn't look like the info is in the mesh file. If you ask me, It's most likely in the material file like the previous game stored it there? I think...

I would suggest working on a smaller mesh to make things easier.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-27T15:49:07+00:00
- Post Title: Risen 3 Titan Lords

but then there should be a difference between the mat file for body, fabric and hat, leather (apart from the strings and that one float value)?



mat_comparison.JPG (151.07 KiB) Viewed 287 times

(For R2 the mat strings were stored in the xskn, so were the face indices indicating the start of a new submesh. For R3 it might be the clo file.)

> Reply from zaramot
>
> [...] and it looks rightcool, 3 submeshes? Then you have the 2 face indices we're searching for?
Then you could start a search for them in all files come into question. (provided they use the same "system" as in R2. Guess, they don't.)

edit: ok, the missing data was supposed to be in a .db file that I don't have since I don't owe the game so far.
## Post #16
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-08-27T16:16:19+00:00
- Post Title: Re: Risen 3 Titan Lords

Use "...\0_na_skn\w_skn_0_na.db" - (binary file) - for searching needed name of material, mesh indice table offset and mesh indice count for each material
## Post #17
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-08-27T16:50:04+00:00
- Post Title: Re: Risen 3 Titan Lords

Looking through the db now

Looks like the model data block is shared by each material, which makes sense as to why the uv were overlapping when I originally read the whole model.

```

--Material: Hum_F_Body_Main_Patty_Fabric_1
B23C93CD F5536CE5 00000004 00000000 : amount to seek in face index block
B23C93CD 2F8143C6 00000004 00004F68 : face index count to read
B23C93CD BD79284B 00000004 00000000 : amount to seek in vertex info block
B23C93CD B99901EC 00000004 0000117B : vertices + uv + etc count to read
B23C93CD 0F2D41B1 00000004 00000000 : amount to seek for last data block?
B23C93CD 6ED76512 00000004 0000002A : count to read for last data block?

--Material: Hum_F_Body_Main_Patty_Skin_1
B23C93CD F5536CE5 00000004 00004F68 : amount to seek in face index block
B23C93CD 2F8143C6 00000004 00001D2E : face index count to read
B23C93CD BD79284B 00000004 0000117B : amount to seek in vertex info block
B23C93CD B99901EC 00000004 00000633 : vertices + uv + etc count to read
B23C93CD 0F2D41B1 00000004 0000002A : amount to seek for last data block?
B23C93CD 6ED76512 00000004 0000002E : count to read for last data block?

```


Finally got the sub mesh info reading from the db.  Thanks again for pointing me in the right direction Szkaradek123.
## Post #18
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-10T07:19:15+00:00
- Post Title: Re: Risen 3 Titan Lords

> Reply from EcheloCross
>
> Looking through the db now

Looks like the model data block is shared by each material, which makes sense as to why the uv were overlapping when I originally read the whole model.
Code: Select allModel : Hum_F_Body_Main_Patty_1_L1

--Material: Hum_F_Body_Main_Patty_Fabric_1
B23C93CD F5536CE5 00000004 00000000 : amount to seek in face index block
B23C93CD 2F8143C6 00000004 00004F68 : face index count to read
B23C93CD BD79284B 00000004 00000000 : amount to seek in vertex info block
B23C93CD B99901EC 00000004 0000117B : vertices + uv + etc count to read
B23C93CD 0F2D41B1 00000004 00000000 : amount to seek for last data block?
B23C93CD 6ED76512 00000004 0000002A : count to read for last data block?

--Material: Hum_F_Body_Main_Patty_Skin_1
B23C93CD F5536CE5 00000004 00004F68 : amount to seek in face index block
B23C93CD 2F8143C6 00000004 00001D2E : face index count to read
B23C93CD BD79284B 00000004 0000117B : amount to seek in vertex info block
B23C93CD B99901EC 00000004 00000633 : vertices + uv + etc count to read
B23C93CD 0F2D41B1 00000004 0000002A : amount to seek for last data block?
B23C93CD 6ED76512 00000004 0000002E : count to read for last data block?


Finally got the sub mesh info reading from the db.  Thanks again for pointing me in the right direction Szkaradek123.Very good game, can upload script, let everyone learn it, thanks，chrrox wrote a python script for noesis for Risen 2.Support only xmesh models do not support character models
## Post #19
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-11-14T19:42:10+00:00
- Post Title: Re: Risen 3 Titan Lords

Nice work EcheloCross, Szkaradek123, shakotay2, zaramot.
## Post #20
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-16T18:29:35+00:00
- Post Title: Re: Risen 3 Titan Lords

Hi
Here is an importer for textured models (*.skn ) from this game. No weighting. No skeleton. 
It requires Blender 249 and Python 26.
How use:
Please read readMe.txt
[Blender249[Risen3][PC][pak][skn][2015-02-16].zip](https://xentaxbackup.github.io/file/8692_Blender249[Risen3][PC][pak][skn][2015-02-16].zip)
## Post #21
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-17T14:09:03+00:00
- Post Title: Re: Risen 3 Titan Lords

cool ！ Hi Szkaradek123 My friend, thank you very much for the great work, the script runs perfectly.
