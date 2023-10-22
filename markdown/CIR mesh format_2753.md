## Post #1
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-15T17:51:40+00:00
- Post Title: CIR mesh format

Today, for a change, I would like to get some help. 

I'm currently working on a mesh format, and being a complete newbie in the field of 3D technology, I seem to be stuck. The following is a format description:

```
Version     : Longint // 16 or 256 allowed
Unknown1    : Longint // only exists in v. 256, set to zero otherwise
Unused      : Longint // 0xdeadbabe
Unknown2    : Single  // probably extreme coordinate value
NumMaterials: Longint
{
  MatNameLen  : Longint
  MaterialName: string
  Unknown1    : Longint
  TexNameLen  : Longint
  TextureName : string
  ColourR     : Single
  ColourG     : Single
  ColourB     : Single
}
NumEntries: Longint // unknown list, does usually not exist
{
  Unknown1: Single
  Unknown2: Single
  Unknown3: Single
  Unknown4: Single
}
NumBones: Longint // really bone list? tree structure!
{
  BoneNameLen: Longint
  BoneName   : string
  Unknown1   : Single
  NumChildren: Longint
  {
    Child: Longint
  }
}
NumGroups: Longint // usually only one
{
  GroupNameLen: Longint
  GroupName   : string
  NumBodyParts: Longint
  {
    MaterialIndex: Longint
    NumVertices  : Longint
    {
      X1        : Single
      Y1        : Single
      Z1        : Single
      X2        : Single
      Y2        : Single
      Z2        : Single
      NormalX   : Single
      NormalY   : Single
      NormalZ   : Single
      TextureS  : Single
      TextureT  : Single
      BoneIndex1: Longint // really?
      BoneIndex2: Longint // really?
      BoneWeight: Single // really? can be != 1, even if BoneIndex1 = BoneIndex2
    }
    NumTriangles: Longint
    {
      VertexIndex1: Longint
      VertexIndex2: Longint
      VertexIndex3: Longint
    }
  }
  NumEntries1: Longint // unknown list, does usually not exist
  {
    Unknown1: Single
    Unknown2: Single
    Unknown3: Single
    Unknown4: Single
    Unknown5: Longint
  }
  NumEntries2: Longint // unknown list, does usually not exist
  {
    StrLen   : Longint
    Unknown1 : string
    Unknown2 : Single
    Unknown3 : Single
    Unknown4 : Single
    Unknown5 : Single
    Unknown6 : Single
    Unknown7 : Single
    Unknown8 : Single
    Unknown9 : Single
    Unknown10: Longint
  }
}
```

Note that the format itself has been verified via disassembly, while the meaning of the values is guesswork. Alas, some stuff in the above description might be wrong, especially the accordingly commented parts.

