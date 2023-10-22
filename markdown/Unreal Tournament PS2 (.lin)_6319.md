## Post #1
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2011-03-29T02:49:16+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Hi, I was wondering if somebody could look at this *.lin file from the PS2 version of Unreal Tournament. I believe this archive contains *.u, *.int, *.uax, *.unr, and *.utx files, which are system (for both *.u and *.int), sound, map, and texture files, respectively. The full archive is somewhat large, so I used Watto's file cutter. 

The archive can be downloaded [here](http://www.mediafire.com/?l2l5j3phzt6b6f4).
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-03-30T06:57:49+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Made a topic regarding this here:
[viewtopic.php?f=21&t=6198](http://forum.xentax.com/viewtopic.php?f=21&t=6198)

It is a compressed container. Possibly zlib-type compression. They are used to compress everything.

Just need somebody to make a decompressor/extractor for ir
## Post #3
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2013-11-02T18:33:23+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Sorry for the huge bump, but I've been looking at this stuff again. It seems that, unlike normal Unreal packages, the *.lin packages have multiple name tables (and maybe multiple import/export tables). Maybe it would be possible for the packages to be read by the PC version of UT by cutting out everything that isn't relevant to a specific table. I really wish I knew more about this stuff.
## Post #4
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-03T13:41:02+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

the *.lin are multipart zlib compressed archives.

i looked at the ones from magna carta PS2 and in this particular game they're built as follows.

0x00: unknown string (it's always 0060 0000)
0x04: address of next compressed block (relative to data start (0x08))
0x08: zLib signature (SIG=7801)

example, if the value at 0x04 is 0000 4500, you will find a new header similar to 0x00 from 0x4508 (0x4508 = 0060 0000 / 0x450C = address of 3rd compressed block // 0x4510 = 7801 (zLib signature))
## Post #5
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2013-11-04T14:55:21+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Thanks for the information. The UT PS2 *.lins are sort of different from those that you described, but the zlib signatures seem to be there. 0x00 is always 7E 5D CF 15, followed by the name of the *.lin file, and then the standard Unreal name table. I'm seeing three different zlib signatures (78 01, 78 9C, 78 DA) in different places. Are the Magna Carta *.lin files are the same way?
## Post #6
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-04T16:31:47+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

old post trashed !!!

i had a script written for me to unpack one of these .lin archives and it seems it's build as follows:

0x00: Uncompressed segment size
0x04: Compressed Segment size
0x08: zlib signature 

in the case of magna carta:
the outputted pieces are all 0x6000 in size when decompressed. (see 0x00)
it's a single file split into 0x6000 bytes, pieces are then individually compressed, and header with above data given to each segment, then all segments are merged together.

i should have a tool for this fileformat written shortly, 

edit #1489074
fixed above data (uncompressed size)

an experimental tool for unpacking these can be found from [Here](http://mce.do.am/forum/25-44-1)
no filename support or support for repacking .lin yet.

hoping to have that done shortly, or less shortly, I've been rather busy with my own research regarding Utawarerumono as of late x.x
## Post #7
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2013-11-07T02:38:52+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Thanks! I wasn't able to get your tool to work for either UT or Unreal Championship 2 (just to try another *.lin format), but it works perfectly for Magna Carta. It seems that UT's *.lin files are more similar to Magna Carta's decompressed files than its compressed *.lin files.
## Post #8
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-07T05:52:36+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

could you drop me an example file or 2 ?

i'd like to take a closer look at one
## Post #9
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2013-11-07T12:05:51+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Sure, I'll send you a PM.
## Post #10
- Username: mugi
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Mar 24, 2011 3:02 am
- Post datetime: 2013-11-07T19:00:30+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

i looked at this for a little but not making much of sense yet.


no idea for the header bytes yet, but the structure of the file table seems as follows:

red byte: size of filename
blue bytes: filename
green bytes: 0xC string of values, it seems that 3 values is written here.

```
0000 0000 0C76 8C01 0000 0000

system/core.u
0C76 8C01 B5E3 0000 0000 0000

system/editor.u
C159 8D01 A0DF 0100 0000 0000

```


i dont really know what the values are yet, but it seems that for the first entry, the first value is 0000 0000 and second is 0C76 8C01
for the second file, the first value is ( 0000 0000 + 0C76 8C01 ) and second is B5E3 0000
and for the 3rd the first value is ( 0C76 8C01 + B5E3 0000 ) and second value is A0DF 0100

this leads me to believe that the first value is indeed a file start address and second value  is file size, however, values this large make no sense as they are way too big for this particular file.
(filesize is 0x4C51E0)

i'd love to examine this more but unfortunately im low on time, need to work on my own projects too 
hope you'll get something out of it~
## Post #11
- Username: AlCapowned
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jul 10, 2010 11:20 pm
- Post datetime: 2013-11-07T20:57:57+00:00
- Post Title: Unreal Tournament PS2 (*.lin)

Thanks, I appreciate your efforts.
