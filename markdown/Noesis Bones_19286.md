## Post #1
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2019-01-08T16:01:56+00:00
- Post Title: Noesis Bones

Hello, I'm trying to parse model bones and create in noesis. This is what I'm trying to achieve:



And this is what I got in noesis with my script:



```
            
        for i in range(self.numBones):
            boneName = self.read_name()
            boneIndex = self.inFile.readUShort()
            boneFlags = self.inFile.readByte()
            #boneMatrix = self.inFile.read('16f')
            boneMat = NoeMat44.fromBytes(self.inFile.readBytes(64)).toMat43()
            boneChildCount = self.inFile.readUInt()
            bone = NoeBone(boneIndex, boneName, boneMat)
            self.boneList.append(bone)


```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-01-08T22:14:39+00:00
- Post Title: Noesis Bones

make sure you provide all parts of the bone.
self.boneList.append(NoeBone(i, "bone%03i"%i, mat, None, boneParent))
## Post #3
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2019-01-09T00:05:37+00:00
- Post Title: Noesis Bones

Thank you. Besides, I needed to transpose matrix.
