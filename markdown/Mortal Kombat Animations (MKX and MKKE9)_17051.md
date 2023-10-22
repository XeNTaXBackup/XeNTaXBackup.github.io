## Post #1
- Username: TTR
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 28, 2011 4:14 am
- Post datetime: 2017-09-22T04:39:31+00:00
- Post Title: Mortal Kombat Animations (MKX and MK:KE9)

Resources: [https://drive.google.com/open?id=0Byiw2 ... XpZeWNzNXM](https://drive.google.com/open?id=0Byiw2ZUNRpDkTXRFWXpZeWNzNXM)

So I'm getting more and more close to figure out how MKX and MK: KE store its animations. These resources are specifically for X, however, KE isn't as complicated and can be more easily understood.

What I've included is a pack of example Shared animations (animations that are shared between all characters, it seems like they all have the same Hit Reactions which I've included), one TPose shared animation, some analyses I've typed up, and the NameTable associated with these. The Hit Reactions all use the same SharedAnimData, the TPose has another one but they should be virtually identical. All of this is found in the FightingArts.xxx package in MKX, just decompress it using the unreal decompression tools, then extract it using the extraction tools. I've saved you that step.

These files store data really simply, but in a way that uModel isn't programmed to handle at all. Somehow uModel can handle meshes and stuff perfectly, but animations it messes up on completely. I've done this so that someone who might be a little bit more knowledgeable than me in reversing animations may be able to help.

NameTable:
This is a set of references that each pack will have. Because of this, the data between packs may LOOK different and have different hex signatures for different things, but this translates these signatures into something readable. For example, if I take an animation from CHAR_Scorpion_N_ScriptAssets, it would look different than an animation from FightingArts. But, using the table, you'll find the structures are more or less the same. Usually, each reference to the list will be a 64bit reference, then you take whatever number that is IN DECIMAL and take it from the NameTable. For example, you might see 0000000000000024h. This points to decimal 36, which is "ArrayProperty" on the NameTable. This means the next set of data is an Array. I think UModel's code handles this a lot easier when serializing.

SharedAnimData:

This is a data structure that ensures all skeletons in the game can potentially use any animation, which modders have already discovered (i.e. models can swap to different move sets without the game crashing). This is because all skeletons use the same naming structure, but different translations/rotations. The game uses this data to retarget these animations.

It starts off with TrackBonesNames, which is an array of references where each is a bone on the common skeleton. It then goes into some kind of generated spheres type reference. The game lists one for each bone and gives its position as well as a radius around this position. Then there's some kind of MD5 checksum data listing which I don't fully understand. If you make it an array, it's a 128bit hash. But why?

AnimSequence:

I'm about 90% certain that actual animation data is stored in these Sequences. Longer sequences in this game are much bigger than shorter sequences, so filesize seems to line up with data actually being in the Sequences. However, I'm not sure about how keys are stored at all. The biggest things are the CompressedTrackOffsets, which accurately list the number of frames in the animation, then there's some kind of m_nVersion flag (no idea, this is the part that confuses Gildor), and then a MotionTrackIndex that is undocumented and most likely custom. After the final None, it seems like keys are probably stored. I think if I figured out how it's decompressing the data it would be easier. EDIT: I've figured out the track table, and added notes to the AnimSequence text file to reflect more stuff I've found. Rotation Tracks are giving me huge, huge issues. I can't figure out still.

If anyone has some tips or hints that would be great, I would love to try to add compatibility for MKX animation, and MK: KE, into uModel.
