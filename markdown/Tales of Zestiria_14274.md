## Post #1
- Username: chiri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 27, 2016 12:58 am
- Post datetime: 2016-04-26T17:23:44+00:00
- Post Title: Tales of Zestiria

Hi

After some hacking I managed to rip static objects directly from the model files. But I'm struggling with the animated model files: The index buffer and texture coordinate data is stored separately from the vertex data. The vertex data itself is stored directly in a hierarchical bone structure, which is too complicated for me to analyze at the moment.
The attached Edna model was ripped using NinjaRipper, but what I'm after is the bone animatable raw vertex data.

Here is what I got so far:
Extract the "TLFILE.TLDAT" and "FILEHEADER.TOFHDB" containers using quickbms with the "tales_of_xillia.bms" profile.
Texture descriptions are then exported in "TOTEXB_D\*.dpd" and the textures itself in "TOTEXP_P\*.dat".
Model animations are stored in "TOMDLB_D\*.dpd" and static model data is stored in "TOMDLP_P\*.dc5".
Run the attached code to extract DirectX DDS textures from the TOTEXP_P folder. Example: "CHR_EDN_TEN_100_CHEST0_C.dds", "CHR_EDN_TEN_100_HAIRBAND0_C.dds" and so on.
Run the attached code to extract OBJ model files from static models in the TOMDLP_P folder. Example: "ATT_106_FLO_00.obj"
Animation data is stored in ".toanmb"-files.

