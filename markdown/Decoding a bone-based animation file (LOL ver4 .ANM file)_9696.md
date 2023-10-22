## Post #1
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-09-30T18:09:00+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

Hi
I'm trying to decode and extract animation data from LOL .ANM file, another people did that for version 1,2,3 but nobody done it yet for version 4.
Its because the version 4 structure is different with older version, even you can't found any information about bones, such as boneID or boneName, or if there are, i did not found them yet 
Sample .anm file (v4) :
[http://www.axifile.com/en/891EE4CBA2](http://www.axifile.com/en/891EE4CBA2)
Note that i did success to extract some information from the file such as BoneCount, FrameRate, Keyframe count from header but i can not found any bone animation data such that must be in body of file.
The bone data that i need is rotation and position of each bones per frames.
For reading header use following pseudo code:

```
data.magic2 = readLong file
data.version = readLong file
data.magic3 = readLong file
data.magic4 = readLong file
data.magic5 = readLong file
data.magic6 = readLong file
data.numberOfBones =  readLong file
data.numberOfFrames =  readLong file
data.playbackFPS = readFloat file
for i = 1 to 3 do
	print (readLong file)
part1StartIndex=readLong file
part2StartIndex=readLong file
part3StartIndex=readLong file

```

and so
Thank you for any help.
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-02T08:38:44+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

[out]
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-10-02T10:35:38+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

@Wobble: hi, can you give an example on "indexing"? (Maybe a link?)

I also could not find the "borders" (start/stop) of the "41 frames".
maybe these are rotation (position?) keyframes:

```
 0.000000 0.000000 0.087152 0.996195
 0.000001 0.000000 0.087155 0.996195
 0.000026 0.000000 0.087154 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087157 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087155 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087152 0.996195
 0.000026 0.000000 0.087156 0.996195
 0.000026 0.000000 0.087154 0.996195

 0.000027 0.000001 0.087142 0.996196
 0.000053 0.225776 0.012935 0.974093
0x694c
 0.000063 -0.025668 0.282352 0.958967
 0.000222 0.393292 0.446769 0.803566
 0.000393 -0.143462 -0.312618 0.938983
 0.000694 0.037390 0.460540 0.886851
 0.000785 0.018486 -0.152407 0.988145
 0.000803 0.079384 0.013172 0.996757
 0.000809 -0.068431 0.015846 0.997530
 0.000891 -0.027771 -0.048990 0.998413
 0.001060 -0.087805 0.768313 0.634023
 0.001088 0.451058 0.000322 0.892494
 0.001516 -0.035967 -0.258022 0.965468
 0.001667 -0.026372 0.270792 0.962275
 0.001715 0.264881 0.000849 0.964279
 0.002559 -0.003620 0.498762 0.866728
 0.002594 0.002354 0.488400 0.872613
 0.002940 0.018267 -0.035857 0.999186
 0.003196 0.068814 0.035723 0.996985
 0.003240 0.065351 0.493375 0.867352
 0.003344 -0.027079 0.255724 0.966365
 0.003617 -0.078308 -0.035283 0.996298
 0.003685 0.110105 0.055155 0.992382
 0.003722 0.452373 0.001095 0.891820
 0.003812 -0.168678 -0.130793 0.976947
 0.004032 -0.043198 0.814303 0.578816
 0.004524 0.003573 -0.005252 0.999970
 0.004923 -0.027806 0.240600 0.970214
 0.005294 0.332245 0.002343 0.943175
 0.005888 -0.024568 -0.229223 0.973046
 0.006193 0.108503 0.055085 0.992549
 0.006269 -0.028536 0.228920 0.973007
 0.006319 -0.162604 -0.087576 0.982777
 0.006513 0.383412 0.159413 0.909692
 0.006931 -0.014940 0.005532 0.999849
 0.006950 0.454715 0.002026 0.890608
 0.007222 -0.006045 -0.005174 0.999942
 0.007272 -0.029224 0.224221 0.974073
 0.007276 0.476328 0.001928 0.879235
 0.007362 -0.026529 0.254585 0.966658
 0.007630 -0.029001 0.270634 0.962215
 0.007863 -0.029868 0.230736 0.972526
 0.007949 -0.031469 0.286603 0.957500
 0.008020 -0.031330 0.280161 0.959408
 0.008114 -0.030465 0.246277 0.968687
 0.008126 -0.030970 0.264752 0.963785
 0.008429 -0.013439 0.450161 0.892807
 0.008590 0.406274 0.003216 0.913705
 0.009224 0.281164 0.015349 0.959493
 0.009225 -0.092680 0.768105 0.633514
 0.009280 0.380044 -0.644442 0.663457
 0.009477 0.158238 -0.031985 0.986837
 0.009579 0.008086 0.456748 0.889508
 0.009612 0.054161 0.079553 0.995312
 0.009825 0.458191 0.002824 0.888795
 0.010134 -0.111869 0.580081 0.806777
 0.010471 0.052112 0.035016 0.997972
 0.010476 0.461745 0.003436 0.886944
 0.010827 -0.060436 0.734874 0.675418
 0.010841 0.468906 0.002975 0.883176
 0.010973 0.476141 0.004189 0.879290
 0.011417 0.462893 0.003217 0.886335
 0.011464 -0.047931 0.391948 0.918667
 0.011490 -0.443154 -0.008370 0.896333
 0.011770 -0.285060 -0.301325 0.909838
 0.011965 -0.049614 0.402643 0.913933
 0.012446 -0.026397 -0.110459 0.993452
 0.013110 -0.307965 0.820415 -0.481566
 0.013380 -0.051526 0.643915 0.763243
 0.013541 -0.054132 0.778172 0.625567
 0.013687 -0.022468 -0.234762 0.971697
 0.014124 -0.416028 -0.003416 0.909236
 0.014338 -0.235982 0.021406 0.971416
 0.014672 -0.027864 0.381494 0.923835
 0.015192 0.437317 -0.003643 0.899172
 0.015639 -0.012932 -0.278529 0.960213
 0.016720 0.012942 -0.019247 0.999591
 0.017151 -0.246531 0.071622 0.966332
 0.017731 0.080452 0.022574 0.996345
 0.018530 0.428346 0.417420 0.801210
```
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-02T13:24:48+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

[out]
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-10-02T17:21:49+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from Wobble
>
> [...]and subtract the offsets to find their estimated size.This is obvious, isn't it?  
What I meant is where the frames to start and stop; what is frame 0 and what is frame 40?

Such as

```
 0? 0.000000 0.000000 0.087152 0.996195
 1? 0.000001 0.000000 0.087155 0.996195
 2? 0.000026 0.000000 0.087154 0.996195
 3? 0.000026 0.000000 0.087156 0.996195
...
20? 0.000026 0.000000 0.087156 0.996195
...
30? 0.000026 0.000000 0.087157 0.996195
..
40? 0.000026 0.000000 0.087156 0.996195

 ? 0.000026 0.000000 0.087154 0.996195

 ? 0.000027 0.000001 0.087142 0.996196
 ? 0.000053 0.225776 0.012935 0.974093
0x694c
```


And what about the important part, the indexing?

edit: ok, got it! Thank you, Wobble!  

edit: ok, from 0xa46c there are 30 tables of this kind (bone 0 to 74?)
the first 4 byte row being identical in every table 

```
   0  64 96 07 00  93 02 39 03  B6 01 00 00 
   1  81 04 A7 07  32 03 39 03  11 04 00 00 
   2  82 04 A7 07  B0 02 36 03  DF 05 00 00 
   3  83 04 A7 07  C7 02 3B 03  A2 04 00 00 
   4  9B 4B 07 00  E2 02 3A 03  E2 03 00 00 
   5  74 EB 06 00  0B 03 37 03  7E 00 00 00 
   6  51 80 6E 00  75 03 3B 03  82 05 00 00 
   7  52 80 6E 00  48 01 39 03  7D 00 00 00 
   8  53 80 6E 00  5B 01 39 03  05 02 00 00 
   9  54 80 6E 00  2D 01 3A 03  B5 01 00 00 
  10  55 80 6E 00  0A 01 38 03  88 03 00 00 
  11  56 80 6E 00  CC 00 38 03  AD 01 00 00 
  12  85 DD 8B 02  48 02 3B 03  43 00 00 00 
  13  52 0C 6D 0F  8C 01 37 03  C5 05 00 00 
  14  17 29 5C 02  5B 00 3B 03  F6 02 00 00 
  15  44 E8 25 07  8E 00 37 03  1D 00 00 00 
  16  71 C4 AF 06  FA 01 39 03  66 06 00 00 
  17  72 C4 AF 06  5A 02 3B 03  93 02 00 00 
  18  91 AB 04 06  AE 01 39 03  20 05 00 00 
  19  92 AB 04 06  2F 02 35 03  AC 02 00 00 
  20  E1 E0 FA 03  99 01 37 03  CB 04 00 00 
  21  E2 E0 FA 03  DC 01 35 03  AC 02 00 00 
  22  D1 04 69 02  A1 01 39 03  47 02 00 00 
  23  D2 04 69 02  14 02 35 03  AC 02 00 00 
  24  E1 55 70 06  AB 01 37 03  EB 00 00 00 
  25  E2 55 70 06  82 02 3B 03  BC 02 00 00 
  26  85 7D 8B 02  67 03 36 03  74 06 00 00 
  27  52 AC 6D 0F  81 03 39 03  EB 05 00 00 
  28  17 29 5C 08  CE 03 3B 03  25 03 00 00 
  29  44 E8 85 07  BD 03 3B 03  B3 03 00 00 
  30  D1 C4 AF 06  6B 03 3B 03  75 06 00 00 
  31  D2 C4 AF 06  62 03 35 03  87 04 00 00 
  32  31 AB 04 06  7A 03 3B 03  7A 05 00 00 
  33  32 AB 04 06  68 03 3B 03  35 02 00 00 
  34  E1 EA FA 03  80 03 3B 03  AA 03 00 00 
  35  E2 EA FA 03  6D 03 3B 03  EB 02 00 00 
  36  D1 04 69 08  7E 03 39 03  14 01 00 00 
  37  D2 04 69 08  6A 03 3B 03  D3 02 00 00 
  38  41 55 70 06  7B 03 3A 03  C8 00 00 00 
  39  42 55 70 06  5F 03 3B 03  D4 02 00 00 
  40  00 5F 72 00  9B 01 38 03  D0 01 00 00 
  41  B5 24 26 07  43 00 3B 03  7F 00 00 00 
  42  64 D6 25 07  06 00 3B 03  46 02 00 00 
  43  55 6B 72 00  F9 01 39 03  C2 01 00 00 
  44  24 2A 5B 0B  EA 02 3B 03  93 02 00 00 
  45  00 5F 78 00  7F 03 3B 03  F3 05 00 00 
  46  B5 24 86 07  EB 03 3B 03  2D 00 00 00 
  47  64 D6 85 07  03 04 3B 03  6B 01 00 00 
  48  55 6B 78 00  6C 03 3B 03  62 03 00 00 
  49  93 6D A3 05  C2 01 3B 03  13 00 00 00 
  50  94 6D A3 05  B5 00 39 03  4E 01 00 00 
  51  33 6D A3 05  77 03 38 03  72 06 00 00 
  52  34 6D A3 05  97 03 3B 03  1C 02 00 00 
  53  5E 87 DB 07  55 00 3B 03  71 06 00 00 
  54  91 6D A3 05  6A 01 3B 03  53 01 00 00 
  55  92 6D A3 05  F0 00 3B 03  E8 06 00 00 
  56  31 6D A3 05  88 03 3A 03  17 06 00 00 
  57  32 6D A3 05  90 03 3B 03  93 02 00 00 
  58  83 F2 C0 0A  1D 02 3B 03  FF 02 00 00 
  59  53 36 4B 00  EF 02 3B 03  FD 02 00 00 
  60  D1 29 AE 02  EB 02 3B 03  7D 02 00 00 
  61  23 EA AF 04  EB 02 3B 03  00 03 00 00 
  62  93 3B FA 02  EB 02 3B 03  00 03 00 00 
  63  C3 2B 3D 02  F0 02 3B 03  FF 02 00 00 
  64  A3 3B 1B 0D  57 00 3B 03  E8 05 00 00 
  65  A3 3B 11 0D  56 00 3B 03  E9 05 00 00 
  66  93 3B 3B 0F  BA 00 3B 03  EA 05 00 00 
  67  93 3B 31 0F  96 03 3B 03  E8 05 00 00 
  68  63 1B E6 0C  6F 03 3B 03  E8 05 00 00 
  69  C3 1B E6 0C  D1 01 3B 03  E8 05 00 00 
  70  D3 64 B1 06  EB 02 3B 03  F5 02 00 00 
  71  13 A1 02 01  1C 02 3B 03  F5 02 00 00 
  72  5C A1 87 06  8D 01 3B 03  A8 05 00 00 
  73  62 A1 87 06  F8 02 3B 03  7C 02 00 00 
  74  87 70 00 00  26 03 3B 03  00 03 00 00
```
## Post #6
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-02T18:53:18+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

Ok, all is fine else of 2 problems:
1.What data type index section is using!?
Here is first part of the index section:
64 96 07 00 93 02 39 03 B6 01 00 00 81 04 A7 07
32 03 39 03 11 04 00 00 82 04 A7 07 B0 02 36 03
DF 05 00 00 83 04 A7 07 C7 02 3B 03 A2 04 00 00
9B 4B 07 00 E2 02 3A 03 E2 03 00 00 74 EB 06 00
0B 03 37 03 7E 00 00 00 51 80 6E 00 75 03 3B 03
82 05 00 00 52 80 6E 00 48 01 39 03 7D 00 00 00
53 80 6E 00 ...

As you can see "64 96 07 00" can not be "float" or "double" or even "int32" ! but how that can contain indexing!?


2.in the position section(i mean start_offset4 to start_offset5, that is 12720 bytes), data only contain 1060 positions but we need 41*75=3075 positions! 
In quaternion section also count of data is not equal to 3075!
When we have 41 frame and 75 bones, then we need 3075 positions and 3075 orientations.
Here is my script for quick test :

```
(
	local firstPos=ftell file
	fseek file 0 #seek_end
	local maxlen=ftell file
	fseek file firstPos #seek_set
	maxlen
)
fn logEvent str=
(
	format (str+"\n")
)
clearlistener()
fFileName="Diana_attack1.anm"
logEvent ("Reading frames file from "+fFileName)
file = fopen fFileName "rb"
struct TLOLANMData (
	magic1=0,
	magic2=0,
	version=0,
	sizeOfReadableBytesUntilEndOfFile=0,
	magic3=0,
	magic4=0,
	magic5=0,
	numberOfBones=0,
	numberOfFrames=0,
	playbackFPS=0.0,	
	start_offset1=0,
	start_offset2=0,
	start_offset3=0,
	start_offset4=0,
	start_offset5=0,
	start_offset6=0,
	start_offset7=0,
	start_offset8=0,
	start_offset9=0,
	data_size4=0,
	data_size5=0,
	data_size6=0,
	bones=#()
)
struct TLOLANMFrame(
	orientation=[0,0,0,0],
	position=[0,0,0]
)
data=TLOLANMData()
data.magic1 = readLong file -- always is r3d2
data.magic2 = readLong file -- always is anmd
data.version = readLong file 
data.sizeOfReadableBytesUntilEndOfFile = readLong file
data.magic3 = readLong file -- always is 3188167891
data.magic4 = readLong file -- always is zero
data.magic5 = readLong file -- always is zero
data.numberOfBones =  readLong file -- e.g. 75
data.numberOfFrames =  readLong file -- e.g. 41
data.playbackFPS = readFloat file -- e.g. 0.03333334
data.start_offset1=readLong file -- FFFFFFFF
data.start_offset2=readLong file -- FFFFFFFF
data.start_offset3=readLong file -- FFFFFFFF
data.start_offset4=readLong file -- 64  (+12)
data.start_offset5=readLong file -- 12784  (+12)
data.start_offset6=readLong file --42080  (+12)
data.start_offset7=readLong file -- FFFFFFFF
data.start_offset8=readLong file -- FFFFFFFF
data.start_offset9=readLong file -- FFFFFFFF
file_size=getFileStreamSizeInByte file
data.data_size4=data.start_offset5-data.start_offset4-- 12720 bytes
data.data_size5=data.start_offset6-data.start_offset5-- 29296 bytes
data.data_size6=file_size-data.start_offset6-- 36900 bytes
print "----------------Part4----------------"
print (ftell file)
for i=1 to data.data_size4/12 do
(
	local x=(readFloat file)
	local y=(readFloat file)
	local z=(readFloat file)
	p=[x,y,z]
	print p	
)
print "----------------Part5----------------"
print (ftell file)
for i=1 to data.data_size5/16 do
(
	local x=(readFloat file)
	local y=(readFloat file)
	local z=(readFloat file)
	local w=(readFloat file)
	p=[x,y,z,w]
	print p	
)
print (ftell file)
print "----------------Part6----------------"
print (ftell file)
for i=1 to data.data_size6/16 do
(
	local x=(readFloat file)
	local y=(readFloat file)
	local z=(readFloat file)
	local w=(readFloat file)
	p=[x,y,z,w]
	print p	
)
print (ftell file)

```


And in end i must say sorry that i used abbreviation form of "League of Legends" as "LOL", however i didn't forget to mention name of game in subject of this thread
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-10-02T19:40:28+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from Ahmadi
>
> Ok, all is fine else of 2 problems:
1.What data type index section is using!?Good question!  
I made a new byte grouping in the edit of my previous post.

Last 4 bytes of a row should be the DWORD index we were searching for.
Max index I found in all of the tables is 0x726 (1830 dec.).

From 0x31FC to 0xA46C we do have 1831 position? lines. 
Each bone in a table gets its position via its index.
Bingo... 

edit: slight correction: there are 41 tables means each bone having 41 keyframes.
## Post #8
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-03T01:25:24+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

[out]
## Post #9
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-03T02:47:01+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from shakotay2
>
> 
Last 4 bytes of a row should be the DWORD index we were searching for.
Max index I found in all of the tables is 0x726 (1830 dec.).

From 0x31FC to 0xA46C we do have 1831 position? lines. 
Each bone in a table gets its position via its index.
Bingo... 

edit: slight correction: there are 41 tables means each bone having 41 keyframes.
What is the first 8 bytes of each row in tables!? you said that the last 4 bytes is a DWord that is index of position. but what about the first 8 bytes!? for each frame we also need bone_id(or name) and orientation not only position.
for example consider following row of the first table:
64 96 07 00  93 02 39 03  B6 01 00 00 
we know that position index is 438. but for what bone!? and with what orientation!? i think we also need index of orientation section for rotations.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-10-03T09:41:41+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from Ahmadi
>
> you said that the last 4 bytes is a DWord that is index of position.Yes; but as you might have noticed I'm somewhat unsure what is position and what is rotation. So it should be rotation and we need positions (in the fst section as stated by Wobble).

There seem to be 795 position lines but I did not find a table containing the appropriate indices (0..0x31A).

> but what about the first 8 bytes!?All I know is
the first 4 bytes are identical in the first, 2nd, ... position of the 41 tables.
So they are rather useless so far.

fst table
0  64 96 07 00  93 02 39 03  B6 01 00 00 
1  81 04 A7 07  32 03 39 03  11 04 00 00 
2  82 04 A7 07  B0 02 36 03  DF 05 00 00 

38th table
0  64 96 07 00  79 03 3B 03  A2 00 00 00 
1  81 04 A7 07  C0 02 39 03  17 05 00 00 
2  82 04 A7 07  B0 02 3A 03  31 04 00 00 

> for each frame we also need bone_id(or name) and orientation not only position.BoneId should be table positions 0, 1, 2...

(If you need names the easiest way to get them would be a search for "toe", "leg", "spline"
or something similar in all game files, I think.)
## Post #11
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-03T10:54:10+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from shakotay2
>
> 
fst table
0  64 96 07 00  93 02 39 03  B6 01 00 00 
1  81 04 A7 07  32 03 39 03  11 04 00 00 
2  82 04 A7 07  B0 02 36 03  DF 05 00 00 

38th table
0  64 96 07 00  79 03 3B 03  A2 00 00 00 
1  81 04 A7 07  C0 02 39 03  17 05 00 00 
2  82 04 A7 07  B0 02 3A 03  31 04 00 00
Nice representation! Excellent!
I'm sure following structure is suitable for the index section:

	local bone_hash_id=(readlong file)
	local position_index=(readShort file)
	local unknow_1=(readShort file)
	local rotation_index=(readShort file)
	local unknow_2=(readShort file)


Because after running a script and some play-tests, position_index is always between 0 to 1059 and rotation_index is always between 0 to 1830 and its correct with size of "position data section" and "quaternion data section" .
in "position data section" we have 1060 records(each is a Float3).
in "quaternion data section" we have 1830 records(each is a Float4).

Now all-things is clear else of  unknow_1, unknow_2.
I'm not sure about bone_hash_id but in another file of game, i have list of bones, then bone-id or bone-index is enough for loading this .anm file, and i don't need bone names for now.

Here is my first result:
[http://axifile.com/en/246CAA9B0A](http://axifile.com/en/246CAA9B0A)
## Post #12
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-04T09:47:48+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

[out]
## Post #13
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-06T16:11:25+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from Wobble
>
> 
Yep, literal string bone names have been replaced with 32-bit hashes for faster lookup apparently.
The first bone, "Root" matches the hash 0x00079664.

You can find this in the game's r3dlog.txt file, if you Google it:

>>> TalentHashMap::HashToName - Match not found for hash 00079664


But, I couldn't find what kind of 32-bit hash generator they're using.
Ran the string "Root" against several 32-bit hash algorithms, nothing matched 0x00079664.
Also checked all uppercase and lowercase characters, "ROOT" and "root", as they usually do that before hashing a string.

About converting boneHashID to boneName, all boneHashID exists in .skl file near of the animation file(the .skl file contain Bone.Name+Bone.ID+Bone.Position+Rotation,Bone.ParentID,HashID and ...). Now problem of converting BoneHashID to BoneName is solved.
To now,All things are good and the .ANM file work fine and show attack1 animation without any problem.
First time i thinked the story ended but when i open and play another animation file(For example IDLE1), the result isn't fine and some of bones(about 50% of them) don't have any animation. After many check i understand that idle1.anm have some hashID that does not exists in .skl file or in attack1.anm file!
Here is the idle1 animation file:
[http://www.uploadmb.com/dw.php?id=1349539684](http://www.uploadmb.com/dw.php?id=1349539684)

Notes:
1.A wonderful thing about the idle1 animation is : The count of bones in each frames are more than the count of bones that the character have! the character have 75 bones, but in each frames in have 76,77,78,79,80,81,82,83,84,85. This problem is not with attack1 or some other animation files.

2.In idle1.anm header, boneCount is 86 and frameCount is 61, but in attack1 header, boneCount is 75 and frameCount is 41,as i know when a character want use 2 or more animations files , the files must have equal bones in their files! why one say 86 and another say 75! Please note that the character have 75 bones, in both skeleton and mesh file . then some of animations files that say bone count is 75 , say truth and some of them that say 86 or somethings else are false. Its fun that you know my code work fine with the truth files and don't work with false files. 

3.Its unbelievable but hashID of bones are not unique in each table! for example if you see first table of attack1.anm(i mean frame0), you can see that "24 2A 5B 0B" is twice! one in +528 and another in +540 offset. But as i know in theory one bone can have one position and orientation in one frame. 

Edited:
Here is frame0 table of 2 animation files, maybe help you 
[http://www.uploadmb.com/dw.php?id=1349542098](http://www.uploadmb.com/dw.php?id=1349542098)
[http://www.uploadmb.com/dw.php?id=1349542107](http://www.uploadmb.com/dw.php?id=1349542107)

Thank you for any idea
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-06T19:56:29+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

[out]
## Post #15
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-06T20:31:03+00:00
- Post Title: Decoding a bone-based animation file (LOL ver4 .ANM file)

> Reply from Wobble
>
> Maybe post the entire character then.  Need .skl and .skn files for Diana character.
I cannot find this character in the game archive.
[http://www.uploadmb.com/dw.php?id=1349554891](http://www.uploadmb.com/dw.php?id=1349554891)

use following script for loading skl :

```
data.magicOne = readLong file
data.magicTwo = readLong file
data.version = readLong file
-- Header
local tempZero = readShort file -- ?
data.numBones = readShort file
data.numBoneIDs = readLong file
local offsetToVertexData = readShort file
local unknown = readShort file -- ?
local offset1 = readLong file
local offsetToAnimationIndices = readLong file
print ("offsetToAnimationIndices="+(offsetToAnimationIndices as string))
local offset2 = readLong file
local offset3 = readLong file
local offsetToStrings = readLong file
incFilePositionIndex file 20
setFilePositionIndex file offsetToVertexData
for i = 0  to  data.numBones-1 do
(
	local b = TLOLBone()
	-- The old scale was always 0.1.
	-- For now, just go with it.
	b.scale = 0.1f
	b.version=data.version

	local zeroTemp = readShort file -- ?
	b.ID = readShort file
	b.parentID = readShort file
	local unknown = readShort file -- ?

	b.namehash = readLong file
	local twoPointOne = readFloat file

	b.position[1] = readFloat file
	b.position[2] = readFloat file
	b.position[3] = readFloat file

	local one = readFloat file
	one = readFloat file
	one = readFloat file

	b.orientation[1] = readFloat file
	b.orientation[2] = readFloat file
	b.orientation[3] = readFloat file
	b.orientation[4] = readFloat file

	local ctx = readFloat file -- ctx
	local cty = readFloat file -- cty
	local ctz = readFloat file -- ctz

	append data.bones b
	append data.boneIDs (i)
	incFilePositionIndex file 32
)
setFilePositionIndex file offset1
for  i = 0 to data.numBones-1 do -- ?
(
	-- 8 bytes
	local valueOne = readLong file
	local valueTwo = readLong file
)
setFilePositionIndex file offsetToAnimationIndices
data.boneIDs=#()
for i = 0 to data.numBoneIDs-1 do -- Inds for animation
(
	-- 2 bytes
	local boneID = readShort file
	--print boneID
	append data.boneIDs boneID
	--append data.boneIDs (1)
)
setFilePositionIndex file offsetToStrings
for i = 0 to data.numBones-1 do
(
	-- bone names
	local curFilePos=(ftell file)
	local name = ReadNullTerminatedString file
	local afterFilePos=(ftell file)
	local def=afterFilePos-curFilePos
	while (mod def 4)>0 do
	(
		local temp=readbyte file
		def+=1
	)
	name = RemoveBoneNamePadding(name)
	name = ToLower name
	data.bones[i+1].name = name
)

```
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-07T03:18:33+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

[out]
## Post #17
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-07T06:18:33+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

> Reply from Wobble
>
> Thanks.

Are these diana .skl files being used in the public game?  Not beta/development?
All game .skl files start with "r3d2sklt".  These are different than what I expected.
There is no such header here.  I hope they are not corrupt.
League of legends is a live game(Always under development), that mean each time that Riot company developers detect that need new thing or features they make new format or the features without worry about old formats, because they stored version of each file in header of that files.
however if we do reverse engineering perfectly , then we also don't have problem with loading of correct version of LOL models. 
Its normal that one file of game with same extension is different with other with same extension. because the game is live.
I'm sure that the files is used in the public game, because i copied them from a playable instance.
## Post #18
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-07T07:35:15+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

[out]
## Post #19
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-07T07:43:05+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

> Reply from Wobble
>
> That's what I get here too.  Skeleton has 75 bones.  Two animations have 86.  Too many.  
Just ignore them?
But the problem is that the 2 animations(with 86 bones) don't contain 75 main bone animations! 
Then when i load idle1 on my skeleton with ignoring algorithm for unknown bones, result is incorrect, because some of main 75 bones don't have any keyframes! if you compare idle1 with other animations, you can see that more than 10 bones of 75 bones does not exists in idle1 file! 
in other word, 86 bones don't contain all of 75 bones.
## Post #20
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-07T08:13:56+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

[out]
## Post #21
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-07T08:33:50+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

> Reply from Wobble
>
>  I don't think they have to exist.
.anm files may only contain "animated" bones.  If a bone isn't animated, then it would be a waste of space writing 
out zero position, and zero rotation for every frame.  This is why they use bone_ids to match up skeleton bones to animated bones,
as it is not a 1-to-1 mapping.
Ok, but "weapon" bone does not exists in both diana_idle1.anm and diana_crit.anm and then it don't have keyframes(As you said this may mean that the bone don't need animating).
Please consider what happen, when i load the animations, weapon is dangling in air same as design time! without any key-frames! it can't be correct(diana_crit is some type of attack! weapon also need animating). I'm sure that one of 86 bones of the files is for "weapon" bone with different hashID from what the bone have in 75 bones file. Please note that ignoring all of invalid HashIDs cause incorrect animation result.
If you are with my opinion that the "weapon" bone need animating and the diana_idle1.anm and diana_crit.anm must contain it, then we are both in same boat, we need to found it, at any cost   

Sorry for the joke and thank you for any help.
## Post #22
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-07T09:52:45+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

[out]
## Post #23
- Username: Ahmadi
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 26, 2010 9:36 pm
- Post datetime: 2012-10-07T19:50:17+00:00
- Post Title: Re: Decoding a bone-based animation file (LOL ver4 .ANM file

> Reply from Wobble
>
> Ok, so there are 10 animated bones with missing names.
Do you know the bone names for these missing ids?
Unfortunately no.I didn't success to found any files that contain information about them.

> Reply from Wobble
>
> 
All 75 bones exist for me, including "Weapon".  See above for snippet from frame 0, idle1 animation.
The problem solved. it caused by a bug in my duplicator remover for hashIDs.I did mistake.
Thank you very much
