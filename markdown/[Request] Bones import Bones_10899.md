## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-10-23T16:46:42+00:00
- Post Title: [Request] Bones import/ Bones

Hello guys!
I would like to ask about bones import tutorial. There are nice tutorials about models import, and to me personally they helped a lot. But alsmost no info on bones import, it would be awesome if someone will make tutorial in MaxScript with a couple of examples how bones are stored and how they could be imported. Maybe someone will be interested explain this to me, then I'll be glad to pay money for such service. Please, write here or send me PM.
P.S. I've attached armature file, this file I would like to import. This file could be an example in tutorial.
[bones_phw_01.7z](https://xentaxbackup.github.io/file/6727_bones_phw_01.7z)
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-18T20:02:11+00:00
- Post Title: [Request] Bones import/ Bones

Do you have the format specification of that skel file?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-18T23:16:53+00:00
- Post Title: [Request] Bones import/ Bones

> Reply from zaramot
>
> This file could be an example in tutorial.Nope, I don't think so. It's unsuitable for a tutorial because it consists of 230 bones/helpers. (About 100 being phy_... helpers?)

Anyway, this is the structure:

```
FA CC  Bip01 Spine  02 00 00 00   BoneID (of parent bone?)

 -0.000001 0.998762 -0.049766 0.000000 	       |
 1.000001 -0.000001 -0.000001 0.000000 	       |    > Rotation
 -0.000001 -0.049766 -0.998763 0.000000 	      |
 -0.000001 112.806000 -2.667690 1.000000 	  Position

 0.000001 0.999999 -0.000001 0.000000 
 0.998760 0.000001 -0.049766 0.000000 
 -0.049766 -0.000001 -0.998759 0.000000 
 -112.798866 -0.000101 2.949481 1.000000 
- - - - - - - - - - - - - - - - - - - - - - - -

 0.998763 -0.000000 0.049766 0.000000 
 -0.000003 1.000002 0.000004 0.000000 
 -0.049766 -0.000004 0.998764 0.000000 
 5.568008 -0.000001 1.042542 1.000000 

 0.998759 0.000000 -0.049766 0.000000 
 0.000003 0.999998 -0.000004 0.000000 
 0.049766 0.000004 0.998757 0.000000 
 -5.612982 -0.000005 -0.764151 1.000000 

 1.000002  1.000002  1.000003  0.000002    // 10 unknown floats
 -0.024891  0.000001  0.999690  
 5.568008  -0.000001  1.042542  
# offset 0x642 
00 00 09 91   unknown DWORD

------------------------------------------
7D D1  Bip01 L Thigh  02 00 00 00 

 -0.039421 -0.998434 0.039701 0.000000 
 -0.999223 0.039393 -0.001443 0.000000 
 -0.000123 -0.039727 -0.999212 0.000000 
 10.470100 107.237999 -1.625140 1.000000 

 -0.039420 -0.999222 -0.000123 0.000000 
 -0.998433 0.039394 -0.039727 0.000000 
 0.039701 -0.001443 -0.999209 0.000000 
 107.547226 6.235026 2.637699 1.000000 
- - - - - - - - - - - - - - - - - - - - - - - -

 -0.998435 -0.039421 -0.039701 0.000000 
 0.039396 -0.999224 0.001440 0.000000 
 -0.039727 -0.000126 0.999213 0.000000 
 -0.000015 10.470109 0.000019 1.000000 

 -0.998432 0.039395 -0.039727 0.000000 
 -0.039422 -0.999221 -0.000126 0.000000 
 -0.039701 0.001440 0.999208 0.000000 
 0.412735 10.461955 0.001300 1.000000 

 1.000001  1.000001  1.000003  -0.019865
 0.000329  0.999608  -0.019712  
-0.000015  10.470109  0.000019  
# offset 0x782
00 00 37 13 

------------------------------------------
1D BC  Bip01 R Thigh  02 00 00 00 
```
Once we found out how the parenting of bones is working here the meaning of the unknown 10 floats should be solved.

If it were less bones I would convert this to a "havok skeleton" but as I said "it's a bad example", imho.
As soon as I have a better one I would like to make a tut. But I've little time and I'm no expert with this.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-19T00:11:10+00:00
- Post Title: [Request] Bones import/ Bones

I already posted a script for this.
The game is Black Desert Online.
[viewtopic.php?f=16&t=10909](http://forum.xentax.com/viewtopic.php?f=16&t=10909)

```
		for i in range(0, boneCount):
			boneHash = bs.readUInt()
			boneNameSize = bs.readUByte()
			boneName = bs.readBytes(boneNameSize).decode("ASCII").rstrip("\0")
			boneParent = bs.readInt()
			boneMtx             = NoeMat44.fromBytes(bs.readBytes(64)).toMat43()
			boneMtxInverse      = NoeMat44.fromBytes(bs.readBytes(64)).toMat43().inverse()
			boneMtxLocal        = NoeMat44.fromBytes(bs.readBytes(64)).toMat43()
			boneMtxLocalInverse = NoeMat44.fromBytes(bs.readBytes(64)).toMat43().inverse()
			boneScale           = NoeVec3.fromBytes(bs.readBytes(12))
			BoneQuat            = NoeQuat.fromBytes(bs.readBytes(16))
			BonePos             = NoeVec3.fromBytes(bs.readBytes(12))
			bs.seek(0x2, NOESEEK_REL)
			newBone = NoeBone(i, boneName, boneMtx, None, boneParent)
			boneList.append(newBone)

```
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-19T09:06:18+00:00
- Post Title: [Request] Bones import/ Bones

thx, chrrox.
(I'll never understand why thread openers hide the names of the games.  )