Any help parsing the animation data please?
[EdnaSwimSuit2.jpg](https://xentaxbackup.github.io/file/10839_EdnaSwimSuit2.jpg)
## Post #2
- Username: chiri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 27, 2016 12:58 am
- Post datetime: 2016-04-26T17:30:10+00:00
- Post Title: Tales of Zestiria

I can only attach one file per post. So here's the code to extract the textures and model data.
[Program.zip](https://xentaxbackup.github.io/file/10840_Program.zip)
## Post #3
- Username: chiri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 27, 2016 12:58 am
- Post datetime: 2016-04-26T17:41:36+00:00
- Post Title: Tales of Zestiria

And here is an example of the Edna bone animation model containing the vertex data. The nodes are named like "DB_XNECKRIBBON1_1_R", "DB_HOOD1_1_BR", "DB_HOOD1_1_BL" and so on.

My goal is to modify the vertex data and store it back into the game for a better gaming experience.
[CHR_EDN_TEN_100_CHEST_MI.zip](https://xentaxbackup.github.io/file/10841_CHR_EDN_TEN_100_CHEST_MI.zip)
## Post #4
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2016-07-05T00:58:37+00:00
- Post Title: Tales of Zestiria

how to use the program?
## Post #5
- Username: jusete
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Oct 19, 2014 8:00 pm
- Post datetime: 2016-08-31T01:06:43+00:00
- Post Title: Tales of Zestiria

Hey friend, How I can extract the models? I extracted the package with quickBms but I don´t know how to figure out the obj models
## Post #6
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T16:53:31+00:00
- Post Title: Tales of Zestiria

at "CHR_EDN_TEN_100_CHEST_MI.toanmb"
offset 0xC8 

```
                      neck ribbon l
        group-00  hood x2                bone 2->7
                      cloth x4
```

offset 0x108

```
         "DB_XNECKRIBBON1_1_R" words= 19 , 0x30-0x20=0x10=16
         ....                                                  0x40-0x30=0x10
         "DB_HOOD1_1_BR"           words= 13 , 0x4a-0x40=0xa =10
         "DB_CLOTH1_1_BR "(space)        words=15  ,0x56-0x4a=12
         "DB_CLOTH1_1_R"            words=13    0x60-0x56=      =10
         "DB_HOOD1_1_BL"            words=13   0x6a-0x60=       =10
         "DB_CLOTH1_1_BL "(space)        words=15  ,0x76-0x6a  =12
```


=========================
in other words,
from offset 0x108
         move 0x20    ##two line down
         get the bone name start address    ## bone name="DB_XNECKRIBBON1_1_R"

from offset 0x10B 
        move 0x30    ##three line down  
        get the 2nd bone name start address ## bone name = "DB_XNECKRIBBON1_1_L"   
....
frome offset 0x124
        move 0x76
        get    0x19A                                 ##bone name="DB_CLOTH1_1_L"
## Post #7
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T17:36:46+00:00
- Post Title: Tales of Zestiria

FROM offset 0x1ac  TO  0x5ac
0x5AC - 0x1AC = 0x400=1024
   8bone                       1024/8= 128
x,y,z,w 4 float number    128/16=8 key frame
       #####w 0 or 1 ,appear many times 

but here ,it would be posible 4x4 matrix

```
 B1 B2 B3   0
 C1 C2 C3   0
 D1 D2 D3  1}
```
 
it looks like a ”no scale（size）transform “ 4x4 matrix

and then compare 0x1ac and after 0x10x4linex8bone offset
                                       that is 0x3ac
                        their matrix
 = = only guess 
  A1
{0.75}       <==>     0.75
0.75          <==>      0.75
-0.037       <==>     -0.037
0.184        <==>     0.184
0.365        <==>     0.365
-0.0375     <==>     -0.0375    
0.184        <==>     0.184
0.365        <==>     0.365

find it that A1 stay the same value, A2 ,A3 changes 
continue find it that
               A1 
                    B2
                         C3
                   stay the same value
so taht ,this matrix possible have "move transform" only
## Post #8
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T18:44:03+00:00
- Post Title: Tales of Zestiria

```
     B2
          C3
               1}
stay the same value

```


does this  anime data only have two key frame?
or above matrix is bone matrix (70% possibility ，consider order ：bone-mesh-animetion)
look down , 
offset 0x5b0

```
     ......
       
```

offset:0x61c
       8 (obejects?) 

offset: 0x628

```
        0.5   0     1       1
        5      π     π       π    ## π=3.14159...
        0.17  0    1       -6.6

= = in fact ,when i saw "0 0 0.1 0.1 0.5 0 1 1" and then number>1 .
i guess the numbers(which>1) would be  <x,y,z> 

so from offset 0x62c skip 0x20 
           ot offset 0x64c read 3 floats as <x,y,z> (which first one is x=y=z=π)
from 0x628 to 0x693 as a part ,0x694-0x628 =0x6c      

```
 
it is

```
        ??     : 2 lines skip 0x20
        <x,y,z>??? :  3 float     like (1,0.5)*π 
        ....

```

this types parts appear 8 times
## Post #9
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T19:02:17+00:00
- Post Title: Tales of Zestiria

ok ， look back to 0x1a0
print (C1 C2 C3)  #IF here is bone matrix ,(C1, C2 ,C3)is bone position (x,y,z)

```
1st: -0.757      120           3.38                   left
2nd  0.757       120          3.38                   right

3rd  -5.5         112           6.49                  hood b right

4th   -4.4        97             2.63                  cloth b right
5th   -9.6        102           -3.02                 cloth right

6th   5.5         112           6.49                  hood b left

7th   4.4         97            2.63                   cloth b left
8th   9.6         102          -3.02                  cloth left

```
 
BINGO!!

and then 9th-16th is what?
## Post #10
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T19:43:46+00:00
- Post Title: Tales of Zestiria

= =CAN NOT FIND vertex_index to  build face
     CAN NOT FIND  X Y Z W   quaternion to build animetion
## Post #11
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-01T20:44:25+00:00
- Post Title: Tales of Zestiria

= = animetion data isobviously in "TOANMB"and "TOANMSB" 
“MDL” 〉〉model ..bone+mesh+weight+material ONLY
[tales.png](https://xentaxbackup.github.io/file/11646_tales.png)
## Post #12
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2016-09-04T18:03:23+00:00
- Post Title: Tales of Zestiria

Now...
is there a way to import the models (probably with animations) into 3dsmax or similar yet?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-06T00:01:41+00:00
- Post Title: Tales of Zestiria

Most confusing thread I've ever read.  

1. it doesn't make sense to care for animation data as long as you don't have the skeleton, imho
2. give the .toanmb file some structure (search for "EDN_" for example)

```
0B20   30 80 00 00 CA 02 00 00  3A 01 00 00 90 00 00 00 
                 0x2CA -> 714 (x28)
```


```
94F0   88 AD 00 00 49 00 00 00  5B 00 00 00 23 00 00 00 
                 0x0049 -> 73 (x28)
```


At 0x9504 and 0x11C1C there's promising point clouds:



charEdnTen100ChestMi.jpg (240.07 KiB) Viewed 663 times
## Post #14
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-06T06:33:48+00:00
- Post Title: Tales of Zestiria

this a file from DLC (story of alisha) in "DATADLC\008\EXTRA\WIN\TOMDLP_P"
which player angrily  call it "真の仲间"


file：
[https://mega.nz/#!VkBHWJzJ!WqHpQl1I__hV ... OraNgEyINo](https://mega.nz/#!VkBHWJzJ!WqHpQl1I__hV1Gis4gcJU_EK7mvpHbuWJOraNgEyINo)
[tales 0b8f.png](https://xentaxbackup.github.io/file/11663_tales 0b8f.png)
## Post #15
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-06T07:20:53+00:00
- Post Title: Tales of Zestiria

in “CHR_EDN_TEN_100_CHEST_MI.toanmb”

```
                                                                         the part is offset 0xb34 - 0x594C
                                                                         FVF size = 28
                                                                         (0x594C-0xb34)/28= 714

```

as the name "HAND_0_L_EDN......"
[hand.png](https://xentaxbackup.github.io/file/11665_hand.png)
## Post #16
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-06T08:05:22+00:00
- Post Title: Re: Tales of Zestiria

before look down 
let me explore the reason  FVFsize change from 28 to 32

when FVFsize==28

```
position :   x  y  z
normal? :   float float float
bone index:   for example (17) / 00 /00/ 00

```
 

when FVFsize==32  (from 0x594c)

```
position :   x  y  z
normal? :   float float float
bone index1:   for example (13)/bone index2:   for example (12) /00 00
weight:     float                              for example   0.8    0.13    0.52  0.9  0.5   0.68 0.2  .......

```
## Post #17
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-06T08:20:02+00:00
- Post Title: Re: Tales of Zestiria

back to 
offset 0xb28  : {3A 01 00 00}= 314
so 0x594c+314x FVFsize(32) =0x808c

FVF size ==36

```
position :   x  y  z
normal? :   float float float
bone index1:   for example (0x00)/bone index2:   for example (0x07) /bone index2:   for example (0x08)/ 00
weight1:     float                for example       0.2                
weight2:     float                for example       0.4

```


that it is say 
we can  think 0.4 /0.2/0.4 is weight to  bone(bone_index)  0x00/0x07/0x08
                or   0.2/0.4/0.4
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-06T09:30:47+00:00
- Post Title: Re: Tales of Zestiria

sry to interrupt you (see you're using this thread as kinda memo pad  )

I modified chiri's C# code to directly import your uploaded .dat file:



0b8f_14.jpg (231.82 KiB) Viewed 387 times


There were 23 objects contained, most of them didn't provide proper vertices for some unknown reasons (FIs ok, so far).

had to expand this line -which I did not fully understand- for those objects with proper vertices, by 12 and -1:
if ((invalidPos == 6) || (invalidPos == 12) || (invalidPos == -1))

Sadly I didn't get correct uvs, so I've suspended further programatical investigations.
## Post #19
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-06T10:25:46+00:00
- Post Title: Re: Tales of Zestiria

this is the file in DLC 008 "TOMDLB_D"and"TOMDLP_P":
[https://mega.nz/#!xowBHIYB!RaLQ2XBeDC0_ ... HXEvQUxMN8](https://mega.nz/#!xowBHIYB!RaLQ2XBeDC0_mCM3hiWqhbgTtvc0C86AnHXEvQUxMN8)

maybe, here be 1-2 cloth model 
(i find one texture of cloth only,and i can't find out what is the file name mean or which model in file)
## Post #20
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-07T10:46:10+00:00
- Post Title: Re: Tales of Zestiria

in "00000c6f"
write a python code in noesis ,but the scale of the bone is too large.
pull it(export to .dae format) into Blender
[tale bone  00000c6f.PNG](https://xentaxbackup.github.io/file/11669_tale bone  00000c6f.PNG)
## Post #21
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-08T17:48:45+00:00
- Post Title: Re: Tales of Zestiria

bone_name
bone_parent
bone_matrix

vert_number 
vert_data offset
face_vertindex_offset
face_vertindex_reading_lenth

vert_relate_bone_Index   and  vert_weight 
==============================
these have been find out
but, the weight (<bone_index number) can't  diretly read float into noesis data,need a "1- float"  --calculate

```
                                                     rapi.rpgBindBoneWeightBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, vertSize[i], Weightpos, 4)
```

So,
copy python code from "fmt_mdl.py" (TalesGFScripts)

```
for n in range(list1[0]):
      ....
      skinIndiceList.append([v4[0]])
      skinWeightList.append([1.0])
for n in range(list1[1]):
      ......
      v5=g.readFloat()
      skinIndiceList.append(v4[:2])
      skinWeightList.append([v5,1.0-v5])
#"and so on"
     ...
     skinWeightList.append([v5,v6,1.0-v5-v6])
     ....
     skinWeightList.append([v5,v6,v7,1.0-v5-v6-v7])

```

= =sadly, "fmt_mdl.py" don't have complete code to add weight ,only ###code
like "##mesh.skinWeightList.append([1.0])"
## Post #22
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-08T18:02:09+00:00
- Post Title: Re: Tales of Zestiria

maybe, changing the code in "__NPExample.txt"  is a way.
           ——build a extra weightbuff to be "rapi.rpgBindBoneWeightBuffer()"ed

```
			vwList = []
			for j in range(0, numWeights):
				vwNum = bs.readInt()
				bidx = []
				bwgt = []
				for k in range(0, vwNum):
					bidx.append(bs.readInt())
				for k in range(0, vwNum):
					bwgt.append(bs.readFloat())
				vwList.append(NoeVertWeight(bidx, bwgt))
			fw = NoeFlatWeights(vwList)
			rapi.rpgBindBoneIndexBuffer(fw.flatW[:fw.weightValOfs], noesis.RPGEODATA_INT, 4*fw.weightsPerVert, fw.weightsPerVert)
			rapi.rpgBindBoneWeightBuffer(fw.flatW[fw.weightValOfs:], noesis.RPGEODATA_FLOAT, 4*fw.weightsPerVert, fw.weightsPerVert)
```

if vert is affect by only one bone:
if vert is affect by two bones:
if vert is affect by three bones:
if vert is affect four bones:

```
         bidx.append(....)
         bwgt.append(weight_after_calculate)
```
## Post #23
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-09T14:31:41+00:00
- Post Title: Re: Tales of Zestiria

connect to [http://imgur.com/](http://imgur.com/) just waste time
[alisha knight.png](https://xentaxbackup.github.io/file/11680_alisha knight.png)
## Post #24
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-09T14:41:49+00:00
- Post Title: Re: Tales of Zestiria

can not find main bone of character,there are only  some bones relate to （physical simulation）collision and joint ，and its' setting parameter.
and miss the character‘s face model（hair and weapon in another .dpd）.
vertex data -bone_index and weight  must be connected to main bone.
maybe have to download the game (size 11G)...
[alisha knight2.png](https://xentaxbackup.github.io/file/11681_alisha knight2.png)
## Post #25
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-09T14:44:55+00:00
- Post Title: Re: Tales of Zestiria

mesh detail
[alisha knight5.JPG](https://xentaxbackup.github.io/file/11682_alisha knight5.JPG)
## Post #26
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2016-09-14T17:26:46+00:00
- Post Title: Re: Tales of Zestiria

alisha_bone_all in file "00000064.dpd"      (...PK1\WIN\TOMDLB_D\)
alisha asassin chest   in file "00000a63.dpd" and "00000a64.dc5"(UV and face index data)

waste some time to find correct Bone__Pallet  (Bone_map ,that is ,index which bone used in mesh  -> bone_index in all Bone)
[alisha assassin .JPG](https://xentaxbackup.github.io/file/11706_alisha assassin .JPG)
## Post #27
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2017-03-21T13:13:39+00:00
- Post Title: Re: Tales of Zestiria

running that code and i got invalid vertex index in max with no texture out
## Post #28
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-04-21T04:56:36+00:00
- Post Title: Re: Tales of Zestiria

> Reply from dian333
>
> alisha_bone_all in file "00000064.dpd"      (...PK1\WIN\TOMDLB_D\)
alisha asassin chest   in file "00000a63.dpd" and "00000a64.dc5"(UV and face index data)

waste some time to find correct Bone__Pallet  (Bone_map ,that is ,index which bone used in mesh  -> bone_index in all Bone)
How did you do that?
## Post #29
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2017-05-29T16:43:49+00:00
- Post Title: Re: Tales of Zestiria

> Reply from Escope12
>
> dian333 wrote:alisha_bone_all in file "00000064.dpd"      (...PK1\WIN\TOMDLB_D\)
alisha asassin chest   in file "00000a63.dpd" and "00000a64.dc5"(UV and face index data)

waste some time to find correct Bone__Pallet  (Bone_map ,that is ,index which bone used in mesh  -> bone_index in all Bone)
How did you do that?
noesis code unfinish
last edited at 2016years 9th month
[DLC alisha knight sample.zip](https://xentaxbackup.github.io/file/12951_DLC alisha knight sample.zip)
