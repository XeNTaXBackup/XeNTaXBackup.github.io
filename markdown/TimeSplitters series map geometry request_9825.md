## Post #1
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-03T13:48:34+00:00
- Post Title: TimeSplitters series map geometry request

Hello there people. I would like to request reverse engineering on the TimeSplitters series level.raw files. TS1 and TS2 both use the same file format of .RAW and i think only use slight differences in format etc, altho i may be wrong.

I am willing to pay for services on this. I would like the maps to have UV coordinates and correct texture placement. I already have a texture converter for .RAW's and .QPM. So getting the textures are not a problem, i will share this tool with the community also.

The reason i need these is because i am making a full mod for UT2004 that has even picked up interest of Crytek members. It currently features 111 characters fully ripped from the original games and weapons are being worked on. We have a 38,000 people following and everyone would love for this to become a reality!

Video of some work: [http://www.youtube.com/watch?v=Zh_5u9n2fLc](http://www.youtube.com/watch?v=Zh_5u9n2fLc)

Please contact me if you are interested at - [Timesplitterstogmod@gmail.com](mailto:Timesplitterstogmod@gmail.com)

Thanks
## Post #2
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-06T18:00:18+00:00
- Post Title: TimeSplitters series map geometry request

Bump

Could i please get some help in here! i am not paying pennies for this.
## Post #3
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-11-06T19:32:02+00:00
- Post Title: TimeSplitters series map geometry request

Nobody of importance here cares about the money, so that's most likely not the reason why you haven't received a response yet.
Unless the money would be going to XeNTaX instead, to keep the site alive.
## Post #4
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-06T19:41:24+00:00
- Post Title: TimeSplitters series map geometry request

> Reply from Demonsangel
>
> Nobody of importance here cares about the money, so that's most likely not the reason why you haven't received a response yet.
Unless the money would be going to XeNTaX instead, to keep the site alive.

If that is what they would want, then that is what i could do.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-07T02:21:48+00:00
- Post Title: TimeSplitters series map geometry request

Post a screenshot of the top of the file in a hex editor.
## Post #6
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-07T02:43:35+00:00
- Post Title: TimeSplitters series map geometry request

[http://filesmelt.com/dl/Topline.jpg](http://filesmelt.com/dl/Topline.jpg)

There you go.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-07T02:44:22+00:00
- Post Title: TimeSplitters series map geometry request

Well at least it's not encrypted or compressed or anything.
Send me one of those.

You mentioned you were modding UT. Does this mean you are looking for a way to take these levels and load i there? If so, what kind of tools does UT have that would allow you to import/modify maps?
## Post #8
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-07T02:49:25+00:00
- Post Title: TimeSplitters series map geometry request

> Reply from finale00
>
> Well at least it's not encrypted or compressed or anything.
Send me one of those.

You mentioned you were modding UT. Does this mean you are looking for a way to take these levels and load i there? If so, what kind of tools does UT have that would allow you to import/modify maps?

I answered your question in PM, but ill post again here for anyone thats interested. UT takes .ASE as an import option, then i use the level as one big static mesh ( Its been tested and works fine ).
## Post #9
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-11-07T16:13:32+00:00
- Post Title: TimeSplitters series map geometry request

Can i see a sample? PM? Wanna have a quick look..
## Post #10
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-07T16:35:13+00:00
- Post Title: TimeSplitters series map geometry request

> Reply from C00L12345
>
> Can i see a sample? PM? Wanna have a quick look..

Sure, PM'd you now 

Here is the topline for TimeSplitters 1 : [http://filesmelt.com/dl/ToplineTS1.jpg](http://filesmelt.com/dl/ToplineTS1.jpg)

Tell me if its similar to TS2's raw format, because if it is, then surely it would not be too hard to get the levels from that game too?
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-10T05:33:08+00:00
- Post Title: TimeSplitters series map geometry request

Since it's a PS2 game there might be a bunch of opcodes that I am just treating as random hex data.

TS2 there are several .raw files (I don't know if this is how it is stored, or just given that extension based on some ripper). The first four bytes indicate what type of file it is

0x01 means it's a texture
0x10 means it's an object mesh
0x20 means it's a level mesh

The mesh formats are similar, however the level mesh has more sections and data.
However it is interesting to note that all meshes are ridiculously small, so I don't know if it's just because the quality sucks and everything just looks like a bunch of ugly polys, or they're using some way to efficiently store this information using PS2 hardware instructions.

I'm guessing the rest of the 3D models have their own format and is easy to tell apart from the raw's and that's why you never mentioned them.

I am just looking at the first section
First is the header

```
int32 headerSize
int32 datStart
int32 ?
int32 ? 
int32 ?
int32 ?
int32 ?

unk struct { // repeats until ID == -1, including the last struct with ID == -1
   int32 ID
   int32 ?
   int32 ?
   int32 ?
}

unk struct2 { // repeat until offset == datStart, which is given in the header
   int32 absolute_offset_to_something
   176 bytes
}

```


For each offset in struct2, if you seek to that offset, you should read an integer 1. This is the start of some chunk, probably a particular mesh. Seek to a couple offsets and you should observe the same pattern.

Ok so now you will go and read a bunch of integers. Not sure what they are, not sure how many there are or how they are determined, but they start at 0, bump up to some large integer, and then increase by 72 each time.

I would suspect that you keep reading integers until you read another 0, which you stop.
If you compare a couple files, you will notice that it is consistent pattern, and the arbitrary padding at the end of each section is just 16-byte alignment



These are images of the stuff starting at DatStart offset. You will see above that you start with a 0, and end with a 0. Below, you will start with a 0, end with a 0, but pad to 16-bytes.



Afterwards, you see some 16-byte structs. I don't know what they are.

For level32 and level33 if you search for the hex string

```

```


You will come up with a bunch of matches.
If you follow the offsets in struct2, you will notice that each of them reference one of these. However I don't know what any of the data means.

Btw, the image converter you sent creates PNG files not BMP. Don't know why the dev called them bmp's...
## Post #12
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-10T21:33:57+00:00
- Post Title: TimeSplitters series map geometry request

> Reply from finale00
>
> Since it's a PS2 game there might be a bunch of opcodes that I am just treating as random hex data.

TS2 there are several .raw files (I don't know if this is how it is stored, or just given that extension based on some ripper). The first four bytes indicate what type of file it is

0x01 means it's a texture
0x10 means it's an object mesh
0x20 means it's a level mesh

The mesh formats are similar, however the level mesh has more sections and data.
However it is interesting to note that all meshes are ridiculously small, so I don't know if it's just because the quality sucks and everything just looks like a bunch of ugly polys, or they're using some way to efficiently store this information using PS2 hardware instructions.

I'm guessing the rest of the 3D models have their own format and is easy to tell apart from the raw's and that's why you never mentioned them.

I am just looking at the first section
First is the header
Code: Select allint32 fmt // 0x20
int32 headerSize
int32 datStart
int32 ?
int32 ? 
int32 ?
int32 ?
int32 ?

unk struct { // repeats until ID == -1, including the last struct with ID == -1
   int32 ID
   int32 ?
   int32 ?
   int32 ?
}

unk struct2 { // repeat until offset == datStart, which is given in the header
   int32 absolute_offset_to_something
   176 bytes
}


For each offset in struct2, if you seek to that offset, you should read an integer 1. This is the start of some chunk, probably a particular mesh. Seek to a couple offsets and you should observe the same pattern.

Ok so now you will go and read a bunch of integers. Not sure what they are, not sure how many there are or how they are determined, but they start at 0, bump up to some large integer, and then increase by 72 each time.

I would suspect that you keep reading integers until you read another 0, which you stop.
If you compare a couple files, you will notice that it is consistent pattern, and the arbitrary padding at the end of each section is just 16-byte alignment



These are images of the stuff starting at DatStart offset. You will see above that you start with a 0, and end with a 0. Below, you will start with a 0, end with a 0, but pad to 16-bytes.



Afterwards, you see some 16-byte structs. I don't know what they are.

For level32 and level33 if you search for the hex string
Code: Select all01 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00


You will come up with a bunch of matches.
If you follow the offsets in struct2, you will notice that each of them reference one of these. However I don't know what any of the data means.

Btw, the image converter you sent creates PNG files not BMP. Don't know why the dev called them bmp's...

I can batch convert the PNG images into .DDS which is efficient for the Unreal Editor. And it will also use all alpha channels correctly then.

As for the actual info you have presented on the files, i have no comment since i have no experience in the matter. But hopefully someone else does?
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-11-10T21:51:59+00:00
- Post Title: TimeSplitters series map geometry request

You don't need experience to be able to parse a file; it's just reading a file.

I am simply trying to parse the file from top to bottom successfully. Pattern-matching is probably the easiest way to start if you have no idea what the data represents.
## Post #14
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-11-23T20:38:01+00:00
- Post Title: TimeSplitters series map geometry request

Still looking for help with this
## Post #15
- Username: Armus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat May 15, 2010 10:51 pm
- Post datetime: 2012-12-27T18:16:42+00:00
- Post Title: TimeSplitters series map geometry request

There's some info on Timesplitter 2 models on this wiki: [http://ps23dformat.wikispaces.com/Timesplitters+2](http://ps23dformat.wikispaces.com/Timesplitters+2)
## Post #16
- Username: CairnTrenz
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 03, 2012 8:18 pm
- Post datetime: 2012-12-29T23:37:02+00:00
- Post Title: Re: TimeSplitters series map geometry request

The glorious Chroxx has helped me with this format, he got out characters, objects and maps for me. Altho the levels still need to be pulled out with LOD
