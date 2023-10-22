## Post #1
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-08-05T17:56:21+00:00
- Post Title: Skeleton parsing help

I'm having trouble reading this skeleton file. It's not like the files I've seen before in recent titles but often in older ps2 titles. Help would be appreciated.
[https://www.mediafire.com/?ustmgg5kvh27vcq](https://www.mediafire.com/?ustmgg5kvh27vcq)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-05T22:18:13+00:00
- Post Title: Skeleton parsing help

Resident Evil: Outbreak?
## Post #3
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-08-05T23:15:42+00:00
- Post Title: Skeleton parsing help

This is dbz burst limit.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-06T06:11:04+00:00
- Post Title: Skeleton parsing help

> Reply from killercracker
>
> I'm having trouble reading this skeleton file. It's not like the files I've seen before in recent titles but often in older ps2 titles. Help would be appreciated.I know you're a skeleton expert and I can't offer a solution but I'd like to pick up this opportunity to build some kind of "getting a skeleton" tutorial (sooner or later  ).

First we have about 278 bones here, right?
Then there's 564 x 64 bytes blocks, with a 12 bytes FF sequence preceded by a word. 
These blocks seem to contain position and rotation (square sum of first 3 components=1).

I'd apply the positions of the first 278 blocks to the bones and check how it looks in a 3D app.

This is the log of the 564 words (highest number is 0x7A):

```
00 03  00 03  00 03  00 03  00 03  00 03  00 03  00 02  00 02  00 03  00 03  00 03  00 03  00 03  00 03  00 03  
00 03  00 05  00 05  00 05  00 05  00 48  00 48  00 48  00 48  00 02  00 02  00 02  00 02  00 02  00 02  00 02  
00 02  00 01  00 01  00 01  00 02  00 01  00 42  00 42  00 42  00 03  00 03  00 42  00 42  00 42  00 42  00 03  
00 42  00 03  00 03  00 05  00 05  00 79  00 79  00 79  00 79  00 48  00 48  00 03  00 42  00 48  00 48  00 03  
00 42  00 48  00 03  00 03  00 03  00 7A  00 7A  00 79  00 79  00 79  00 02  00 02  00 02  00 03  00 03  00 03  
00 03  00 03  00 02  00 02  00 79  00 79  00 79  00 79  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  
00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 01  00 01  00 01  00 01  
00 01  00 01  00 01  00 01  00 01  00 77  00 77  00 01  00 77  00 77  00 01  00 01  00 01  00 01  00 77  00 01  
00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 77  00 78  00 78  00 77  
00 78  00 78  00 77  00 78  00 78  00 77  00 77  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  
00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  00 78  
00 78  00 78  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 79  00 48  00 48  
00 48  00 48  00 48  00 48  00 48  00 48  00 48  00 48  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  
00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 48  00 48  00 48  00 48  
00 48  00 48  00 48  00 48  00 48  00 48  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  00 43  
00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  00 42  
00 42  00 42  00 42  00 42  00 7A  00 7A  00 79  00 79  00 7A  00 7A  00 79  00 7A  00 7A  00 79  00 7A  00 7A  
00 02  00 03  00 02  00 03  00 03  00 01  00 79  00 79  00 03  00 68  00 68  00 68  00 68  00 03  00 03  00 03  
00 03  00 03  00 03  00 69  00 69  00 69  00 69  00 03  00 03  00 03  00 03  00 03  00 03  00 03  00 03  00 02  
00 02  00 03  00 03  00 03  00 03  00 03  00 05  00 05  00 27  00 27  00 27  00 27  00 02  00 02  00 02  00 02  
00 02  00 02  00 02  00 01  00 01  00 02  00 01  00 01  00 02  00 21  00 21  00 21  00 21  00 03  00 03  00 21  
00 21  00 21  00 21  00 03  00 03  00 03  00 05  00 68  00 68  00 68  00 68  00 27  00 27  00 21  00 03  00 27  
00 27  00 21  00 03  00 27  00 03  00 69  00 69  00 68  00 68  00 68  00 02  00 03  00 03  00 03  00 68  00 68  
00 68  00 68  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 05  00 01  00 01  
00 01  00 01  00 01  00 01  00 64  00 64  00 01  00 64  00 64  00 01  00 01  00 01  00 64  00 64  00 64  00 64  
00 64  00 64  00 64  00 64  00 64  00 64  00 64  00 64  00 64  00 65  00 65  00 64  00 65  00 65  00 64  00 64  
00 65  00 65  00 64  00 64  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  
00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 65  00 68  
00 68  00 68  00 68  00 68  00 68  00 68  00 68  00 68  00 68  00 68  00 68  00 27  00 27  00 27  00 27  00 27  
00 27  00 27  00 27  00 27  00 27  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  
00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 27  00 27  00 27  00 27  00 27  00 27  00 27  
00 27  00 27  00 27  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 22  00 21  00 21  00 21  
00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  00 21  
00 21  00 69  00 69  00 68  00 69  00 69  00 68  00 69  00 68  00 69  00 69  00 68  00 69  00 02  00 03  00 02  
00 03  00 68  00 68  00 03
```
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-07T12:07:03+00:00
- Post Title: Skeleton parsing help

Hello skeleton experts 

This is what I'm getting from this file:



139 bones, hierarchy, rotations, positions, scales - all in the first segment called "amo".

First goes hierarchy, with parent bone linked as an offset to parent bone.
Next a table of references to data, which are all linear anyway.
Then goes actual data: 4 floats in line: rotations, positions, scales, and some more data probably not needed.

Then bone names, repeated 2 times.

The following segment (RPT) is probably something for his pants clothstate.
And the last segment (BND) is maybe childs list and rotation matrices which I didn't check because I don't think you need it.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-09T15:48:19+00:00
- Post Title: Skeleton parsing help

Ok, looks like you don't need this skeleton anymore. You could at least confirm that you read this.
## Post #7
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-08-09T18:11:13+00:00
- Post Title: Skeleton parsing help

My bad. I thank you for your work, I was trying to make significant progress before replying.
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-10T16:52:39+00:00
- Post Title: Skeleton parsing help

Good, I wanted to know if that information i posted was understandable. Good luck.
## Post #9
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-08-10T19:30:20+00:00
- Post Title: Skeleton parsing help

This is what I have so far. I see a structure but it stil isn't there. I can't find out what I'm doing wrong. 

```
   i = bit.floatAsInt f
   h = bit.intashex i
   while h.count < 8 do h = "0" + h
   
   s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
   bit.intAsFloat (bit.hexasint s)
)   
fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)
fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)
fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
)


-- fname = GetOpenFileName caption:"" types:"(.)|*."
fname = @"C:\Users\Xavier\Desktop\BCTSH000.AMO"
If (fname!=undefined) and ((DoesFileExist fname)==true) then (
f = fopen fname "rb"   --open file in read only format
FileExtension = getFileNameType  fname
FileName = getFileNameFile fname
clearlistener()
Global fscale=5
delete $*
Print "===================================="
print (FileName + FileExtension) as string
Print "===================================="
--)

amo = ReadFixedString f 4
fseek f 0xc #seek_cur
boneCount = readbelong f
fseek f 0x2c #seek_cur

boneTable=#()
tableOffset=#()
tableOffset2=#()
tableOffset3=#()

for x=1 to boneCount do (
	boneID = readbelong f
	boneTable[x] = readbelong f
	tableOffset[x] = readbelong f
	tableOffset2[x] = readbelong f
	tableOffset3[x] = readbelong f
	fseek f 0xc #seek_cur
	
-- 	print (bit.intashex(boneTable[x]))
)

boneOffset=#()
for x=1 to boneCount do (
	fseek f boneTable[x] #seek_set
	fseek f 0x8 #seek_cur
	boneOffset[x] = readbelong f
	null = readlong f
	
-- 	print (bit.intashex(boneOffset[x]))
)

parentOffset=#()
for x=1 to boneCount do (
	fseek f tableOffset[x] #seek_set
	if tableOffset[x] > 0 do (
		fseek f 0x4 #seek_cur
		parentTable = readbelong f
		
		fseek f parentTable #seek_set
		fseek f 0x8 #seek_cur
		parentOffset[x] = readbelong f
		null = readlong f
		
	)
)


BNArr=#()
for x=1 to boneCount do (
	
	fseek f boneOffset[x] #seek_set
	c11 = readbefloat f; c12 = readbefloat f; c13 = readbefloat f; c14 = readbefloat f 
	c21 = readbefloat f; c22 = readbefloat f; c23 = readbefloat f; c24 = readbefloat f 
	c31 = readbefloat f; c32 = readbefloat f; c33 = readbefloat f; c34 = readbefloat f
	tfm = (quat c11 c12 c13 c14) as matrix3
	tfm.row4 = ([c21,c22,c23])
	fseek f 0x20 #seek_cur
	
	if parentOffset[x] != undefined do (		
		fseek f parentOffset[x] #seek_set
		d11 = readbefloat f; d12 = readbefloat f; d13 = readbefloat f; d14 = readbefloat f 
		d21 = readbefloat f; d22 = readbefloat f; d23 = readbefloat f; d24 = readbefloat f 
		d31 = readbefloat f; d32 = readbefloat f; d33 = readbefloat f; d34 = readbefloat f
		tfm2 = (quat d11 d12 d13 d14) as matrix3
		tfm2.row4 = ([d21,d22,d23])
		fseek f 0x20 #seek_dur
-- 		print parentOffset[x]
	)
	
	
-- 	if (boneParentID[x] != -1) do (
-- 	tfm = tfm * BNArr[(boneParentID[x] + 1)].objecttransform	
-- 	)	
	if (parentOffset[x] != undefined) do (
		tfm *= tfm2
	)
		
	newBone = bonesys.createbone	\
	tfm.row4	\
	(tfm.row4 + 0.01 * (normalize tfm.row1)) \
	(normalize tfm.row3)
	newBone.width  = 0.01
	newBone.height = 0.01
	newBone.transform = tfm
	newBone.setBoneEnable false 0
	newBone.wirecolor = white
	newbone.showlinks = true
	newBone.pos.controller      = TCB_position ()
	newBone.rotation.controller = TCB_rotation ()
-- 	if (parentID[x] != 0) then(
-- 		newBone.parent = BNArr[(parentID[x] + 1)]
-- 	)
	
	append BNArr newBone
)






Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
)
gc()
fclose f


```
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-10T20:06:04+00:00
- Post Title: Skeleton parsing help

I have no idea what kind of script is this, it would be better if you just tell me what data you getting is wrong. Hierarchy? Positions/rotations?
## Post #11
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-08-13T16:38:32+00:00
- Post Title: Skeleton parsing help

> Reply from daemon1
>
> I have no idea what kind of script is this, it would be better if you just tell me what data you getting is wrong. Hierarchy? Positions/rotations?

This is maxscript. Thanks to shakotay2 I found the problem was the hierarchy and parent transformation. Had to start from scratch and got it working.



Updted scricpt for the interested.
[http://pastebin.com/2XHfy1sn](http://pastebin.com/2XHfy1sn)
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-13T16:58:36+00:00
- Post Title: Skeleton parsing help

good that you made it!
## Post #13
- Username: Bladers
- Rank: veteran
- Number of posts: 92
- Joined date: Mon Aug 11, 2014 8:20 am
- Post datetime: 2016-08-17T12:46:07+00:00
- Post Title: Skeleton parsing help

i need help fixing the skeletons/bones for the models in Quantum Break, when imported into Unreal and trying to retarget animations for the skeleton.
Lets just say the model becomes messed up and distorted and enlarged 1000x.

Here's the script from the lovely vfolin [viewtopic.php?p=118375#p118375](http://forum.xentax.com/viewtopic.php?p=118375#p118375)
