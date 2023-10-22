## Post #1
- Username: srbvn
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Oct 03, 2019 6:10 pm
- Post datetime: 2020-02-22T17:22:41+00:00
- Post Title: [Noesis] Animation matrices - localspace and worldspace

Hi everyone, 
With strong help from jayn23 ([viewtopic.php?f=16&t=21731](https://forum.xentax.com/viewtopic.php?f=16&t=21731)), I could now parse the mesh and bones for my desired models. However, we are in trouble with animations.

Bones and mesh are in 1 file and animation in another one. Bones are in world space while matrices in animation files may be not (I guess so).

I think there are something to do with local space and world space for matrices in animation files, and have tried some ways but none of them work. The game uses DirectX as I known.

Hope someone proficient in animation could help. Many thanks.
Here is the animation file structure (there are 5 animation in the example file)

```
unk1 4 bytes // 00 00 00 00
numAnim 4 bytes Uint
frameRate 4 bytes Uint
animName 30 bytes string
numBones 4 bytes Uint
numFrames 4 bytes Uint
unk2 4 bytes // 
boneNames [] 30 *  numBones // string
boneMatrices [] 64 * numBones * numFrames bytes // 4x4 matrices, may be not need to invert

```

and current noesis script (animation not work): [https://pastebin.com/4sgQwuJR](https://pastebin.com/4sgQwuJR)
[003.rar](https://xentaxbackup.github.io/file/17542_003.rar)
