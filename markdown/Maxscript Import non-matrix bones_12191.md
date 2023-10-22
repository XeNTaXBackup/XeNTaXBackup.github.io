## Post #1
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-03T19:29:24+00:00
- Post Title: Maxscript Import non-matrix bones

I have trouble importing bones with XYZ(W) values.
I'm not really certain about the order of the coordinates.

```
fseek 0xC #seek_cur
for x = 1 to BoneCount do (
   fseek 0x8 #seek_cur
	BoneID = readlong f
	BoneParent = readlong f
	PosX = readfloat f
	PosY = readfloat f
	PosZ = readfloat f
	PosW = readfloat f
	RotX = readfloat f
	RotY = readfloat f
	RotZ = readfloat f
   RotW = readfloat f
	ScaleX = readfloat f
	ScaleY = readfloat f
	ScaleZ = readfloat f
	ScaleW = readfloat f
	fseek 0x10 #seek_cur
)

```

sample
[http://puu.sh/cBWxG.dat](http://puu.sh/cBWxG.dat)
## Post #2
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-11-04T00:30:52+00:00
- Post Title: Maxscript Import non-matrix bones

That's because it's a Transformation matrix and not Quats i belive, it would be so weird, in fact, you can't position with quaternions in 3DS MAX, it just doesn't make any sense.

Thsi is how i put 4x4 Transformation matrices on 3ds max:

```
BoneCount = readlong f
fseek 0xC #seek_cur
for x = 1 to BoneCount do 
(
   fseek 0x8 #seek_cur

   BoneID = readlong f
   BoneParent = readlong f

   	trans1 = point3 (readfloat f) (readfloat f) (readfloat f)
	readfloat f
	trans2 = point3 (readfloat f) (readfloat f) (readfloat f)
	readfloat f
	trans3 = point3 (readfloat f) (readfloat f) (readfloat f)
	readfloat f
	trans4 = point3 (readfloat f) (readfloat f) (readfloat f)
	readfloat f
	Transformation = matrix3 trans1 trans2 trans3 trans4

   fseek 0x10 #seek_cur
)

```


Works for me, not sure on your format though.

For making the bone you should do this:

```
newBone.transform = Transformation 

```


If the result looks weird try adding this:

```

```


I hope that works
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2014-11-07T20:58:06+00:00
- Post Title: Maxscript Import non-matrix bones

Sadly it didn't.

This is the data for 1 bone. Importing it as a 4x4 matrix doesn't yield decent results, nor did your method.
The best result I got with this script:

```
if BoneCount != 0 do (
BNArr = #()
for i = 1 to BoneCount Do 
(
fseek f 0x8 #seek_cur --skipping junk
BoneID = readlong f
BoneParentID = readlong f
print BoneParentID
rx = readfloat f; ry = readfloat f; rz = readfloat f; rw = readfloat f
px = readfloat f; py = readfloat f; pz = readfloat f
sx = readfloat f; sy = readfloat f; sz = readfloat f; sw = readfloat f
fseek f 0x14 #seek_cur --skipping offsets
BoneRot = (quat rx ry rz rw) as matrix3
BonePos = [px,py,pz]
BoneScl = [sx,sy,sz,sw]
	
bne = dummy showLinks:true showLinksOnly:true
bne.scale = BoneScl
bne.name = Bone_Data_array[i].BoneName
bne.rotation = BoneRot
bne.pos = BonePos
append BNArr bne
if (BoneParentID != -1) then (
bne.parent = BNArr[BoneParentID+1]
bne.transform *= bne.parent.transform
)
)
	Print ("Bone data end @ 0x"+((bit.intAsHex(ftell f))as string))
)

```

[http://puu.sh/cHdzI.png](http://puu.sh/cHdzI.png)
