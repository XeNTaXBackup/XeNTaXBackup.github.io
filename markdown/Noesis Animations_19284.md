## Post #1
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2019-01-08T13:36:43+00:00
- Post Title: Noesis Animations

Hello, I'm trying to implement animation support in a noesis [plugin](https://github.com/RoadTrain/noesis-plugins-official/blob/master/finale00/fmt_LithTech_abc.py). I've already been able to read animation data such as its name, keyframes, etc., as described [here](https://github.com/cmbasnett/io_scene_abc/wiki/ABC#animation-1), but I'm with a doubt about how append this animation so for noesis load it. Probably I must use setAnims (as the original code does) but I've no idea how it handle data structure. Could anyone help?

Here's the code (parse_animations it's the code that I did)
[https://paste.ofcode.org/9mC999E7kF8hmSJVyHPAsX](https://paste.ofcode.org/9mC999E7kF8hmSJVyHPAsX)
## Post #2
- Username: Kerilk
- Rank: beginner
- Number of posts: 38
- Joined date: Sun Aug 27, 2017 9:08 pm
- Post datetime: 2019-01-13T07:05:03+00:00
- Post Title: Noesis Animations

I only used animations in Noesis using the c++ interface ([https://github.com/Kerilk/noesis_bayonetta_pc](https://github.com/Kerilk/noesis_bayonetta_pc)), but nonetheless the process should be similar in python:

 for each animation :
    - create a (local) transform matrix for each bone of the model
    - create an animation out of the matrices using rpgAnimFromBonesAndMatsFinish (bones, bone_number, matrices, frameCount, frameRate);
    - put this anim in a list
 create an animation from you list of animation:
    - int anims_num = animList.Num();
    - noesisAnim_t *anims = rapi->Noesis_AnimFromAnimsList(animList, anims_num);
 set the model to use the animation: rapi->rpgSetExData_AnimsNum(anims, 1);
The api suggests that other approaches might be viable but I never managed to achieve it any other way.

Sorry I can't be of more help.

for reference:

```
	if (!anim) {
		DBGLOG("Could not create anim for %s (out of memory?)!\n", fname);
		rapi->Noesis_UnpooledFree(matrixes);
		continue;
	}

	anim->filename = rapi->Noesis_PooledString(fname);
	anim->flags |= NANIMFLAG_FILENAMETOSEQ;
	anim->aseq = rapi->Noesis_AnimSequencesAlloc(1, frameCount);
	anim->aseq->s->startFrame = 0;
	anim->aseq->s->endFrame = frameCount - 1;
	anim->aseq->s->frameRate = 60;
	anim->aseq->s->name = rapi->Noesis_PooledString(fname);
	if (anim)
	{
		animList.Append(anim);
}
```
## Post #3
- Username: Crazy
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 08, 2019 9:26 pm
- Post datetime: 2019-01-13T12:35:38+00:00
- Post Title: Noesis Animations

Hello, thank you for your answer. I did some tries based in python scripts, but didn't work.

Code:

```
    anim = Animation()
    anim.extents = NoeVec3.fromBytes(self.inFile.readBytes(12))
    anim.name = self.read_name()
    anim.unknown = self.inFile.readInt()
    anim.time = self.inFile.readUInt()
    anim.frameCount = self.inFile.readUInt()
    animMat = []

    for j in range(anim.frameCount):
        self.inFile.readUInt()
        self.read_name()

    for k in range(self.numBones):
        for j in range(anim.frameCount):
            pos = NoeVec3.fromBytes(self.inFile.readBytes(12))
            rot = NoeQuat.fromBytes(self.inFile.readBytes(16)).transpose()
            mat = rot.toMat43() 
            mat.__setitem__(3, pos)
            animMat.append(mat)

    noeAnim = NoeAnim(anim.name, self.boneList, anim.frameCount, animMat, 30.0)
    self.animList.append(noeAnim)
```


Result:


I would like to try your suggestion, but I'm with a doubt about how "transformations" work in lithtech .abc models. I can provide the plugin with a model for testing purpose.

Besides, here's the model animation reference.
[https://github.com/cmbasnett/io_scene_a ... nimation-1](https://github.com/cmbasnett/io_scene_abc/wiki/ABC#animation-1)
