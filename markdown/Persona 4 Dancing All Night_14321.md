## Post #1
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2016-05-08T06:12:42+00:00
- Post Title: Persona 4: Dancing All Night

P4: DAN has been dumped for a while, so i thought  its models would be finally able to be extracted from the game's data! however it seems that's not the case... after extracting the cpk, i found that the models of the characters (and personas) where in these folders respectively:

The persona folder has these files

And the player folder has these:

Folders such as 001,002,etc. have these files inside:

I've heard that the models were in a .gmd format, so here's a link to some of the files!!
[http://www.mediafire.com/download/0hf7r ... player.rar](http://www.mediafire.com/download/0hf7reh6bfc74vt/player.rar)
Hopefully someone can find a way to convert these models to different formats owo;; also i hope the information i provided helps somehow!!! i tried to be the least vague as possible D:
btw sorry if the images are too big. lightshot tends to do that sadly;;;
edit: i also uploaded the files from the 001 folder! [http://www.mediafire.com/download/6fon2 ... oz/001.rar](http://www.mediafire.com/download/6fon2osphzgxwoz/001.rar)
Thanks in advance btw uwu
## Post #2
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2016-05-08T07:50:28+00:00
- Post Title: Persona 4: Dancing All Night

I've been looking at this for a while. I'm going to ramble because I didn't really write any of my findings down. I've been working on this (horrible looking) Noesis Script. GAP's are animations, GMD's and GFS's are models. This script can load every model except pc008_f1 and pc008_f2 (Those are weird and I didn't look into why yet).

There are a few more problems with my script. I can't figure out the bones parents. The characters have 2 skeletons in their files, A bind pose (for the skinning) and some kinda animation rig. The rig could be useful if I could figure out the first skeletons bone parents but I hit a brick wall on that. The other problem is that some meshes have their positions relative to a node that its parented to (not skinned to) so they are far out of position. This mostly happens to some of the characters eyes, I have no idea how to fix that.

I'll try to explain more later today so maybe some greater minds can help.
[fmt_p4d_gmd.7z](https://xentaxbackup.github.io/file/10914_fmt_p4d_gmd.7z)
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-05-08T11:05:41+00:00
- Post Title: Persona 4: Dancing All Night

For bones use recursive function in section at end file with strings like "lockInfluenceWeight" and bone names


```


....
=====================
bone
=====================
offset 746059	(4,) - string len
offset 746061	root
offset 746065	(
-0.00010046560782939196, 
1.7763568394002505e-15,110.68985748291016, 1.2013832019874826e-05,  - bone position
0.0, 0.0, 0.0, 1.0, - bone quaternion
1.0, 1.0, 1.0, 0.0, 2.350988701644575e-38, 2.350988701644575e-38) 
offset 746121	(3,)
offset 746122	(20,)
offset 746124	lockInfluenceWeights
offset 746144	(234, 148, 171, 143, 0, 0, 0, 1, 0, 63, 128, 0, 0)
offset 746157	(8,) - child count
=====================
bone
=====================
offset 746161	(8,)
offset 746163	spine_00
offset 746171	(
-3.2469128432878978e-35, 
4.6077910469111399e-15,1.8706696033477783, 0.028047563508152962, 
0.0, 0.0, 0.0, 1.0, 
1.0, 1.0, 1.0, 0.0, 2.350988701644575e-38, 2.350988701644575e-38)
offset 746227	(3,)
offset 746228	(20,)
offset 746230	lockInfluenceWeights
offset 746250	(234, 148, 171, 143, 0, 0, 0, 1, 0, 63, 128, 0, 0)
offset 746263	(1,) - child count
=====================
bone
=====================
offset 746267	(8,)
offset 746269	spine_01
offset 746277	(
-8.4957790878464147e+29, 
-3.8694484828738496e-05, 12.831052780151367, -0.25826916098594666, 
0.0, 0.0, 0.0, 1.0, 
1.0, 1.0, 1.0, 0.0, 2.350988701644575e-38, 2.350988701644575e-38)
offset 746333	(3,)
offset 746334	(20,)
offset 746336	lockInfluenceWeights
offset 746356	(234, 148, 171, 143, 0, 0, 0, 1, 0, 63, 128, 0, 0)
offset 746369	(5,) - child count
.....

       I use this to get bones (it is not for Noesis):

	skeleton=Skeleton()
	skeleton.BONESPACE=True
	skeleton.NICE=True

	def boneTree(g,parent):
		bone=Bone()
		skeleton.boneList.append(bone)
		bone.name=g.word(g.H(1)[0])		
		if parent is not None:
			bone.parentName=parent.name
		A=g.f(14)	
		bone.posMatrix=VectorMatrix(A[1:4])
		bone.rotMatrix=QuatMatrix(A[4:8]).resize4x4()
		
		g.B(1)
		g.word(g.H(1)[0])	
		g.B(13)
		childCount=g.i(1)[0]
		for m in range(childCount):
			boneTree(g,bone)
		
		
	g.seek(746059)
	boneTree(g,None)
	skeleton.draw()	




```

[skeleton.jpg](https://xentaxbackup.github.io/file/10916_skeleton.jpg)
## Post #4
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2016-05-09T01:34:44+00:00
- Post Title: Persona 4: Dancing All Night

Oh I was reading the rotations wrong for those bones. Unfortunately those bones aren't the ones the meshes are skinned to, the bones at the top of the model are (In pc001_01 starting at 350809, 69 bones. 4x4 matrices). Also in pc001_01 at 355229 there are 69 shorts (the same number of bones) that seemingly have something to do with the second skeleton but I don't know what/how.
## Post #5
- Username: PolarSoda
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 17, 2014 10:49 am
- Post datetime: 2016-05-15T00:50:21+00:00
- Post Title: Persona 4: Dancing All Night

Oh, I thought I had posted a reply on this thread

btw I did try to import one of the gmd models in noesis (i think it was the nanako one/08) and i exported it as a psk
the rigging was fine if im not mistaken? kinda weird but yes it was ok

if anything the models appear to be rotated in a very weird way if you import it to blender
and yeah the faces seem to have all their expressions at once if you import them in noesis o:, maybe this could be fixed by loading the gap data? 

but yeah thats what i was going to say, sorry for not posting before
and thanks for replying btw ;w;
## Post #6
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-05-16T14:42:28+00:00
- Post Title: Persona 4: Dancing All Night

How to use python script in lastest blender?
## Post #7
- Username: headgehof
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jun 27, 2010 10:11 pm
- Post datetime: 2016-05-21T21:21:09+00:00
- Post Title: Persona 4: Dancing All Night

search for Marie DLC 
thanks
## Post #8
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2016-05-27T20:52:30+00:00
- Post Title: Persona 4: Dancing All Night

Bone links seem to be off, Has anyone figured those out yet?
## Post #9
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2016-10-04T03:36:17+00:00
- Post Title: Persona 4: Dancing All Night

> Reply from Simguy
>
> I've been looking at this for a while. I'm going to ramble because I didn't really write any of my findings down. I've been working on this (horrible looking) Noesis Script. GAP's are animations, GMD's and GFS's are models. This script can load every model except pc008_f1 and pc008_f2 (Those are weird and I didn't look into why yet).

There are a few more problems with my script. I can't figure out the bones parents. The characters have 2 skeletons in their files, A bind pose (for the skinning) and some kinda animation rig. The rig could be useful if I could figure out the first skeletons bone parents but I hit a brick wall on that. The other problem is that some meshes have their positions relative to a node that its parented to (not skinned to) so they are far out of position. This mostly happens to some of the characters eyes, I have no idea how to fix that.

I'll try to explain more later today so maybe some greater minds can help.

These files don't seem to work. Whenever I try to open it using that script, it says theres an error with line 521 it seems. I wish I could understand this stuff but just looking at it makes my head hurt. lol.

```
https://mega.nz/#!fxljiTYD!VLcDnBwS_TIuUDTy7j6Ejc-RNkpG-L5A6NmaC7FKABI
```
## Post #10
- Username: persisent
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 15, 2016 3:49 am
- Post datetime: 2016-12-14T22:44:51+00:00
- Post Title: Persona 4: Dancing All Night

share all game data,please. or how can get this game cpk and how can extracted this cpk,thanks
