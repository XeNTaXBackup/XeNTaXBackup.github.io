## Post #1
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2022-01-03T10:27:49+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

I found this description

```

HAnimAnimation chunk header (0x1B)
	RwInt32                     0x100
	RwInt32                     interpolation type id (1 = RpHAnimStd)
	RwInt32                     numFrames
	RwInt32                     flags
	RwReal                      duration
	numFrames*sizeof(keyFrame)  key frames

serialized format of RpHAnimStdKeyFrame:
	RwReal      time
	RtQuat      q     // quaternion describing rotation
	RwV3d       t     // position
	RwInt32     prev  // should be offset of previous key frame from beginning of frame data but appears to be junk

PS2 .ska (skeletal animation) are almost the same format.
They have no chunk header nor the first two ints (so a file starts at numFrames directly).
In key frames the time comes after t, not before q.
```

But this wrong.
My data is

```
03 11 00 00 74 00 00 00 00 00 00 00 89 88 88 3D 
C6 B4 96 BE 8D 33 DD BE 27 D1 91 BD 00 00 80 3F 
4E 4E 11 40 00 00 80 3F ...
```

where

```
3C 09 00 00 - size (without this header, after version) - 2364
65 00 02 1C - engine version 3.7.0.1
00 01 00 00 - Version: animation's version format (in all GTAs - 1.0 (0x100))
03 11 00 00 - Type: defines the frame format, 0x01 - normal,  0x02 - compressed, but what this (03 11) means?
74 00 00 00 - Frames: number of frames defined in the container - 116
00 00 00 00 - Flags
```

