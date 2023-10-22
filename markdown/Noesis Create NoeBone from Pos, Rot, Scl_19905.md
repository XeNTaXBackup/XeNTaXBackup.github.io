## Post #1
- Username: dgl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 28, 2019 1:32 pm
- Post datetime: 2019-03-29T03:42:00+00:00
- Post Title: Noesis Create NoeBone from Pos, Rot, Scl?

I have a bone format that is stored as position, rotation, and scale as vectors. I'm looking over the NoeBone and NoeMat functions, but I don't see an clear way to create a NoeBone from these transformations.

```
		for i in range (0, self.header['boneCount']):
			id = self.bs.readShort()
			parentId = self.bs.readShort()

			pos = NoeVec3([
				self.bs.readFloat(),
				self.bs.readFloat(),
				self.bs.readFloat()
			])

			rot = NoeVec3([
				self.bs.readFloat(),
				self.bs.readFloat(),
				self.bs.readFloat()
			])

			scl = NoeVec3([
				self.bs.readFloat(),
				self.bs.readFloat(),
				self.bs.readFloat()
			])

			# How to Generate NoeMat43?

```
## Post #2
- Username: dgl
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-29T08:43:53+00:00
- Post Title: Noesis Create NoeBone from Pos, Rot, Scl?

Just look in the python folder at the file inc_noesis.py
then find the starting data type like for instance 
class NoeQuat
you can see it being initialized
quat = (0.0, 0.0, 0.0, 1.0)
and the option
toMat43
so you could do
myQuat = NoeQuat().toMat43()
then set the position with
myQuat[3] = [x,y,z]
## Post #3
- Username: dgl
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 28, 2019 1:32 pm
- Post datetime: 2019-03-30T03:41:34+00:00
- Post Title: Noesis Create NoeBone from Pos, Rot, Scl?

Thanks for the reply. From reading through the source code, I was starting to suspect that was the expected approach. Suspicions confirmed, but the implementation turned out pretty simple.

```
		for i in range (0, self.header['boneCount']):
			id = self.bs.readShort()
			parentId = self.bs.readShort()

			pos = NoeVec3.fromBytes(self.bs.readBytes(0x0c))
			rot = NoeAngles.fromBytes(self.bs.readBytes(0x0c))
			scl = NoeVec3.fromBytes(self.bs.readBytes(0x0c))

			name = "bone_%03d" % id
			parentName = "bone_%03d" % parentId

			mat = rot.toMat43()
			mat[3] = pos;
			mat[0][0] = scl[0]
			mat[1][1] = scl[1]
			mat[2][2] = scl[2]

			if i == 0:
				bone = NoeBone(id, name, mat)
			else:
				bone = NoeBone(id, name, mat, parentName, parentId)
			self.bones.append(bone)

```


Looks like NoeAngle has the option to be converted into a NoeMat43 as well, so from there it's just a matter of setting the position and scale.