My main concern is the interpretation of the values contained in the vertex descriptions. I'm not sure why there is more than one coordinate definition, thus I'm not sure how to render the meshes. Some observations:
- If both BoneIndexes (if there is really such a thing as bones in this file, I'm not entirely sure) of a vertex are the same, both of the coordinate sets are usually nearly identical and the "BoneWeight" value is exactly 1 in most cases, though not always.
- If the BoneIndexes are different, they usually seem to point to attached bones in either direction (parent/child or child/parent) and the coordinate sets usually differ in X direction, sometimes in the other directions as well.

Thus my questions: Are the coordinates given in the vertex definition relative to some other system? Why are there two of them? Could there be an implicite symmetry somewhere (as in "define the left leg, mirror the right one")?

For now, I just use the first coordinate set for rendering, which sometimes works ...

... and sometimes doesn't ...

... where this is supposed to be the backside of a pair of trousers; the model's behind complete with back pocket is recognizable if you look closely. The rest is probably supposed to be a leg ...

Help! 

[Edit: Forgot to add an example file. I don't expect anybody to write a converter for this format, though. Just some hints would be fine.]
[april_1000.zip](https://xentaxbackup.github.io/file/1318_april_1000.zip)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-16T21:46:47+00:00
- Post Title: CIR mesh format

By looking at just 1 file. It is hard to tell what is missing from the format above!

But something pop out from my mind that the vertices need to transform with the bones as well!  Like "The Sims", "half-life" etc. 

The face came out fine because all the vertices bind to 1 bone, but that april mesh bind to different bones.

Not sure, just guessing! 

PS: What game is it?
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-17T07:58:30+00:00
- Post Title: CIR mesh format

Thanks for your reply.

> Reply from fatduck
>
> By looking at just 1 file. It is hard to tell what is missing from the format above!
That should not be a problem. I've attached some more examples. and if you want even more data, you could take a look at the demo (the game's name is "The Longest Journey", by the way), which can be found at [http://www.longestjourney.com/download/demo/](http://www.longestjourney.com/download/demo/). You can view the game data using my [TLJView](http://wiki.xentax.com/index.php/The_Longest_Journey_Toolset) application, which will give you a textual representation of the CIR files as well (though most values will be called "Unknown"):

> Reply from fatduck
>
> But something pop out from my mind that the vertices need to transform with the bones as well!  Like "The Sims", "half-life" etc.
I assume so, yes. But to do that, I would need the bone positions. I'm not sure where to find those in the given data. One could imagine that certain parts of the vertex data are actually bone descriptions, but as far as I can see, all of them are referenced in the triangle section as actual vertices (at least in the above example).

> Reply from fatduck
>
> The face came out fine because all the vertices bind to 1 bone, but that april mesh bind to different bones.
Yes, you're right, all of them are bound to one bone and all weights are exactly 1, so this is the trivial case. By the way, I forgot to mention that both objects shown above (i.e. the face as well as the pair of trousers) are contained in the given example mesh. They're just two different body parts which I chose to render separately.

Thanks again!
[moremeshes.zip](https://xentaxbackup.github.io/file/1322_moremeshes.zip)
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-21T13:39:33+00:00
- Post Title: CIR mesh format

OK, I tried the demo. That April's voice is annoying  
Back to the topic. I had a look on animation file(ani) and found these:

```
  dword		headerID	//03 animation
  dword		version		//?? always 256
  dword		const1		//0xA9F5D5CE
  dword		const2		//0xDEADBABE
  dword		nMaxKeyTime	//Length of the animation
  dword		nBones
  dword				//0
  dword				//always 1
  dword				//0
  dword				//0
  dword				//0
  dword				//0
  float				//always 1
  dword				//0
  dword				//0
  dword				//0
}
struct Anim {

  dword		nBoneID
  dword		nFrames

  struct KeyData {
    dword	nKeyTime	//1 second = 1000
    float X 4	QRotXYZW
    float X 3	PosXYZ
  } KeyData[nFrames]

} Anim[nBones]

```


So you might try to transform the model parts with these!

And also the 2 BoneIndeices means each vertex could be affected by 2 bones. If 2 BoneIndeices are equal, the weight will be 1.(One bone anyway). If they are different, the BoneWeight will be for the 1st index. Weight for the 2nd bone will be (1 - BoneWeight)

For the 2nd set of coordinate, I guess it's for morph anination. Because there are some instructions(look like) in the script file.
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-21T15:27:22+00:00
- Post Title: CIR mesh format

> Reply from fatduck
>
> OK, I tried the demo. That April's voice is annoying
Hey, Sarah Hamilton's voice work is one of the most acclaimed aspects of the game, and deservedly so. 

> Reply from fatduck
>
> Back to the topic. I had a look on animation file(ani) and found these:
You got the format almost correct. Just some minor modifications:

```
  dword		headerID    //03 animation
  dword		version     //3 or 256
  dword		const1      //0xA9F5D5CE (only in version 256, internally set to 0 otherwise)
  dword		const2      //0xDEADBABE (swapped with next field in version 3)
  dword		nMaxKeyTime //Length of the animation (swapped with previous field in version 3)
  dword		nBones
}
struct Anim {

  dword		nBoneID
  dword		nFrames

  struct KeyData {
    dword	nKeyTime	//1 second = 1000
    float X 4	QRotXYZW
    float X 3	PosXYZ
  } KeyData[nFrames]

} Anim[nBones]

```

(The "header" part containing many zeros should already be part of the Anim structure.)

Thanks for the interpretation, this surely looks promising. One question concerning the rotation, though: How does it relate to the positions given -- is it relative to the position of the parent bone?

I'll try and see if I can just render the first frame -- that should give me a basic position, shouldn't it?

> Reply from fatduck
>
> And also the 2 BoneIndeices means each vertex could be affected by 2 bones. If 2 BoneIndeices are equal, the weight will be 1.(One bone anyway).
Okay, good, I suspected that. I was a bit unsure about it as there are some instances where the weight is not equal to 1, even if the bone indices are identical. (I can't quote it right now, but I think there was at least one example with a weight of 0.95[...]. I'd have to look that up.)

Thanks for your help!
## Post #6
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-22T15:46:23+00:00
- Post Title: CIR mesh format

Okay, this is the skeleton I get when I use the position and rotation information from the .ani file together with the bone tree from the .cir file. It's a bit ... weird. 

I'll probably first check if I have some of the data mixed up ...
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-22T17:06:37+00:00
- Post Title: CIR mesh format

No, you did something wrong!
Here is what I got from  man1_walk.ani and Man1.cir

About the format, you are right. I missed out the root bone.  
[Ani.jpg](https://xentaxbackup.github.io/file/1325_Ani.jpg)
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-22T22:32:21+00:00
- Post Title: CIR mesh format

Heh, stupid mistake. I read the BoneID, but ignored it afterwards. 
This looks much better now:

Some vertices still seem to be a bit off, but that's probably another programming bug.

Once again, thanks for your help!
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-23T00:27:12+00:00
- Post Title: CIR mesh format

Just a quick note: A linear interpolation between the two coordinate sets (using the BoneWeight value) seems to fix some of the wrong vertices, while the result is not fully correct yet.

Additionally, the whole model seems to be mirrored on the YZ plane. Is there any quick way to correct this?
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-23T11:24:57+00:00
- Post Title: CIR mesh format

I'm not good in maths, if you want to mirror y-axis. You can multiply the transform by [1,0,0] [0,-1,0] [0,0,1] [0,0,0] etc.

For the vertices not correct. Are those with same bone indices but weight less than 1? Try make the weight = 1 !? Or weight it with root bone(index 0) as well !?

PS: I am not good in maths. What formula do you use to calculate the interpolation? Thank you very much if you could share it for me.
## Post #11
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-23T17:28:44+00:00
- Post Title: CIR mesh format

I'll see what can be done about the mirror image, but it's currently not that important anyway ...

> Reply from fatduck
>
> For the vertices not correct. Are those with same bone indices but weight less than 1?
I'm not sure whether this is always the case, but at least some of those vertices are among the incorrect ones.

> Reply from fatduck
>
> Try make the weight = 1 !? Or weight it with root bone(index 0) as well !?
I'll try that, thanks!

> Reply from fatduck
>
> PS: I am not good in maths. What formula do you use to calculate the interpolation? Thank you very much if you could share it for me.
Sure. It's just a linear interpolation, though, nothing fancy:
PosX := BoneWeight * X1 + (1 - BoneWeight) * X2
PosY := [...]
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-23T18:32:42+00:00
- Post Title: CIR mesh format

> Reply from Deniz Oezmen
>
> 
fatduck wrote:PS: I am not good in maths. What formula do you use to calculate the interpolation? Thank you very much if you could share it for me.
Sure. It's just a linear interpolation, though, nothing fancy:
PosX := BoneWeight * X1 + (1 - BoneWeight) * X2
PosY := [...]

How about the rotation? 
For example: you turn your face 90 to the left. You will have the same position but different rotation!?
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-23T21:22:34+00:00
- Post Title: CIR mesh format

I'm not sure I have understood you correctly -- the rotations only affect the skeleton, which seems to be perfectly well-formed. Only the relative vertex positions are still a bit unclear, I'd say.
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-26T09:29:32+00:00
- Post Title: CIR mesh format

Okay, I think I've got it now. I asked a friend who is experienced in 3D programming, and he almost immediately pointed me at the solution: The two vertex positions are relative to the two bones, i.e. (X1, Y1, Z1) is a coordinate in the system for bone 1, while (X2, Y2, Z2) belongs to the system of bone 2. The weight then tells us how to interpolate between these two positions in absolute (!) terms.

In hindsight, this makes perfect sense, more than anything else. 

The lighting on the textures is not yet correct, but here's the current status, looking much better than before:



Once again, thanks for the help. I appreciate it!
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-26T10:51:42+00:00
- Post Title: CIR mesh format

Right about the lighting but you've made a great big leap from the before and after. Quite amazing really.
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-26T14:21:58+00:00
- Post Title: 

I think I've got that (almost) fixed as well ...
## Post #17
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-27T00:22:18+00:00
- Post Title: 

Aaannd ...
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-08-27T02:29:20+00:00
- Post Title: 

Animation too? Now thats something I don't ofter seen done!
## Post #19
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-27T07:48:51+00:00
- Post Title: 

The animation files had to be loaded anyway to display the model (since there is no base position), so it wasn't very far away. I'm currently checking if the animations are correct, though.
## Post #20
- Username: carpedieem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 27, 2018 2:27 am
- Post datetime: 2020-06-04T13:10:12+00:00
- Post Title: 

Hi there. Thank you for your viewer OP btw, I think it's the only one for TLJ!

Has anyone ever written a script to load cir meshes in 3dsmax, or even better export a mesh as a cir file? I haven't found any
