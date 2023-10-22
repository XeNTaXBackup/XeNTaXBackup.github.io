## Post #1
- Username: Ryder25
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 01, 2011 6:43 am
- Post datetime: 2015-12-28T00:34:22+00:00
- Post Title: Rise of Nations Models

Hey everyone,

I have figured out most of the file format for Rise of Nations, but there's just this one section that I can't figure out that has to do with the normals I think.

Here is a link to my 3ds Max scripts, and 010 Editor binary templates:
[https://github.com/Ryder25/Rise-of-Nations](https://github.com/Ryder25/Rise-of-Nations)

The section in question is chunkId 3. Any help is greatly appreciated.

There was an official exporter released for this game, but it worked for 3ds Max 5 only. I want to create a new importer/exporter for this game, so that newer versions of 3ds Max can be used.

Attached is the old exporter with some official 3ds max meshes, and also example 3d files and animations (bh3, bha respectiviely).  They mention using smoothing groups, and also physiques.  Since physique's seem to no longer be used, I thought I would use skin intead.  Does anyone know how to limit it so that there's no blending? (I believe this means only one bone per vertex)

Thank you!

[http://www.mediafire.com/download/sjqb9 ... models.zip](http://www.mediafire.com/download/sjqb99tygkwt2p9/RoN_models.zip)
## Post #2
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-12-31T02:34:02+00:00
- Post Title: Rise of Nations Models

This seems to look okay to me, but I can't verify if it's correct. Here's the edited part.
In response to your question about the skin modifier, you can set the amount of max weights via maxscript by getting the skin modifier and modifying the 'bone_Limit' property. It's equal to setting the bone affect limit in the skin modifier under advanced settings.

```
(
	local vertIndex = readLong binStr
	local vertCount = readLong binStr
	local boneName = readStr binStr
	local boneRot = inverse(quat (readFloat binStr) (readFloat binStr) (readFloat binStr) (readFloat binStr))
	local bonePos = [(readFloat binStr),(readFloat binStr),(readFloat binStr)]
	local boneTm = transmatrix bonePos
	boneTm = (boneRot as matrix3) * boneTm
	readFloat binStr
	local boneDum = dummy name:boneName rotation:boneRot position:bonePos boxsize:[1,1,1]
	--local boneDum = BoneSys.createBone boneTm.row4 (boneTm.row4+boneTm.row1) boneTm.row3
	--boneDum.name = boneName
	--boneDum.showlinks = true
	--boneDum.setBoneEnable false 0
	if (not(parent == undefined)) then
	(
		boneDum.parent = parent
		boneDum.transform *= parent.transform
	)
	
	-- Get the transpose of the inverse bone matrix
	nrmMtx1 = inverse boneDum.transform
	nrmMtx2 = inverse boneDum.transform
	for i = 1 to 3 do
	(
		for j = 1 to 3 do
		(
			nrmMtx2[j][i] = nrmMtx1[i][j]
		)
	)
	nrmMtx = nrmMtx2
	
	-- Set the translation part to 0
	nrmMtx.row4 = [0,0,0,0]
	
	if vertCount > 0 then
	(
		local vtIndex
		for vt = 1 to vertCount do
		(
			vtIndex = vt + vertIndex
			vertices[vtIndex] = vertices[vtIndex] * boneDum.transform
			normals[vtIndex] = normals[vtIndex] * nrmMtx
		)
	)
	append weights [vertCount,vertIndex]
	append dummies boneDum
	boneDum
)

```
## Post #3
- Username: Ryder25
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jan 01, 2011 6:43 am
- Post datetime: 2015-12-31T09:16:52+00:00
- Post Title: Rise of Nations Models

Thanks a lot TGE! I tried this out, and it seemed to work quite well. It wasn't perfect compared to the official rifleman.max file that I tested against, but I'm not sure if the rifleman.bh3 was exported directly out of that max file anyway. The differences are not much regardless. [http://imgur.com/fZ1XwD6](http://imgur.com/fZ1XwD6)  This is most likely due to the max file only having 141 normals, but when it was exported, 233 normals had to be created to match up with the vertex count.

I still wonder why chunkID 3 has an extra 4 bytes per normal after the main array of normals. I just filled in 0xFF for those bytes, and I didn't notice any changes in game, and the model still seemed to look fine.

One thing I should mention though, is that members of matrix3 values in 3ds Max seem to be immutable. For some reason your loop for transposing didn't work on my end. I ended up using the following code instead:

```
				   nrmMtx = matrix3 [nrmMtx[1][1],nrmMtx[2][1],nrmMtx[3][1]] [nrmMtx[1][2],nrmMtx[2][2],nrmMtx[3][2]] [nrmMtx[1][3],nrmMtx[2][3],nrmMtx[3][3]] [0,0,0]
```


Thanks again for all of your help! I have uploaded the latest changes to github.
## Post #4
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-12-31T13:43:00+00:00
- Post Title: Rise of Nations Models

Glad to have been able to help.
