## Post #1
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-06T09:44:08+00:00
- Post Title: MvC3 .DOM Model Format

[http://www.mediafire.com/?m3vql7k7pf7nqvm](http://www.mediafire.com/?m3vql7k7pf7nqvm)

The linked file is Spiderman's .DOM 3d model file.

Any info or help would be appreciated.
## Post #2
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-07T10:40:40+00:00
- Post Title: MvC3 .DOM Model Format

Out of curiosity, has anyone actually had a look at this file yet?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-07T10:43:06+00:00
- Post Title: MvC3 .DOM Model Format

I already pm'd you about this file type. All the main contibuters have looked at this and are stuck as i am. The format for the vertex points is simple the faces are not. If you can not read this simple model structure there is no way you could decode the faces.
## Post #4
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-09T23:51:44+00:00
- Post Title: MvC3 .DOM Model Format

So what is the approx 3.5k triangle list at the end of the file?
The values (big endian) suggest 4.8k vertices, which seem about right, it's what i'd look for in a simple format.
The 03 at the beginning of the list throws the list off by one so you might be loking at something other than pure triangles, triangle strips maybe.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-09T23:53:57+00:00
- Post Title: MvC3 .DOM Model Format

that is the problem the faces do not work and it is tri strip.
youll notice the stride in some models works fine mainly the helpers but the stride is off on all main characters and the faces do not work at all.
## Post #6
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-10T22:33:43+00:00
- Post Title: MvC3 .DOM Model Format

closer inspection shows if you start at the 03 (offset 609212 <- decimal) you run into triangles with repeated vertices,, same if you start with the 02 next to it.

Offsets for each 'triangle strip'?
That would account for the extra 2 bytes (1/3 of a triangle) if you jumped into the middle of the triangle data. And I know it sounds stupid, but maybe they needed to preserve some order to the triangles and not to the vertex data, for whatever daft reason.
Either that or they intentionally placed extra bytes in there to screw the order up.
Weirdness.!!!
## Post #7
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-04-10T22:59:17+00:00
- Post Title: MvC3 .DOM Model Format

There is associated data nearer the beginning of the file that matches the "index" data, it seems likely that it's used to decode and/or define run offsets and run lengths for the provided indices. However, I haven't been able to make any sense of it, without being able to debug the game. You can tell right off the bat that the raw indices do not cover the necessary range of vertices, though, regardless of how you treat them.
## Post #8
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-12T01:58:28+00:00
- Post Title: MvC3 .DOM Model Format

Looked at that data near the beginning, see what you mean.
Obviously not triangles then, can't see any 3D compression to them either.

```
102 - ??
34  - number of objects/bones??
12  there are 12 obvious names at offset 16080
12237  ???
10360   10360 vertex numbers for triangle data at end.
17762  ???
285392 - number of bytes in this data (no fixed length - ie NOT 20 bytes per field)
0
0
0
6
0
128     chunk? must be....
15888   nuffer chunk
16080   names? materials? 12 of these
17616   nuffer chunk
323820  chunk - 285392 bytes long (equal to last number in above data)                               
609212 triangle list thing = 20720 bytes or 10360 vertex numbers
```
## Post #9
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-12T09:27:43+00:00
- Post Title: MvC3 .DOM Model Format

ninja> i don't think mradult speak of thoses values , you are just giving the header values here ^^

also from my latest look on the mesh format it appears that it use morph targets on the charcter face, maybe also on some other parts so this may be a why we can't actually get the vertexcount to match the index count as a morph target use the same indices all the time ....

hope it can help
## Post #10
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-16T01:51:41+00:00
- Post Title: MvC3 .DOM Model Format

[http://www.mediafire.com/?c52lb7jkp4bgzsj](http://www.mediafire.com/?c52lb7jkp4bgzsj)

Well here is a dump of what I believe to be Spiderman's raw vertex and face data. How exactly do I read the vertices?
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-16T01:54:46+00:00
- Post Title: MvC3 .DOM Model Format

the verts are just signed short values
## Post #12
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-16T02:39:31+00:00
- Post Title: MvC3 .DOM Model Format

[http://www.mediafire.com/?lsx0me2msso13r3](http://www.mediafire.com/?lsx0me2msso13r3)

That is the new dump (including the vertex conversions). I'm not sure if I have the right data, the vert positions are so big :S
## Post #13
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-16T08:42:00+00:00
- Post Title: MvC3 .DOM Model Format

Getting somewhere now. Why aren't all the vertices in there though?
## Post #14
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-04-16T12:19:31+00:00
- Post Title: MvC3 .DOM Model Format

whoaaaaaaaaaa!!!!!! Very nice Vile!!!!!!!!!!!!
## Post #15
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-19T22:51:02+00:00
- Post Title: MvC3 .DOM Model Format

> Reply from VILE
>
> 
Getting somewhere now. Why aren't all the vertices in there though?

More than 34 objects?
or there are 34 objects and you haven't used the correct number of vertices?
(Your ankles end abruptly)

Also that 'face' data is unsigned shorts not bytes.
## Post #16
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-20T13:20:22+00:00
- Post Title: Re: MvC3 .DOM Model Format

> Reply from Ninja
>
> VILE wrote:
Getting somewhere now. Why aren't all the vertices in there though?

More than 34 objects?
or there are 34 objects and you haven't used the correct number of vertices?
(Your ankles end abruptly)

Also that 'face' data is unsigned shorts not bytes.

I used all the data in the header, should be correct (I'll still try and modify it). The indicies are read as unsigned shorts.
## Post #17
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-20T18:19:12+00:00
- Post Title: Re: MvC3 .DOM Model Format

Well the offset data in the 34 x 56_byte chunk all adds up, you got the correct number of vertices for that data.
Have you tried plotting the extra 4716 vertices? (they are all 24 byte length)

Also,
not sure I understand where your getting the 'face' data from, bytes 27 and 28 as the offset and bytes 31 and 32 as the data length ?????? (from the 56_byte data)
The bytes 31 and 32 represent number of values not length in bytes.
Even so, 8 values for 24 vertices, and 16 values for 56 vertices? :$
## Post #18
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-21T01:26:37+00:00
- Post Title: Re: MvC3 .DOM Model Format

> Reply from Ninja
>
> Well the offset data in the 34 x 56_byte chunk all adds up, you got the correct number of vertices for that data.
Have you tried plotting the extra 4716 vertices? (they are all 24 byte length)

Also,
not sure I understand where your getting the 'face' data from, bytes 27 and 28 as the offset and bytes 31 and 32 as the data length ?????? (from the 56_byte data)
The bytes 31 and 32 represent number of values not length in bytes.
Even so, 8 values for 24 vertices, and 16 values for 56 vertices? :$

In the object header blocks 0x18(4) is the offset relative to the indicies offset and 0x1C(4) is the indicies length.

It does look a little strange though.
## Post #19
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-21T16:07:48+00:00
- Post Title: Re: MvC3 .DOM Model Format

I'm starting to believe the faces are simple triangle indicies and the vertex order is off.
## Post #20
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-21T18:27:52+00:00
- Post Title: Re: MvC3 .DOM Model Format

It's a puzzle 
object 0 has 24 listed vertices, but only 8 unique vertices, the 'face' data values go up to 16....
However I did notice something fishy in the vertex data, if you look to the right of the number you dumped for the vertices, you see the last 2 values are always different for 'identical' vertices, so i'm wondering if they have split up the Significand and exponent?   
11245 0 2095 0 1 778 16191 16191 32639 -257  
11245 0 2095 0 1 778 16191 16191 32512 32767 
Would you still get a resemblance of spiderman if you only plotted the Significand portion as signed shorts?
Still doesn't solve the triangles issue, the number of vertices aren't always divisible by 3. (or 4 if it's quads)

data from offset 17616

```
      VV            field length VV    offset1          tri_offsets??                 object number
      VV                VV       VV       VV                VV    tri_len?                VV
1020 0018 07F000FF 8400 14 0D 00000000 00000000 0CB68010 00000000 00000018 00000000 0004 0012 0000000F 0CBBFF40 00000001 0CE0E780 
FFFF 0018 07F000FF 8400 18 0C 00000000 000001E0 14D4001D 00000018 00000008 00000000 0004 000B 00000005 0B516CA0 00000001 0B520B10 
1020 0038 001001FF 8400 14 0F 00000000 00000420 0CB68010 00000020 00000010 00000000 0002 000C 00000027 0B5CBAF0 00000001 0B520C30 
FFFF 015B 001001FF 8400 18 0E 00000000 00000880 14D4001D 00000030 00000160 00000000 0005 000D 00000157 0D12D0C0 00000001 0B7EB0B0 
1020 008D 001002FF 8400 14 0F 00000000 00002908 0CB68010 00000190 00000048 00000000 0015 000E 00010030 0CA6E950 00000001 0CE0E350 
FFFF 049A 001002FF 8400 18 0E 00000000 0000340C 14D4001D 000001D8 000004B8 00000000 001C 000F 00000340 0BD28ED0 00000001 0CE0E470 
1020 0038 001003FF 8400 14 0D 00000000 0000A27C 0CB68010 00000690 00000010 00000000 0002 0009 00000028 0B6814F0 00000001 0B520920 
FFFF 015B 001003FF 8400 18 0C 00000000 0000A6DC 14D4001D 000006A0 00000190 00000000 0005 0010 00000159 0B4A1750 00000001 0CE0E590 
1020 000C 001004FF 8400 14 0D 00000000 0000C764 0CB68010 00000830 00000008 00000000 0004 000A 0002000C 0C6D1070 00000001 0B5209F0 
FFFF 0203 001004FF 8400 18 0C 00000000 0000C854 14D4001D 00000838 00000278 00000000 0008 0003 00000201 0B68A5D0 00000001 0B5202A0 
FFFF 017F 001005FF 8400 18 0C 00000203 0000C854 14D4001D 00000AB0 000001A0 00000000 000B 0004 0203035B 0C6E2A40 00000001 0B5203C0 
1020 001C 001006FF 8400 14 0D 00000000 00011C84 0CB68010 00000C50 00000010 00000000 0005 0005 0001000A 0B3700B0 00000001 0B5204E0 
FFFF 0365 001006FF 8400 18 0C 00000000 00011EB4 14D4001D 00000C60 00000408 00000000 000B 0006 0000025B 0B7700B0 00000001 0B520600 
1020 008D 001007FF 8400 14 0D 00000000 0001702C 0CB68010 00001068 00000040 00000000 0015 0008 00000031 0B387890 00000001 0B520800 
FFFF 049B 001007FF 8400 18 0C 00000000 00017B30 14D4001D 000010A8 00000508 00000000 001C 0007 00000494 0B787890 00000001 0B520720 
1020 000C 001008FF 8400 14 0F 00000000 0001E9B8 0CB68010 000015B0 00000008 00000000 0004 0001 0000000E 0B1D4240 00000001 0B520060 
FFFF 0204 001008FF 8400 18 0E 00000000 0001EAA8 14D4001D 000015B8 00000290 00000000 0008 0002 00000203 0CE348F0 00000001 0B520180 
1020 0196 047009FF 8400 14 0D 00000000 00021B08 0CB68010 00001848 00000088 00000000 0001 0019 000400BA 0CBA97E0 00000001 0CE0EF20 
1020 019C 048009FF 8400 14 0D 00000196 00021B08 0CB68010 000018D0 00000088 00000000 0001 001B 01980251 0B659460 00000001 0CE0F110 
1020 017C 049009FF 8400 14 0D 00000332 00021B08 0CB68010 00001958 00000078 00000000 0001 001D 033303E8 0CA1B1A0 00000001 0CC8C2F0 
1020 0196 046009FF 8400 14 0D 000004AE 00021B08 0CB68010 000019D0 00000088 00000000 0013 001E 04B0056E 0C913690 00000001 0CC8C3D0 
FFFF 03C7 048009FF 8400 18 0C 00000000 00029858 14D4001D 00001A58 000002C8 00000000 0001 001C 000002E5 0B818A30 00000001 0CE0F230 
FFFF 03C8 047009FF 8400 18 0C 000003C7 00029858 14D4001D 00001D20 000002C8 00000000 0001 001F 03C7065E 0CB96070 00000001 0CC8C4F0 
FFFF 00D2 001009FF 8400 18 0C 0000078F 00029858 14D4001D 00001FE8 000000C0 00000000 0002 0020 078F07F5 0B1E5C60 00000001 0CC8C610 
FFFF 03D4 049009FF 8400 18 0C 00000861 00029858 14D4001D 000020A8 000002B8 00000000 0001 0021 08610B50 0CA07820 00000001 0CC8C730 
FFFF 03C8 046009FF 8400 18 0C 00000C35 00029858 14D4001D 00002360 000002C0 00000000 001A 0022 0C350F15 0C8FA460 00000001 0CC8C850 
FFFF 0059 04900AFF 8400 18 0E 00000FFD 00029858 14D4001D 00002620 00000048 00000000 0001 0013 0FFD1055 0CA2EB20 00000001 0CE0E8A0 
FFFF 0059 04600AFF 8400 18 0E 00001056 00029858 14D4001D 00002668 00000050 00000000 000A 0014 105610AE 0CDFA1B0 00000001 0CE0E9C0 
FFFF 0059 04800AFF 8400 18 0E 000010AF 00029858 14D4001D 000026B8 00000048 00000000 0001 0015 10AF1107 0B66CBA0 00000001 0CE0EAE0 
FFFF 0059 04700AFF 8400 18 0E 00001108 00029858 14D4001D 00002700 00000060 00000000 0001 001A 1108115F 0B7F6860 00000001 0CE0F040 
FFFF 0059 04600BFF 8400 18 0C 00001161 00029858 14D4001D 00002760 00000048 00000000 000A 0011 116111B9 0CE032A0 00000001 0CE0E6B0 
FFFF 0059 04700BFF 8400 18 0C 000011BA 00029858 14D4001D 000027A8 00000040 00000000 0001 0016 11BA1202 0B80F940 00000001 0CE0EC00 
FFFF 0059 04900BFF 8400 18 0C 00001213 00029858 14D4001D 000027E8 00000048 00000000 0001 0017 1213125C 0CC7CF60 00000001 0CE0ED20 
FFFF 0059 04800BFF 8400 18 0C 0000126C 00029858 14D4001D 00002830 00000048 00000000 0001 0018 126C12C3 0B675C90 00000001 0CE0EE40 

```
## Post #21
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-21T23:19:05+00:00
- Post Title: Re: MvC3 .DOM Model Format

Yeah, I checked all the vertex x,y,z values, couldn't find any with negative numbers.
My brain won't let me figure out if you'd be able to plot a near enough model using just the mantissa, guess it depends on the axis orientation.
It would explain the difficulty finding triangles.
24bit floats anyone?
## Post #22
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-22T01:34:55+00:00
- Post Title: Re: MvC3 .DOM Model Format

Nah I don't think they are 24bit floats, maybe these values "0CBBFF40 00000001 0CE0E780" have something to do with it. Possibly the vertices are meant to be put in a hash table?
## Post #23
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-22T18:39:09+00:00
- Post Title: Re: MvC3 .DOM Model Format

the dom files like on re5 pc and xbox version use the mesh boundingbox to repos the entire mesh vertices
## Post #24
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-22T21:32:55+00:00
- Post Title: Re: MvC3 .DOM Model Format

Posting the data for the first 2 objects using 3 bytes from the data instead of signed shorts.
To me that looks like 2 billboards reflected about an axis instead of being 2 boxes on top of each other(as you have them now)
I re-arranged object 1 vertex order to show that they match up.

```
7F2E16  FF0000  FE082F           7F2E16  3F0000  FE082F
7F2BED  FF0000  FE082F           7F2BED  3F0000  FE082F
7F2BED  FF0000  7F082F           7F2BED  3F0000  7F082F
7F2BED  FF0229  FE082F           7F2BED  3F0229  FE082F
002BED  FF0229  7F082F           002BED  3F0229  7F082F
002BED  FF0000  7F082F           002BED  3F0000  7F082F
7F2BED  FF0000  7F0606           7F2BED  3F0000  7F0606
002BED  FF0000  7F0606           002BED  3F0000  7F0606
7F2E16  FF0000  7F082F           7F2E16  3F0000  7F082F
FE2E16  FF0000  7F082F           FE2E16  3F0000  7F082F
7F2E16  FF0229  FE082F           7F2E16  3F0229  FE082F
FE2E16  FF0000  7F0606           FE2E16  3F0000  7F0606
7F2E16  FF0000  7F0606           7F2E16  3F0000  7F0606
FE2E16  FF0229  7F082F           FE2E16  3F0229  7F082F
7F2E16  FF0229  7F082F           7F2E16  3F0229  7F082F
7F2BED  FF0229  7F082F           7F2BED  3F0229  7F082F
7F2E16  FF0229  7F0606           7F2E16  3F0229  7F0606
FE2E16  FF0229  7F0606           FE2E16  3F0229  7F0606
7F2E16  FF0000  000606           7F2E16  3F0000  000606
7F2E16  FF0229  000606           7F2E16  3F0229  000606
7F2BED  FF0000  000606           7F2BED  3F0000  000606
7F2BED  FF0229  000606           7F2BED  3F0229  000606
002BED  FF0229  7F0606           002BED  3F0229  7F0606
7F2BED  FF0229  7F0606           7F2BED  3F0229  7F0606
```
## Post #25
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-23T01:56:55+00:00
- Post Title: Re: MvC3 .DOM Model Format

> Reply from Ninja
>
> Posting the data for the first 2 objects using 3 bytes from the data instead of signed shorts.
To me that looks like 2 billboards reflected about an axis instead of being 2 boxes on top of each other(as you have them now)
I re-arranged object 1 vertex order to show that they match up.
Code: Select all	   object_0				            object_1
7F2E16  FF0000  FE082F           7F2E16  3F0000  FE082F
7F2BED  FF0000  FE082F           7F2BED  3F0000  FE082F
7F2BED  FF0000  7F082F           7F2BED  3F0000  7F082F
7F2BED  FF0229  FE082F           7F2BED  3F0229  FE082F
002BED  FF0229  7F082F           002BED  3F0229  7F082F
002BED  FF0000  7F082F           002BED  3F0000  7F082F
7F2BED  FF0000  7F0606           7F2BED  3F0000  7F0606
002BED  FF0000  7F0606           002BED  3F0000  7F0606
7F2E16  FF0000  7F082F           7F2E16  3F0000  7F082F
FE2E16  FF0000  7F082F           FE2E16  3F0000  7F082F
7F2E16  FF0229  FE082F           7F2E16  3F0229  FE082F
FE2E16  FF0000  7F0606           FE2E16  3F0000  7F0606
7F2E16  FF0000  7F0606           7F2E16  3F0000  7F0606
FE2E16  FF0229  7F082F           FE2E16  3F0229  7F082F
7F2E16  FF0229  7F082F           7F2E16  3F0229  7F082F
7F2BED  FF0229  7F082F           7F2BED  3F0229  7F082F
7F2E16  FF0229  7F0606           7F2E16  3F0229  7F0606
FE2E16  FF0229  7F0606           FE2E16  3F0229  7F0606
7F2E16  FF0000  000606           7F2E16  3F0000  000606
7F2E16  FF0229  000606           7F2E16  3F0229  000606
7F2BED  FF0000  000606           7F2BED  3F0000  000606
7F2BED  FF0229  000606           7F2BED  3F0229  000606
002BED  FF0229  7F0606           002BED  3F0229  7F0606
7F2BED  FF0229  7F0606           7F2BED  3F0229  7F0606

I tried using 24bit integers, didn't seem to work.

This is a snippet of Hagger's pole vertex data (lol)

```
06 19 0C 99 73 29 00 01 9C B2 0F FF
04 11 0D 24 73 29 00 01 7F FE 7F FF
04 11 0D 24 73 29 00 01 7F BA 0F FF

```


06 19 0C 99 73 29 as the vertex positions make a lot more sense than 06 19 0C 99 73 29 00 01 BE.

I am pretty sure that it is the vertex order that is off and not the indicies.
## Post #26
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-04-23T17:53:49+00:00
- Post Title: Re: MvC3 .DOM Model Format

Your probably correct, the repeated vertices stop after the first few objects anyway.

You accounted for the 2 offsets in the indices? 
Have a look at offset 2 in the data i posted, the last offset is 0x126C with a length of 0x59 vertices, that's 4805 in decimal 
The tri data values go up to 4803.
Some of objects have their vertex count continue from the previous object.
object 11 vertex numbering starts at 515
You probably saw that already.
## Post #27
- Username: sidneymadmax
- Rank: beginner
- Number of posts: 35
- Joined date: Fri Sep 17, 2010 11:10 pm
- Post datetime: 2011-06-01T20:47:10+00:00
- Post Title: Re: MvC3 .DOM Model Format

I just downloaded the model of Felicia on a website! ( obj )
## Post #28
- Username: iK1L73r
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 08, 2011 6:21 am
- Post datetime: 2011-08-09T21:41:24+00:00
- Post Title: Re: MvC3 .DOM Model Format

i need wolverine's x360 .mod or arc please help me
