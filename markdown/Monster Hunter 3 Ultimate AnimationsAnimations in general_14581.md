## Post #1
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-06-28T14:34:56+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

So thanks to the MaxScript from zaramot, we can import models from Monster Hunter 3 Ultimate. Because I prefer working in Blender, I converted the script into a blender .py script ([http://pastebin.com/pcsY1zH3](http://pastebin.com/pcsY1zH3)). I haven't implemented all the vertex formats, but it imports most enemy models.

Now I've turned to animation. I understand that the animation resides within the .lmt files but I'm a bit stumped. What I expected were keyframe indices and rotation values for the bones. But the animation data seems to consist of quite a few other things.

Has anyone else looked at these animations or animations from other video games who could give me pointers as to what kind of data to expect?

Here's what I got so far (as a blender script with explanations): [http://pastebin.com/pfdbnEaD](http://pastebin.com/pfdbnEaD)

P.S.: The blender scripts register as an addon, so they add an entry to the File -> import menu. You can invoke the script from there.
## Post #2
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-07-05T14:58:43+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

> without an lmt sample nobody would know about what to talk
OK, I was thinking about general advice about what sort of data would be in an animation file.
Here's the sample along with what I found so far.
[Dump from my hex editor](http://pastebin.com/raw/fx4LbBjd) [Link to full file](https://www.dropbox.com/s/rx8wtknwfqx9mts/mot_em001_000.lmt?dl=0)

The model I am working with is Rathian:

The model has 44 bones, though only 42 are animated (as is described by the animation header which is just before the sample above).

As far as I can tell, the data blocks in this file are animations, simply because they are too long to be just a keyframe. The file above contains 56 animations. Strangely, in the index at the start of the file, there are also 15 addresses which are just 0. The only other meaningful information about the short sample (which is the first animation) that I got from the header is the number 213, which I assume to be the animation length (in frames?).

The animation block starts at address 0xf2c with 42 data blocks of 36 bytes each. The blocks correspond to the animated bones.
The structure of each of these blocks is as follows:

```
0x0  ubyte  bone id
0x1  ubyte  0
0x2  ubyte  unknown
0x3  ubyte  unknown
0x4  float  1
0x8  uint   data1_length
0xc  uint   data1_offset
0x10 float  rot_x
0x14 float  rot_y
0x18 float  rot_z
0x1c float  rot_w
0x20 uint   data2_offset
```

In order to apply the bone rotation, it is important to note that in Blender, Z is up, whereas for the model, Y is up. In addition, all coordinates are mirrored, and must be inverted. Finally, the quaternion is given in global coordinates (took me a while to figure that one out). That is actually convenient, because it means that the model importer doesn't need to exactly reproduce the bones' orientation, so long as the starting point of the bone is at the correct place.

Next in the animation block is what I've labeled as data2. It's always 32 bytes long (hence, no length argument in the first block). In the sample, these blocks start at 0x1520. There isn't a data block for each bone, some have data2_offset=0. The first 16 bytes could be floats, though they generally represent very small values (<1e-2) and don't look like a quaternion (the fourth value isn't close to one). The following 16 bytes are floats, and represent a quaternion. When applied (the line to do that is commented out in the import script), they form a slightly different pose than the other quaternion from above. Maybe this is the pose at the end of the animation?

Now comes the really confusing part: The data I've labeled as data1. Some simply don't have any, others have between 28 and 176 bytes of it. In another animation file, I found examples of this block being even longer. The data is always multiples of four bytes long. In the sample above, they start at 0x1880. I will give some examples of such data blocks to showcase my confusion:

```
0808743f 08080911 08081824 0808df15 0808f720 0808cf2b 08087400
Data block from bone 4 (the lower jaw):
fffdfff7 ff56bd31 fd863591 faefaae1 f7f95eea f511136f f2ad0a2d f11f843f
f02c00a6 f01d806f f14d84ee  f45fd0bc f8bfa204 fd02736c 2fe13f7c 0ffdfff7
Data block from bone 0 from another animation (excerpt, data block is 1104 bytes long):
1bfd640c b3950002 1b9b6495 b3210002 1acf65f6 b1df0002 19c367dc afe70003
18166af8 abd70003 16c66d6c a6bf0003 16606e1e a0f50002 16b26d10 9ce00003
...
1a8350ea ce1a000c 1bb8591d c2a2000c 1c1e620e b6c60002 1c0b6367 b4a90001
1c0263d6 b3f10001 1bfd640c b3950000

```

I'm, fankly, stumped. The values seem to be in no way similar. From the first and last sample one might assume that it must be interpreted in 2 byte chunks. But whichever way you interpret, the values seem to represent an extreme value range. The first animation is mostly values starting in f or ff, so (relatively) small negative values, but then you have a value like 0x71bc (29116) in there. I just don't know what these numbers could represent.
Some other things about them that confuse me:
The last example implies a repeating structure every 8 bytes, but not all thata blocks have lengths that are divisible by 8.
If these are keyframes in the animation, there should be frame numbers of some sort. The value which I suspected to be animation length was a 4 byte integer, so presumably, frame indices would have to be as well. But there is nothing that could be something like that.
There is a pattern which I found only in the data blocks of length 64 in the first animation (second example above). The first 4 bits of the block are 1111, the rest of the 4-byte block is equal to the last 4-byte value in the block, except for the first 4 bits which are 0000 (compare 0xfffdfff7 and 0x0ffdfff7 above). I did not find this pattern anywhere else.
These numbers are definitely not floats (there are a fair few NaN if they are). The 3dsmax import script by zaramot made reference to "half-floats" (2 byte IEEE floating point numbers), but I find it unlikely that it's those either, as some values are <1 and others are >17000. My best guess at this point is that some of them at least are integers implicitly representing a number between 0 and 1 by dividing by INT_MAX. But even then they don't look much like quaternions, which is what I expect to find in these blocks.
I thought maybe they were hitboxes or camera data, but there are seperate files for the model named "body", "cambody", "hitdata" and "hitsize". I haven't looked at those files in detail, but it sounds like they contain that data.

The animation block ends with another puzzling, if seemingly useless, block of data (begins at 0x20d0 in the sample): 64 0-bytes, followed by a 1 as a 4-byte integer, followed by a 4-byte adress. Repeat 4 times. Then, 0 and 213 (the value of frame_count from the animation) alternating, as 4-byte integers, repeating four times. The addresses point to the 0 values, in sequence. 
I've looked at several animations, and except for the value of frame_count differing, it seems to be always the same. Always the same number of values (even for different models) never anything but 0s and the four 1s.

This has been a fantastic puzzle so far and I'm incredibly pleased that I was able to extract just a pose, but how much more awesome would this look in motion?


If you want to give it a shot yourself: [The model file](https://www.dropbox.com/s/mw61q4iwznsj9xc/em001.mod?dl=0) ,[Animation file](https://www.dropbox.com/s/rx8wtknwfqx9mts/mot_em001_000.lmt?dl=0) (same link as above), [Blender Model import script](http://pastebin.com/raw/zc1qpWVm), [(unfinished) animation import script](http://pastebin.com/raw/1Bw4549c)
Both scripts are registered as addons in blender and will show up under File -> Import. For the animation import to work, an armature needs to be selected.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-05T21:30:29+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

thanks for sharing! (data endianess is 'big'?)

The lmt you provided is much too big/complex, imho.
Don't you have a smaller one?

(A model with less bones, a chicken maybe, could simplify things, too.)

btw: I appreciate your explanations but it's a little bit tedious to follow
would be really helpful if you gave more offsets, for example 0x1A74 for 'Data block from bone 4'

You got the data for a pose, shouldn't the (other) keyframe data have the same structure?
(to be honest I don't know the difference between 'pose' and 'keyframe'
 is a pose a starting keyframe?)

Where does the pose data start?

(For the number related stuff: did you take into account that animation data might be compressed?)
## Post #4
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-07-05T23:28:11+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

> data endianess is 'big'?Yep, all files are big endian.

> Don't you have a smaller one?Well I do have this: [Model file](https://www.dropbox.com/s/63c16i5e3f5lqh6/em022.mod?dl=0), [Animation File](https://www.dropbox.com/s/16ry5d1tts28ogm/mot_em022_000.lmt?dl=0)
Which is a Delex with only 12 bones and 27 animations.

But the animation file is pretty much the same complexity. It's just fewer animations because it's not a boss.

> You got the data for a pose, shouldn't the (other) keyframe data have the same structure? You would think so, wouldn't you? I got two poses out of each animation block, but they don't seem to make sense sequentially (I suspected at one point that what I now read out as "animations" is actually just one pose, but the poses don't match up to an animation). If each animation really only is one (or two) keyframes, that leaves the question open what all that other stuff in there is, which makes up the bulk of the file.

By pose I mean one rotation value for every bone. To make a keyframe, I would also need some kind of time information. A keyframe also doesn't need to involve all bones, it could be just one (i.e. each bone could have keyframes at different frames).

> Where does the pose data start? For the file from the last post, at 0xf2c. In the file from this post, at 0x73c. You can recognize the start by the value 0xff000401 (bone id 255 (invalid), 0, 4 and 1 unknown value). Sometimes it's also 0xff000404. You can also easily recognize the start of an animation block just by visual inspection of the file, as the end of a block involves a lot of 0s (see my last post) which are easy to spot when just scrolling through the file.

You can also look inside the lmt import script, where I have annotations specific to the file from the last post, including offsets.

> For the number related stuff: did you take into account that animation data might be compressed? I thought of that, but I don't really know compression formats. I'll read up on it, but I thought I would first ask if someone else has some intuition as to what the data could mean.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-06T10:57:20+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

thx, I'll give that a go - but I'm very slow.
Before I can contribute anything you'll have solved the ridle, I guess. 

> but I thought I would first ask if someone else has some intuition as to what the data could mean.yep, the one who has is MrAdults. He might jump into discussion as soon as the keyword Noesis appears.  
(But you'll need to dive into Noesis python script before.)
## Post #6
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-07-06T12:51:54+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

> But you'll need to dive into Noesis python script before.I actually have. But I thought Noesis was for textures?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-06T14:47:14+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

> Reply from Scaatis5768
>
> But you'll need to dive into Noesis python script before.I actually have. But I thought Noesis was for textures?Textures is the smallest part. Primary I use it for models, animations and format conversions (especially the to SMD conversion is a must have, imho).

btw: those datablocks, you referred to:
bone id 0, 0x1880, 1C
bone id 1, 0x189C, 4C
bone id 2, 0x18E8, 4C
...
bone id 0x91, 0x2020, B0

Didn't find a pattern/sense so far. Did you try interpreting the data as words?
(At 0x2020 those bytes 0x14, 0x0B, 9, 0x10 (every 8 bytes) are "suspicious", at least.)

For the other lmt (mot_em022) you'd say it contains 25 anims because of 25 occurences of this pattern: 000000xxFF0004?
## Post #8
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-07-06T16:55:29+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

> Did you try interpreting the data as words?I've tried looking at them byte by byte, as two bytes and as four bytes. There could be data recurring every eight bytes (in fact there probably is), but I don't think that there is a single value encoded as eight bytes (like a double). Nothing like that was in the model file, and nothing like that has been in other places in the animation file.

> you'd say it contains 25 anims because of 25 occurences of this pattern: 000000xxFF0004? I guess that's one way to look at it. I get 25 because at the start of the file there is a list with 25 entries, each with a pointer to an address that (usually) happens to contain that sequence.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-06T18:29:00+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

I think you'll need to check more "unusual" datablocks like this one (from mot_em001) to get a clue which meaning the values might have (the count is 448 x 4 bytes):

```
730DB869 CC490001 
72FFABFB CC490001 
72D39DDB CC490001 
7286925F CC490001 
72138DDC CC490002 
..
87EF130E CC490001 
891D1055 CC490001 
8A3D0E1C CC490001 
8B4F0C67 CC490001 
8C530B00 CC490002 
8E3108D7 CC490004 
914605CD CC490004 
937E02BF CC490003 
94970135 CC490003 
95340055 CC490003 
95550008 CC490001 
95270038 CC490001 
94BF00BF CC490004 
92050421 CC490004 
8FAF0633 CC490006 
8C7F089A CC490004 
8B0A09C9 CC490006 
8A200B07 CC490005 
89DC0B7C CC490004 
89B30B29 CC490003 
89A009DD CC490005 
89A80706 CC490002 
89AF0652 CC490002 
89B40636 CC490001 
89B40674 CC490001 
89B306ED CC490002 
89B20898 CC490002 
89B10AE8 CC490006 
89AF12EB CC490002 
89AE1505 CC490002 
89AD165F CC490001 
89AD16AD CC490001 
89AC16B1 CC490002 
89AB15DF CC490005 
89A91285 CC490008 
89A91055 CC490009 
89A90E92 CC490007 
89B80DF6 CC490005 
8A120E1E CC490004 
8A180EEB CC490003 
89A9101B CC490002 
88CF10F8 CC490004 
85BB129B CC490003 
8361147C CC490002 
82591665 CC490002 
8217190D CC490001 
82571AB7 CC490001 
82E61CA2 CC490001 
83CC1ED5 CC490001 
84EF2155 CC490001 
86412428 CC490002 
89702A71 CC490002 
8D553162 CC490002 
91EF38F9 CC490002 
973A4137 CC490002 
9D344A1A CC490002 
A3DA53A3 CC490001 
A76D592B CC490001 
AB2A5F2F CC490002 
B3206C01 CC490002 
BBBA78C9 CC490001 
C0137EC2 CC490001 
C446843A CC490001 
C8538908 CC490001 
CC3F8D03 CC490001 
D00C9001 CC490001 
D3BC91D8 CC490001 
D75492F2 CC490001 
DAD5936A CC490001 
DE429359 CC490001 
E19E92D9 CC490001 
E4ED9201 CC490003 
EE7F8E6A CC490002 
F3FE8C1E CC490001 
F6638B4A CC490001 
F88B8ACF CC490001 
FA708AC5 CC490001 
FC138B46 CC490001 
FD6F8C6A CC490001 
FE848E18 CC490001 
FF4D9033 CC490001 
FFCA92A3 CC490001 
FFF8954E CC490001 
FFD3981C CC490001 
FF5B9AF4 CC490001 
FE8C9DBC CC490001 
FD64A05D CC490001 
FBE1A2BE CC490001 
FA00A4C5 CC490001 
F7BFA65A CC490001 
F51CA763 CC490001 
F1BAA7C9 CC490001 
ED72A773 CC490001 
E866A692 CC490001 
E2B7A544 CC490001 
DC86A3A6 CC490002 
CF259FED CC610002 
C14D9C4D CA060002 
B4079950 C1130002 
A63695CA ADB30002 
988A925C 8EE50001 
91E890FA 7F970001 
8B7D8FFB 70B20001 
85598F7E 61EA0001 
7F8B8FA0 52F40001 
7A22902C 43820001 
752D9105 33480002 
6C0B9363 12A00001 
67F494C8 069E0001 
6445963D 00080001 
611097B3 00EE0001 
5E67991A 0B660001 
5C5B9A63 21810001 
5AFD9BD0 45530001 
5A5F9D41 78EE0001 
5A939EAA AD940001 
5AF4A001 D6AC0001 
5B3DA139 F2A80001 
5B8BA247 FFF80001 
5BFDA321 FD0C0003 
5E3FA537 DA880001 
5F01A5CF D2090003 
6169A74A D28A0002 
62BCA808 D1BB0001 
6307A855 CC490000
```


When looking at this block in mot_em022 the first byte (with msb=0 or something like this) seems to have a special meaning but for some strange reason this doesn't apply to all datablocks. I could imagine that the 0x3 ubyte unknown determines the "type" of a datablock.

```
02 0033E4 80180FE7 
03 0013E5 9019CFE8 
07 FFE3E8 301C4FEC 
07 FF63EF 9021CFF5 
07 FEFFF8 2026CFFA 
05 FEC401 002ACFFB 
04 FEC406 F02C4FF9 
04 FEDC0A F02C0FF7 
04 FF080E 402A4FF5 
04 FF4410 B0270FF3 
05 FF8C12 10224FF3 
05 FFE812 F01B0FF3 
05 003413 00130FF3 
07 007012 300A4FF5 
07 008C10 1FFD8FF7 
06 006C0E 3FF04FF9 
07 00240D 1FE34FF8 
04 FF9C0C 7FD1CFF6 
04 FF400B 2FC94FF6 
03 FEE009 0FC2CFF5 
03 FEA006 CFC00FF5 
05 FE7803 DFC00FF6 
05 FE63FD BFC3CFF7 
07 FE83F7 4FC98FF6 
05 FEF3EE DFD40FF2 
04 FF5BE9 AFDD0FED 
03 FFB3E6 6FE48FE9 
04 FFF3E4 CFEA4FE7 
06 003FE3 BFF24FE6 
06 008FE2 FFFE8FE5 
06 00A7E2 8009CFE4 
04 0087E2 D0118FE4 
04 005BE3 60154FE5 
00 0033E4 80180FE7
```
For datablocks of this kind the second byte seems to be restricted to 0, FE or FF.

Looking at the anim at 0xC4F28 the 0xB datablocks don't seem to share this "special" first byte (msb=0, upper two or three bits=0, whatever):
10. 0xc5090
5 0 0 b 
-> 0xC8628

25. 0xc52ac
14 0 0 b 
-> 0xCD8D0 

26. 0xc52d0
15 0 0 b 
-> 0xCDC10
## Post #10
- Username: Scaatis5768
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jun 06, 2016 7:35 am
- Post datetime: 2016-07-10T00:24:37+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

I was thinking about from another angle: in the em001 file, I was able to get a pose (the initial pose?) from the animation. From the pose, it looks like the first animation is a) A shout. Every monster does one when it first spots you -> might be the first animation b) An idle animation or c) a walk cycle. Either way, I'm not expecting a great deal of rotation change from the root bone (bone 0). The data for that bone from the first animation is

```
starting at 0x1880: 0808743f 08080911 08081824 0808df15 0808f720 0808cf2b 08087400
```
I'm hoping to get some more info out of that data with this knowledge. By the way, this segment is 7x4=28 bytes long, one of the arguments against data being in 8 byte chunks, as the length of this is not a multiple of 8. Then again, the data might be in different formats for different bones.

I know there is also a sleeping animation. I found earlier it when going through animations to look at the initial poses. I will try and find it again later and maybe get some more from that.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2022-07-16T14:43:31+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

just relink of @Scaatis5768 script so we're not lost it
[MH3U_Model_importer.zip](https://xentaxbackup.github.io/file/22507_MH3U_Model_importer.zip)
## Post #12
- Username: felykiosa
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 31, 2018 6:54 pm
- Post datetime: 2022-08-17T15:23:34+00:00
- Post Title: Monster Hunter 3 Ultimate Animations/Animations in general

thx aslo I have a problem with the arctool I can't extract my .arc it always does a file in.000000 if you know the problem help me please .
