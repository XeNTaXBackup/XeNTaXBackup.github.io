## Post #1
- Username: ytrfamli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 4:23 pm
- Post datetime: 2010-10-29T12:19:34+00:00
- Post Title: CRC32 in Ogg pages...How?

Uh, this might seem a little dumb, but how is the CRC32 field in an Ogg page calculated, exactly?

I'm doing some simple research on the ogg format, and since the documentation from Xiph states that
"the CRC32 field is calculated with the field set to zero.", naturally, I'd want to verify it myself.

So I grabbed some random Ogg file from the net (see attatched) and opened it up in Hexworkshop...

Now, according to the documentation, the area with the yellow background is a single Ogg page,
and the highlighted area is the CRC32 field for that page.




So, following the description, I zero out the CRC32 field, highlight the whole page, 
click "Checksum", select "CRC(32 bit)", and finally, click "Generate", 




and voila!!!




I failed to get the correct CRC32 result.

Can someone help point out where I did wrong?

Note: 
The Ogg page I'm tempering with is composed of 2 headers (see the green line that divides the area),
The first is an ordinary Ogg page header, the second is the identification header.
I did try to calculate the CRC32 value of only the page header, but the result is still not right.
[Epoq.rar](https://xentaxbackup.github.io/file/3565_Epoq.rar)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-10-29T22:14:45+00:00
- Post Title: CRC32 in Ogg pages...How?

Hexworkshop uses the standard CRC32, Ogg uses a slightly simplified one (0 init and 0 final XOR, no reflections). Here's [a quick and dirty calculator](http://hcs64.com/files/oggcrc.zip), run like oggcrc.exe file.bin.
## Post #3
- Username: ytrfamli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 4:23 pm
- Post datetime: 2010-10-30T02:39:53+00:00
- Post Title: CRC32 in Ogg pages...How?

> Reply from hcs
>
> Hexworkshop uses the standard CRC32, Ogg uses a slightly simplified one (0 init and 0 final XOR, no reflections). Here's a quick and dirty calculator, run like oggcrc.exe file.bin.

Thank you so much, this worked like a charm! 
(I think you meant   crctest.exe file.bin  ,yes?)

Just wondering though, is there a way to make Hexworkshop reproduce this feat?

There's the Custom CRC (32 bit) option, but if I go like



OK...0 initial, 0 Xor, no reflection...



 
THIS IS GONNA WOR---
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-10-30T03:49:03+00:00
- Post Title: CRC32 in Ogg pages...How?

Weird... looks like it is doing CRC-16...
If you put in FFFFFFFF for the init and xor and switch on both reflections do you get the normal CRC-32 result?
Those low bytes are reversed because of the bit packing order Ogg uses, but I don't know where the high bytes went.
## Post #5
- Username: ytrfamli
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 27, 2010 4:23 pm
- Post datetime: 2010-10-30T05:43:13+00:00
- Post Title: CRC32 in Ogg pages...How?

> Reply from hcs
>
> Those low bytes are reversed because of the bit packing order Ogg uses, but I don't know where the high bytes went.
Yeah, I thought it's some endian issue...



> Reply from hcs
>
> Weird... looks like it is doing CRC-16...
If you put in FFFFFFFF for the init and xor and switch on both reflections do you get the normal CRC-32 result?
Seems like it then...this is the result of CRC32 and CustomCRC32 on the value 0x00,with FFFFFFFF in both init and xor, 
both refections switched on, polynomial 04C11DB7 (default setting of Custom CRC32):



I grabbed and older version of Hexworkshop and it didn't have the issue.

Maybe some part of my copy is corrupted...I'll try a fresh install.

Anyway, thanks! You've been most helpful!
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-11-05T15:48:56+00:00
- Post Title: CRC32 in Ogg pages...How?

I'm looking too a program to "fake" the bitrate, i have a ogg vorbis player but it checks the nominal bitrate i read this case too in hydrogenaudio, but i dont' know where to found a program to do this "hack".

In minds it's:

-I have a big ogg vorbis at 128kbs
-The player checks the nominal bitrate and if the vlaue it's bigger than 96 then the sound plays.

The idea it's create a:
-Program to fake the nominal bitrate in a low quality ogg vorbis, and compatible with the standard.
