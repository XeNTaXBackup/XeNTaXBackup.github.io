## Post #1
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-04-21T21:10:40+00:00
- Post Title: Haunting Ground Vertexes

I'm having a hard time, figuring out the format of the vertexes. I'm now thinking that they might be half-floats instead of signed integers, what do you guys think?
Here is a sample file:
[http://ps23dformat.wikispaces.com/file/view/FIW_000.PCK](http://ps23dformat.wikispaces.com/file/view/FIW_000.PCK)
Here is what I know about the format:
4ByteInteger#ofFiles
{FirstFileOffset,SecondFileOffset,....}
The first file takes to the mesh (other ones take you to animatios), which begins at offset 0x20
Then at offset 0x24 it takes you to the data section (relative to offset 0x20),
so in this case: 0x20+0x1580=0x15A0
There are 0x1B subsections and the first one begins at offset 0x15B0
The 48Byte Header is:
{4ByteInteger#ofVertexes,4ByteOffset:VertexSection,4ByteOffset:TextureMappingSection,4ByteOffset:NormalMappingSection,4ByteOffset:UnknownSection#1 ,4ByteOffset:UnknownSection#2,4ByteOffset:TriStripInfoSection,4ByteInteger,4ByteInteger,4ByteInteger,4ByteOffset:BaseSection,4ByteInteger} Relative to the start of the header so in this case there are 0x34 Vertexes and they begin 0x10+0x15B0+0x520=0x1AE0
Here are the vertexes that I need to convert, but I don't see their format:

```
E2 00 DA 00 DD 00 
DE FF EC 00 5D FD 
A9 00 8E 00 03 01 
B8 00 8B 00 E4 FD 
41 00 0E 00 83 01 
75 01 F2 FF 7D FE 
BF FF 0E 00 83 01 
A2 01 D9 FE 96 FF 
57 FF 8E 00 03 01 
6A 01 AC FD C3 00 
1D FF DA 00 DD 00 
9F 00 5F FD E9 00 
26 FF 4A 01 64 00 
2E FF 93 FD E2 00 
AA FF BF 01 D6 FF 
3C FE 41 FE 2A 00 
56 00 BF 01 D6 FF 
FE FD 64 FF E4 FE 
DA 00 4A 01 64 00 
E3 FE 7D 00 D6 FD 
E2 00 DA 00 DD 00 
F9 03 A9 FE 4D 01 
3B 00 57 01 B3 FE 
28 FF 61 00 5F 00 
72 FF 1C 01 BD FE 
98 FE 00 00 00 00 
4E 01 96 00 AB FE 
CC FE 00 00 00 00 
00 00 00 00 00 00 
07 FF 67 FF 99 00 
DF 00 03 00 BC 00 
73 FF E4 FE 43 01 
83 02 00 00 00 00 
72 FF F2 FE 0E 01 
2B 01 56 FF E0 FF 
D8 FE 52 FF B8 00 
B6 FD 7F 03 5B FC 
79 FF 86 FE A0 01 
D9 00 61 00 5F 00 
8D 00 F2 FE 0E 01 
68 01 00 00 00 00 
95 FE A8 FE 98 00 
6E 01 00 00 00 00 
92 FE 00 00 00 00 
03 00 58 01 68 FF 
D5 FE 56 FF E0 FF 
C5 FF 57 01 B3 FE 
B4 02 13 02 C7 FD 
1A 00 6A FF 55 01 
DF 00 FD FF 44 FF 
87 00 86 FE A0 01
```

Here is my current QuickBMS script:
[http://ps23dformat.wikispaces.com/file/ ... unting.bms](http://ps23dformat.wikispaces.com/file/view/Haunting.bms)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-22T08:55:18+00:00
- Post Title: Haunting Ground Vertexes

> Reply from FurryFan
>
> I'm having a hard time, figuring out the format of the vertexes. I'm now thinking that they might be half-floats instead of signed integers, what do you guys think?I've left the path of wild guessing...
I'd a look at the 5.3ds file which was created by the bms script. Vertices chunk id (4110) and the vertex count (0x020D=525)
seem to be correct but the resulting obj file not. The assumed floats contain too many zeroes (red underlining) so they might be a combination of a word ID and a half float.



Haunting_5_3ds.JPG (66.97 KiB) Viewed 280 times


I'm a little bit tired of reading scripts using nonsense variable names such as tigertigertigerface
but if you told me from which address in the FIW_000.pck the above mentioned Chunk ID and the vertex count were extracted from I'd give it another try.

(You could go through the bms script inserting print commands as a debug help.
for example:

print "number of vertices: %vertexNumber%"

For v = 1 To vertexNumber ;
 print "vertex-addr: %werefox%"
 GoTo werefox 0 ;
)
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-04-22T18:23:08+00:00
- Post Title: Haunting Ground Vertexes

I made a cleaner version of the script with real variable names here:
[http://ps23dformat.wikispaces.com/file/ ... pdated.bms](http://ps23dformat.wikispaces.com/file/view/Haunting_updated.bms)
But I thank you got confused by looking at the outputted 3ds files. There are lots of zeros because the game uses what I think are 2ByteSigned Integers for the vertexes, which I change to Floats to used in the .3ds files. My script attempts to convert the meshes into .3ds format meshes, there are no .3ds files in the Haunting Ground files, thus the "Vertices chunk id (4110)" only exists in the output files and not in the original input. The vertexes for mesh5 begin at offset 0x00002540 in FIW_000.PCK and there are 0x020D =525 vertexes. The question is what format are the vertexes in, because assuming 2byteSigned vertexes and converting them to floats only yields unrecognizable objects.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-22T20:02:35+00:00
- Post Title: Haunting Ground Vertexes

> Reply from FurryFan
>
> I made a cleaner version of the script with real variable namesyeah, that's better (and bigger  ) thx.

> The question is what format are the vertexes in, because assuming 2byteSigned vertexes and converting them to floats only yields unrecognizable objects.yep. This point cloud looks interesting, though:



Haunting_0x2540.JPG (40.3 KiB) Viewed 266 times
## Post #5
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-04-22T22:53:50+00:00
- Post Title: Haunting Ground Vertexes

So shakotay2, what do you think it is then if it is not 2Byte Signed?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-23T05:34:17+00:00
- Post Title: Haunting Ground Vertexes

I didn't say that it's not signed short. As you can see the above point cloud is drawn using them.

Here's another promissing structure using "ShortAll" (signed):



FIW_000.JPG (28.42 KiB) Viewed 251 times
## Post #7
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-04-23T13:28:23+00:00
- Post Title: Haunting Ground Vertexes

> Reply from shakotay2
>
> I didn't say that it's not signed short. As you can see the above point cloud is drawn using them.

Here's another promissing structure using "ShortAll" (signed):
FIW_000.JPG
Is "shortall signed" the same as 2ByteSigned? Also I don't understand how someimtes you get meshes that look like nothing (in your first point), but other times look like something like in your last post.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-23T15:52:54+00:00
- Post Title: Haunting Ground Vertexes

> Reply from FurryFan
>
> Is "shortall signed" the same as 2ByteSigned?should be. The scaling/dividing factor may be different.

> Also I don't understand how someimtes you get meshes that look like nothing (in your first point), but other times look like something like in your last post.Don't understand it, too. Haunting_5_3ds.JPG just shows what your script extracts from FIW_000.pck. Or did you get another result?
## Post #9
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2015-04-23T21:28:23+00:00
- Post Title: Haunting Ground Vertexes

> Reply from shakotay2
>
> FurryFan wrote:Is "shortall signed" the same as 2ByteSigned?should be. The scaling/dividing factor may be different.
Also I don't understand how someimtes you get meshes that look like nothing (in your first point), but other times look like something like in your last post.Don't understand it, too. Haunting_5_3ds.JPG just shows what your script extracts from FIW_000.pck. Or did you get another result?
That's what I get too, even though it should be a normal mesh. What am I doing wrong?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-24T06:41:28+00:00
- Post Title: Haunting Ground Vertexes

dunno, You might read the Wild Arms 3 thread where meshes were extracted correctly (more or less).
Maybe it's similar.