after follow 7 floats (28 bytes), unknown and numframes of char[8] + numframes of char[12] (you can clearly see the different structure of bytes in these 2 parts, and therefore divided), or just numframes of char[20].
if type 0x01 then 36 bytes per frame, if 0x02 then 22 bytes per frame, but i have only 20
File example in attachment
[PC_TG_LockOn_Idle.7z](https://xentaxbackup.github.io/file/21497_PC_TG_LockOn_Idle.7z)
## Post #2
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2022-01-06T20:18:36+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

I have completed the mesh exporter. [This](https://www19.zippyshare.com/v/itwpBmjY/file.html) mesh for animation (with skin and skeleton). Have 53 bones.

Found a pattern in anm files. After 7 unknown floats follow this struct

```
    int8_t un[4];
    float time;
};
```

always with zero float (time?) and their number equal to the number of bones. in all files



Screenshot_35.png (66.92 KiB) Viewed 177 times
## Post #3
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2022-01-08T11:46:41+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

Some new information.
Standard header, with new unknown field

```
    uint32_t version; //always 0x100, gta
    uint32_t type; //always 0x1103
    uint32_t count; //number of "packets"
    uint32_t flags; //always 0
    float length; //time length of animation
    float unknown[6];
};
```

Then 2 structures follow with number of number of packets each

```
    int8_t unknown[4];
    float time;
};
struct Data1{
    int8_t unknown[12];
};
```

Together

```
    uint32_t type; //0x1B anim animation
    uint32_t size;
    uint32_t version; //engine version 3.7.0.1
    Head head;
    Data0 data0[head.count];
    Data1 data1[head.count];
};
```

For now trying to understand the structure of data0. Unknown 4 bytes, then time goes by. First comes the number of structures with zero time equal to the number of bones. Then there are packets with other times, and there are as many packets with a finite time as there are bones, and there are no more intermediate ones than bones.
A few words about the unknown 4 bytes. Packets with zero time of the last bit always have 0x83 and one common penultimate, and all the others packets have two last bytes 0. At the same time, there are a lot of repetes.
Judging by the timestamps and the total animation time, the frame rate is always 30 fps. Time step always 0.0333.
I attach a longer and more understandable walk animation. 
It is necessary to understand the sequence of packets for each bone, to which bone these sequences belong and what information is in them. Although usually there should be translations (for skeletal I think it is not necessary) and rotations (usually in the form of quaternions)
PC in file names is Playable Character
[PC_TG_Walk.7z](https://xentaxbackup.github.io/file/21551_PC_TG_Walk.7z)
## Post #4
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2022-01-09T12:11:06+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

Found in the documentation words about the order of frames.

> The keyframe data does not contain an explicit link to the node it will be applied to. Instead, it is determined implicitly from the ordering of the keyframes in the array. For data cache coherence, the keyframes are sorted in time order.
>
> Each and every node has a keyframe at the beginning and end of the
>
> animation. Then there are optional additional keyframes in-between. The first keyframe is stored for each node in turn, then the second for each node in turn. These are used to initialize the first interpolation for each node.
>
> 
>
> An unordered array of keyframes may be sorted in a conventional way
>
> using the following as primary and secondary sort keys:
>
> 1. The time of the previous keyframe for the node
>
> 2. The node index

I have 53 bones (nodes) and frames (packets) ordered by this (hopefully right ) for PC_TG_LockOn_Idle.anm
format string: data0.unknown * data1.unknown  #  data0.unknown * data1.unknown  #

```
CC 41 38 83 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  
E0 41 38 83 * 7E EB A6 7D EB DF B3 49 90 9C 5C 18  #  24 04 00 00 * 7E EB A6 7D EB DF B3 49 90 9C 5C 18  #  
F4 41 38 83 * 80 00 88 7C FE 0F 5A 4B DE 2B 89 12  #  24 04 00 00 * 80 00 88 7C FE 0F 5A 4B DE 2B 89 12  #  
08 42 38 83 * 8D C6 78 6A CC 2F 21 64 5C 2C 3E 0F  #  24 04 00 00 * 8D C6 78 6A CC 2F 21 64 5C 2C 3E 0F  #  
1C 42 38 83 * 7E 14 D8 9D C6 CF 41 51 00 00 C2 15  #  24 04 00 00 * 7E 14 D8 9D C6 CF 41 51 00 00 C2 15  #  
30 42 38 83 * 79 F3 F7 7E FB 2F 41 50 7E 02 00 00  #  24 04 00 00 * 79 F3 F7 7E FB 2F 41 50 7E 02 00 00  #  
44 42 38 83 * 80 00 08 80 FF 0F 5A 4B EC 25 38 2E  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B EC 25 38 2E  #  
58 42 38 83 * 72 E8 45 84 AA CF 92 32 5C 2C 3E 0F  #  24 04 00 00 * 72 E8 45 84 AA CF 92 32 5C 2C 3E 0F  #  
6C 42 38 83 * 80 EF B7 97 DB FF 73 45 00 00 C2 15  #  24 04 00 00 * 80 EF B7 97 DB FF 73 45 00 00 C2 15  #  
80 42 38 83 * 8E 8B D7 6D D9 4F 72 46 7E 02 00 00  #  24 04 00 00 * 8E 8B D7 6D D9 4F 72 46 7E 02 00 00  #  
94 42 38 83 * 80 00 08 80 FF 0F 5A 4B EC 25 38 2E  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B EC 25 38 2E  #  
A8 42 38 83 * 7A 37 87 7E F3 DF 5A 4B EC 37 15 11  #  24 04 00 00 * 7A 37 87 7E F3 DF 5A 4B EC 37 15 11  #  
BC 42 38 83 * 7F 2B B7 8A EC CF 5A 4B C4 3E 52 10  #  24 04 00 00 * 7F 2B B7 8A EC CF 5A 4B C4 3E 52 10  #  20 03 00 00 * 7F 2B B7 8A EC CF 5A 4B C4 3E 52 10  #  
D0 42 38 83 * 80 2C 97 88 EF DF 5A 4B 73 42 0B 10  #  24 04 00 00 * 80 2C 97 88 EF DF 5A 4B 73 42 0B 10  #  20 03 00 00 * 80 2C 97 88 EF DF 5A 4B 73 42 0B 10  #  
E4 42 38 83 * 81 AC C7 85 FB 7F 5A 4B F2 3F 2E 0B  #  24 04 00 00 * 81 AC B7 85 FB 7F 5A 4B F2 3F 2E 0B  #  20 03 00 00 * 81 AC C7 85 FB 7F 5A 4B F2 3F 2E 0B  #  
F8 42 38 83 * 7E 94 E9 79 D4 CF C8 5D DD 32 A6 25  #  24 04 00 00 * 7E 94 E9 79 D4 DF C8 5D DD 32 A6 25  #  20 03 00 00 * 7E 94 E9 79 D4 CF C8 5D DD 32 A6 25  #  
0C 43 38 83 * 4E 06 18 5A F7 1E 1E 6C B1 30 33 04  #  24 04 00 00 * 4E 06 18 5A F7 1E 1E 6C B1 30 33 04  #  
20 43 38 83 * 73 89 31 7F A1 0C 08 96 D2 2F 63 0D  #  24 04 00 00 * 73 89 31 7F A1 0C 08 96 D2 2F 63 0D  #  
34 43 38 83 * 7B D1 97 7A FB BF D8 92 D0 2F FF 1B  #  24 04 00 00 * 7B D1 97 7A FB BF D8 92 D0 2F FF 1B  #  
48 43 38 83 * 58 8A 36 A5 15 3F 39 54 51 2F 39 1B  #  24 04 00 00 * 58 8A 36 A5 15 3F 39 54 51 2F 39 1B  #  
5C 43 38 83 * 8C 11 9A 8F 9E FF D0 57 05 32 03 10  #  24 04 00 00 * 8C 11 9A 8F 9E FF D0 57 05 32 03 10  #  
70 43 38 83 * 8B 00 08 80 F7 3F 16 5C B6 30 C3 10  #  24 04 00 00 * 8B 00 08 80 F7 3F 16 5C B6 30 C3 10  #  
84 43 38 83 * 7C 26 04 F0 21 B8 B0 55 27 31 58 17  #  24 04 00 00 * 7C 26 04 F0 21 B8 B0 55 27 31 58 17  #  
98 43 38 83 * 82 78 AA F9 F4 07 0A 54 B6 30 3A 12  #  24 04 00 00 * 82 78 AA F9 F4 07 0A 54 B6 30 3A 12  #  
AC 43 38 83 * 7C 30 64 F0 01 F8 26 53 B6 30 3A 12  #  24 04 00 00 * 7C 30 64 F0 01 F8 26 53 B6 30 3A 12  #  
C0 43 38 83 * 38 00 08 80 A0 6E AB 57 11 30 20 11  #  24 04 00 00 * 28 00 08 80 CF 3D AB 57 11 30 20 11  #  6C 02 00 00 * 1A 00 08 80 D8 4C AB 57 11 30 20 11  #  
D4 43 38 83 * 26 88 67 85 A8 2D DB 57 69 2F 21 11  #  24 04 00 00 * 2E 82 A7 81 27 BE DB 57 69 2F 21 11  #  6C 02 00 00 * 38 6F 17 7E 94 0E DB 57 69 2F 21 11  #  
E8 43 38 83 * 80 00 38 91 EC 0F 5A 4B FA 3D EB 18  #  24 04 00 00 * 80 00 38 91 EC 0F 5A 4B FA 3D EB 18  #  6C 02 00 00 * 80 00 38 91 EC 0F 5A 4B FA 3D EB 18  #  
FC 43 38 83 * 6D 77 7B 6F 0A FF 5A 4B 15 38 3E 16  #  24 04 00 00 * 6D 77 7B 6F 0A FF 5A 4B 15 38 3E 16  #  
10 44 38 83 * 7E 14 18 7E FE FF 6B 52 29 3A F7 26  #  24 04 00 00 * 7E 14 18 7E FE FF 6B 52 29 3A F7 26  #  
24 44 38 83 * 7E 14 18 7E FE FF 7F 42 DF 39 F2 26  #  24 04 00 00 * 7E 14 18 7E FE FF 7F 42 DF 39 F2 26  #  
38 44 38 83 * 6B 15 38 FE BA 87 EB 38 D0 32 AB 25  #  24 04 00 00 * 6B 13 38 FE BB 87 EB 38 D0 32 AB 25  #  30 02 00 00 * 6B 15 38 FE BA 87 EB 38 D0 32 AB 25  #  
4C 44 38 83 * 4A 85 75 8B CA AE 95 2A AF 30 37 20  #  24 04 00 00 * 4A 85 75 8B CA AE 95 2A AF 30 37 20  #  
60 44 38 83 * 88 9E 81 73 B9 1C 00 00 9A 31 11 17  #  24 04 00 00 * 88 9E 81 73 B9 1C 00 00 9A 31 11 17  #  
74 44 38 83 * 7C 52 67 7C F5 8F DB 03 9D 31 75 08  #  24 04 00 00 * 7C 52 67 7C F5 8F DB 03 9D 31 75 08  #  
88 44 38 83 * 9B 66 4F A4 0E 49 3D 44 0E 32 93 0A  #  24 04 00 00 * 9B 66 4F A4 0E 49 3D 44 0E 32 93 0A  #  
9C 44 38 83 * A7 49 B9 64 4B AF 5C 58 F7 31 A5 15  #  24 04 00 00 * A7 49 B9 64 4B AF 5C 58 F7 31 A5 15  #  E0 01 00 00 * A7 49 B9 64 4B AF 5C 58 F7 31 A5 15  #  
B0 44 38 83 * 67 00 08 80 D9 BF 9D 3A B6 30 B0 13  #  24 04 00 00 * 67 00 08 80 D9 BF 9D 3A B6 30 B0 13  #  
C4 44 38 83 * 8C 8D FE C6 2A D7 54 42 17 32 13 0C  #  24 04 00 00 * 8C 8D FE C6 2A D7 54 42 17 32 13 0C  #  
D8 44 38 83 * E2 3A 88 66 E1 0C D9 54 B8 30 BA 14  #  24 04 00 00 * E2 3A 88 66 E1 0C D9 54 B8 30 BA 14  #  
EC 44 38 83 * CB 47 28 66 3D 8E 88 52 B8 30 2F 14  #  24 04 00 00 * CB 47 28 66 3D 8E 88 52 B8 30 2F 14  #  
00 45 38 83 * 5D 49 59 F9 7B E8 76 45 59 36 6F 10  #  24 04 00 00 * 5D 49 59 F9 7B E8 76 45 59 36 6F 10  #  
14 45 38 83 * 31 7D 18 76 42 7E 08 3F 5C 31 53 13  #  24 04 00 00 * 2C 3E D8 7B 0A 6E 08 3F 5C 31 53 13  #  7C 01 00 00 * 27 F8 27 81 C9 CD 08 3F 5C 31 53 13  #  
28 45 38 83 * 2D 00 08 80 20 DE D8 3E 03 32 52 13  #  24 04 00 00 * 1E 00 08 80 2E 9D D8 3E 03 32 52 13  #  
3C 45 38 83 * 80 00 38 96 DF 0F 95 6A 0B 29 56 4C  #  24 04 00 00 * 80 00 38 96 DF 0F 95 6A 0B 29 56 4C  #  
50 45 38 83 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  
64 45 38 83 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  
78 45 38 83 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  
8C 45 38 83 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B B6 30 3A 12  #  
A0 45 38 83 * 80 00 08 80 FF 0F 5A 4B FE FF EA 17  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B FE FF EA 17  #  
B4 45 38 83 * 80 00 08 80 FF 0F 5A 4B BB 3B 9E 12  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B BB 3B 9E 12  #  
C8 45 38 83 * 80 00 08 80 FF 0F 5A 4B 3A EC A4 14  #  24 04 00 00 * 80 00 08 80 FF 0F 5A 4B 3A EC A4 14  # 
```

it turns out 12 bytes per frame, not counting the first 4. it remains to understand how to decrypt them
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-09T12:35:32+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

If you have 6 bytes for translation and 6 bytes for rotation "League of legends" comes into my mind
and fatduck's quatDecompress(). Just as a thought, not checked...
## Post #6
- Username: alecss131
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 10, 2016 3:49 pm
- Post datetime: 2022-01-10T07:35:28+00:00
- Post Title: Skeletal animations from .anm file (renderware ps2)

This code?

```
  tmp0= s0>>15 
  tmp1= (s1*2+tmp0) & 0x7FFF
  s0= s0 & 0x7FFF ;
  tmp2= s2*4 ;
  tmp2= (s2*4+ (s1>>14)) & 0x7FFF ;
  s1= tmp1 ;
  AxisFlag= s2>>13 ;
  s2= tmp2 ;
  f0 = 1.41421*(s0-0x3FFF)/0x7FFF ;
  f1 = 1.41421*(s1-0x3FFF)/0x7FFF ;
  f2 = 1.41421*(s2-0x3FFF)/0x7FFF ;  
  f3 = sqrt(1.0-(f0*f0+f1*f1+f2*f2))
  if AxisFlag==3:x= f2;y= f1;z= f0;w= f3
  if AxisFlag==2:x= f2;y= f1;z= f3;w= f0
  if AxisFlag==1:x= f2;y= f3;z= f1;w= f0
  if AxisFlag==0:x= f3;y= f2;z= f1;w= f0
  return x,y,z,w  
```

I got weird numbers, none of the bones have zero rotations.
And I also don’t understand why skeletal animation have tranlation when bones can only rotate.
The engine has compressed floats, to uint16. My founded code (from maxscript), and not work for me

```
    (
        local floatInt = bit.shift (bit.and compressed 0x8000) 16
        if ((bit.and compressed 0x7fff) != 0) then
        (
            floatInt = bit.or floatInt ((bit.shift (bit.and compressed 0x7800) 12) + 0x38000000)
            floatInt = bit.or floatInt (bit.shift (bit.and compressed 0x07ff) 12)
        )

        bit.intasfloat floatInt
    ),
```

The engine is highly modifiable and can have anything. For example, bone indices were packed into their respective weights (uint8 into float). Code for unpack

```
    uint32_t tmp{bit_cast<uint32_t>(in)};
    uint8_t out{static_cast<uint8_t>(tmp >> 2)};
    if (out > 0) out--;
    return out;
}
```

Another finding of a pattern. The first byte in data0.unknown usually has the form X0, X4, X8 or XC, that is, the last 2 bits are always 0. But this numbers with >>2 bigger then number of bones.
Indices in delta morph has RLE compression. Or some files in Sonic Heroes have PRS compression. In my game files in archive use zlib compression.
