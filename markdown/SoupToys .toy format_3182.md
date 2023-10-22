## Post #1
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2008-10-11T08:09:45+00:00
- Post Title: SoupToys .toy format

Hey. I've been playing this game [http://www.souptoys.com](http://www.souptoys.com), and have gotten considerably fed up with the "limit" of each toy available. 

Hopefully, the format isn't too hard.
(File format header: 883F0305)

(If you download it, the toy files can be found at C:\Documents and Settings\All Users\Application Data\Souptoys\Toys.
[toys_souplabs.zip](https://xentaxbackup.github.io/file/1682_toys_souplabs.zip)
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-16T02:11:57+00:00
- Post Title: SoupToys .toy format

Here is just a quick little bit of info about this format:

It starts out with a 76 byte header that doesn't seem to be part of the format, since all offsets are relative to the end of this header (so to get the real offset you need to add 76 to the value in the file). The file table is at the end of the file, even though there seems to be something at the beginning too. Everything is little-endian.

```
uint32 {4} - Offset to the end header (subtract 4, but also remember to add 76 to it!)

// The end header
uint32 {4} - Offset to the file table (remember to add 76 to it!)

// The file table
uint32 {4} - Number of files

// For each file
  uint32 {4} - Filename length
  char {x} - Filename
  uint32 {4} - Offset to the file data (remember to add 76 to it!)
  uint32 {4} - Extension length
  char {x} - Extension, although already specified in the filename
  uint32 {4} - Size of the file
```
## Post #3
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2008-10-18T06:24:29+00:00
- Post Title: SoupToys .toy format

Thanks for looking at it. So far it seems that it's some kind of archive file with AutoCAD 3d files in them?
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-20T01:22:48+00:00
- Post Title: SoupToys .toy format

> Reply from AngelSL
>
> Thanks for looking at it. So far it seems that it's some kind of archive file with AutoCAD 3d files in them?The file you posted is an archive, but there are no AutoCAD files in it. It looks like it has a few pictures, sound effects, and script files. An extractor for it would probably not be difficult to write.
## Post #5
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2008-10-21T06:49:00+00:00
- Post Title: SoupToys .toy format

I must be mistaken then. I hope to see an extractor soon, maybe even a repacker (okay I'm going way too far.. am I?)
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-28T15:48:11+00:00
- Post Title: SoupToys .toy format

> Reply from AngelSL
>
> I must be mistaken then. I hope to see an extractor soon, maybe even a repacker (okay I'm going way too far.. am I?)Good thing I held off on making an extractor... it looks the format is not what I thought it is (I downloaded the demo). A repacker would not be too difficult to make.
## Post #7
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-10-31T22:18:14+00:00
- Post Title: SoupToys .toy format

Just to mix things up a bit, here is a Game Extractor plugin to read this format. It's my first attempt at writing a Game Extractor plugin, so I may not have done things completely right. Just extract the ZIP into C:\Game Extractor\plugins.
[Plugin_TOY.zip](https://xentaxbackup.github.io/file/1710_Plugin_TOY.zip)
## Post #8
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2008-11-02T02:29:37+00:00
- Post Title: SoupToys .toy format

Thanks all. I'll look at the java source and try to reverse it (i.e repacker)
## Post #9
- Username: Snow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 02, 2008 11:51 pm
- Post datetime: 2008-11-02T20:01:18+00:00
- Post Title: SoupToys .toy format

Nice job, ill be sure to contribute what i understand, and if i can get a repack script together
## Post #10
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2008-11-03T07:23:56+00:00
- Post Title: SoupToys .toy format

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Snow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 02, 2008 11:51 pm
- Post datetime: 2008-11-10T05:25:29+00:00
- Post Title: SoupToys .toy format

My bad, i just have a mess of things, well thanks for the simplified versions
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-11-12T02:29:10+00:00
- Post Title: SoupToys .toy format

Looks neat, but yet I haven't gotten around to trying it!
