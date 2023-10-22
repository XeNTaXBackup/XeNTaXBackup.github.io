## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-18T20:05:36+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

Hello everyone,

I have a noesis script and the animation seems inverted? I'm not sure, but mr. Szkaradek123 told me this about my file format:

> Armature use absolute position for bones. 
>
> It is important . You must multiply each bone frame transform (matrix 4x3) with bone position from armature from obj file.
You can find the discussion [here](http://forum.xentax.com/viewtopic.php?f=16&t=15030&start=15).

This is the animation parsing portion of my script:

```
    numBones  = ani.readShort()
    numFrames = ani.readShort()
    
    animFrameMats = []
    
    for fi in range(0, numFrames): # frames
        for bi in range(0, numBones): # bones
            boneMat  = bones[bi].getMatrix()
            frameMat = NoeMat43.fromBytes(ani.readBytes(48))
            matrix   = boneMat * frameMat
            animFrameMats.append(matrix)

    anim = NoeAnim("action_%d" % aci, bones, numFrames, animFrameMats)
    anims.append(anim)

```


But the result is messed-up:



As reference, here is part of the script that relates to the bone:

```
NoeMat44.fromBytes(obj.readBytes(64)) # unknown
NoeMat44.fromBytes(obj.readBytes(64)) # unknown
NoeMat44.fromBytes(obj.readBytes(64)) # unknown
NoeMat44.fromBytes(obj.readBytes(64)) # unknown

bones.append(NoeBone(boneIndex, boneName, boneMat, bonePName, bonePIndex))

```


The related files can be found [here](http://www.mediafire.com/download/6fkt57l5sllocuo/noesis_anim_bug.zip). (including the noesis plugin)

QUESTION: What am I missing? Is the animation wrong? Or is the animation messed-up because the bones are wrong?
## Post #2
- Username: majidemo
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-19T10:41:41+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

I was going to half-ass a reply to this without looking, but I decided to actually look at your sample and saw there are quite a few issues:

1) The first matrix stored in the file is the inverse bind pose, but the second one is just the modelspace bind pose, which you could use instead of inverting the first one, like:

```
            boneMat = NoeMat44.fromBytes(obj.readBytes(64)).toMat43() #bind pose
            NoeMat44.fromBytes(obj.readBytes(64)).toMat43()
            NoeMat44.fromBytes(obj.readBytes(64)).toMat43()
            NoeMat44.fromBytes(obj.readBytes(64)).toMat43()
```

2) Your weights are wrong, where bidx2-4 are always 0, and bwgt is always 1, so you are specifying unnormalized weights. You probably want to read a single index as a uint32 and use that with a single weight, unsure without seeing more files in this format if that's correct or not globally. For this file, this works:

```
            bidx1 = obj.readUInt()                                         # i weight index 
            wgtList.append(NoeVertWeight([bidx1], [bwgt])) # set weights
```

3) Your logic for creating bone names ends up referencing the wrong bone by name for the root, which offsets the whole skeleton incorrectly when bone parents are later associated by name. Instead of naming the root bone_root, you should do something like:

```
            bonePName = "bone_%d" % bonePIndex if bonePIndex >= 0 else ""
```

4) Unlike model bones, which are in modelspace, animation transforms are assumed to be in local space, so relative to the parent in the hierarchy. In addition to that, the frame transforms in the file are transposed. So you want to rework your whole frame loop to look something like this:

```
                modelSpaceTransforms = []
                modelSpaceInverseTransforms = []
                #first accumulate all of the transforms in modelspace
                for bi in range(0, numBones):
                    boneMat = bones[bi].getMatrix()
                    frameMat = NoeMat43.fromBytes(ani.readBytes(48))
                    modelSpaceMat = boneMat * frameMat.transpose()
                    modelSpaceTransforms.append(modelSpaceMat)
                    modelSpaceInverseTransforms.append(modelSpaceMat.inverse())
                #now run through and calculate local space transforms to use as the animation transforms
                for bi in range(0, numBones):
                    localSpaceMat = modelSpaceTransforms[bi]
                    if bones[bi].parentIndex >= 0:
                        localSpaceMat = localSpaceMat * modelSpaceInverseTransforms[bones[bi].parentIndex]
                    animFrameMats.append(localSpaceMat)
```


Address each of those things, and you'll have a happily transformed fowl.
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-19T10:48:13+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

Hello, I can't believe the very man of noesis would respond to me 

I only have one thing, there are files that the weights have 0.50000, and the indices have something like 10, 13, 0, 0.

--------------------------
Thank you very much it works. Except for files that has the weights of 0.50000 and x,y,0,0 bidx. I left this unchanged (works for pet too):

```
bidx1 = obj.readByte()                                         # i weight index 
bidx2 = obj.readByte() 
bidx3 = obj.readByte() 
bidx4 = obj.readByte()                                                    
wgtList.append(NoeVertWeight([bidx1, bidx2, bidx3, bidx4], [bwgt,bwgt,bwgt,bwgt])) # set weights
```


The weights are something like:

```
pos -46.468 181.114 -49.751, wgt: 0.500000, bidx: 3 22 0 0
pos -47.803 187.814 -24.509, wgt: 0.500000, bidx: 22 3 0 0
pos -21.495 180.091 -44.933, wgt: 0.500000, bidx: 22 3 0 0
pos -24.359 184.170 -50.520, wgt: 0.500000, bidx: 22 3 0 0
pos -50.402 190.328 -29.360, wgt: 0.500000, bidx: 22 3 0 0
```


The bird works, but the horse doesn't:



But I guess, the problem is the vertex weights and how I set it, so I'll try to figure this out. Thanks again.
## Post #4
- Username: majidemo
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-19T11:11:20+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

Ah, I see. In that case, you probably want to keep reading the 4 bone indices, but instead of the full weight for each, distribute 1-weight over the subsequent indices.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-19T14:05:57+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

> Reply from MrAdults
>
> Ah, I see. In that case, you probably want to keep reading the 4 bone indices, but instead of the full weight for each, distribute 1-weight over the subsequent indices.


Thank you so much.
## Post #6
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-04-02T08:29:50+00:00
- Post Title: [solved] Noesis Animation Issue (4x4 BoneMatrix)

Hi All,
I searched around the forum and found this topic very useful in my case.
I have .mesh file (vertices and bones), .tga file (texture) and .ani file (animation).
I load successfully the bones, the mesh and texture but not animation.



The problem is that bones is in worldspace and animation matrices are assumed in worldspace, too.
I try to follow and multiply matrices in many ways but none of them works.
Here is my current script, file structure and related files. Hope you could take a look and give advise.
Thanks.
[https://pastebin.com/QUfus2CM](https://pastebin.com/QUfus2CM)

```
BlockLength 4 bytes 
numAnim 4 bytes 
Type 4 bytes 
animName 30 bytes 
numBones 4 bytes 
numFrames 4 bytes 
FrameLength 4 bytes 
boneNames [] 30 *  numBones 
4x4boneMatrices [] 64 * numBones * numFrames bytes  // order look like bone0_frame0, bone0_frame1....bone1_frame0, bone1_frame1
```

[UnpackModels.rar](https://xentaxbackup.github.io/file/17861_UnpackModels.rar)
