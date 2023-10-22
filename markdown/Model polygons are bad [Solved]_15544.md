## Post #1
- Username: lan1211
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 27, 2016 12:46 am
- Post datetime: 2016-11-26T17:40:39+00:00
- Post Title: Model polygons are bad? [Solved]

I'm writing a decompression algorithm binary format 3D model, but I have something does not work. For example, I unpacked the cube.

This block faces in file (HEX editor):
I came to the conclusion that something is wrong with the faces. Faces extraction code looks like this:


Thank You in advance for your help!
P.S sorry for my English)
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-11-26T18:36:48+00:00
- Post Title: Model polygons are bad? [Solved]

For the box you have 8 vertices, but your indices go up to 23, so that's probably not index data or there are more vertices.
## Post #3
- Username: lan1211
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 27, 2016 12:46 am
- Post datetime: 2016-11-27T07:20:54+00:00
- Post Title: Model polygons are bad? [Solved]

> Reply from Sir Kane
>
> For the box you have 8 vertices, but your indices go up to 23, so that's probably not index data or there are more vertices.

Yes, I know that there should be 24, but in front of the block with the vertices there is a block of 4 bytes, which indicates the number, there is number 8. Face correct, because in the file there are no more blocks, in which could be faces. I noticed that all the options vertices, which could be a cube (no repeated vertices), where present, so there is likely peaks are compressed to reduce the file size.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-11-27T09:53:58+00:00
- Post Title: Model polygons are bad? [Solved]

lan1211,

Nice to see my program (3D Object Converter) in work.

Which file format are you working on?
## Post #5
- Username: lan1211
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 27, 2016 12:46 am
- Post datetime: 2016-11-27T12:40:00+00:00
- Post Title: Model polygons are bad? [Solved]

> Reply from Karpati
>
> lan1211,

Nice to see my program (3D Object Converter) in work.

Which file format are you working on?

Zoltan,

I'm writing a program to extract the 3d model in the binary file format (.dobj v1) in the .x format (Direct X ASCII). 3D Object Converter I use to visually see the results.

By the way, I once wrote to you on your email about this file format DOBJ v1.
## Post #6
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-11-27T16:25:51+00:00
- Post Title: Model polygons are bad? [Solved]

Can you provide the box file?
## Post #7
- Username: lan1211
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 27, 2016 12:46 am
- Post datetime: 2016-11-29T11:10:05+00:00
- Post Title: Model polygons are bad? [Solved]

Problem Solved.
## Post #8
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2016-11-29T14:34:02+00:00
- Post Title: Model polygons are bad? [Solved]

Well, what was it?
## Post #9
- Username: lan1211
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 27, 2016 12:46 am
- Post datetime: 2016-11-29T18:17:25+00:00
- Post Title: Model polygons are bad? [Solved]

> Reply from Sir Kane
>
> Well, what was it?
Lossy compression, maps in other files:)
