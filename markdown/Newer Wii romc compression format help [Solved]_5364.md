## Post #1
- Username: Redead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2010 9:49 pm
- Post datetime: 2010-11-07T21:21:57+00:00
- Post Title: Newer Wii romc compression format help [Solved]

I no longer need help decompressing the Super Smash Bros. romc file. Thank you hcs.

sample file (Super Smash Bros.
Link removed

Something interesting, the US version of Mario Party 2 looks a bit different than srcorsario's Japanese one.
Link removed
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-11-08T19:10:54+00:00
- Post Title: Newer Wii romc compression format help [Solved]

Yeah this has definitely got some Huffman coding going on, just look at the 55s at the end.
I'm reluctant to try applying Okumura's LZHUF stuff to this directly, though (and I did make an initial attempt, after correcting for variable size assumptions) as it seems more likely that the tables are stored in the file itself, as in lzh8 (which I also tried to fit this into, unsuccessfully).
As they say, when all you have is a hammer... I'm going to try digging into the binary, maybe I'll have luck again.

[edit] a quick (5 hour) scan of several versions didn't get me anywhere closer to finding the romc decompression routines, sorry.
## Post #3
- Username: Redead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2010 9:49 pm
- Post datetime: 2010-11-09T00:19:23+00:00
- Post Title: Newer Wii romc compression format help [Solved]

That's okay, thanks a lot for trying.
## Post #4
- Username: srcorsario
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Aug 16, 2010 11:08 pm
- Post datetime: 2010-11-20T20:08:33+00:00
- Post Title: Newer Wii romc compression format help [Solved]

I m looking for a de/compressor as well...

I got Mario Party 2 (japo version) and insite i found a romc file.

When i tried to decompres with Jurai program i got something extrange... I dont know if it could help. I got a file with the original rom size!!  (33.554.432 bytes) however its not a valid N64.

In case could help thats the romc file from Mario Party 2:
[http://uppit.com/6f9ckdjtg9co/romc.rar](http://uppit.com/6f9ckdjtg9co/romc.rar)


Thanks in advance
## Post #5
- Username: Redead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2010 9:49 pm
- Post datetime: 2010-11-28T22:53:52+00:00
- Post Title: Newer Wii romc compression format help [Solved]

> Reply from srcorsario
>
> I m looking for a de/compressor as well...

I got Mario Party 2 (japo version) and insite i found a romc file.

When i tried to decompres with Jurai program i got something extrange... I dont know if it could help. I got a file with the original rom size!!  (33.554.432 bytes) however its not a valid N64.

You get the original file size because Jurai's decompresser takes the first byte in the case of Mario Party 2 it is 0x08 and multiplies it by 4194304. That gives you the value of  33.554.432 bytes. It works the same for all versions of romc that I've seen, however, the actual compression/decompression algorithms are different.
## Post #6
- Username: Redead
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 06, 2010 9:49 pm
- Post datetime: 2010-12-05T05:37:26+00:00
- Post Title: Newer Wii romc compression format help [Solved]

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-01-13T14:16:11+00:00
- Post Title: Newer Wii romc compression format help [Solved]

Not sure how much help this will be, but I've been successful at parsing through the three different versions of the Smash Bros. romc.  It seems that there is a segment for each 0x10000 bytes of the source file.

Just the source for further investigation: [http://hcs64.com/files/romchuf00.zip](http://hcs64.com/files/romchuf00.zip)

All I can do right now is read the very minimal header for each segment, in order to skip it to get on to the next one.

[edit] Interesting note, I've discovered the "store" mode block mechanism, we could probably use this to trivially create files of this type if we wanted.
[edit2] A more correct header parsing: [http://hcs64.com/files/romchu01.zip](http://hcs64.com/files/romchu01.zip)
[edit3] Identified two tables and a body in each block, but doesn't seem to be the same table format as in huf8 and lzh8. [http://hcs64.com/files/romchu02.zip](http://hcs64.com/files/romchu02.zip)
[edit4] Found the decompressor, 8006B9A0 in the europe ssb vc wad.  I'll try to keep quiet until I have it worked out now
## Post #8
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-01-14T21:21:35+00:00
- Post Title: Newer Wii romc compression format help [Solved]

Here's a decompressor: [http://hcs64.com/files/romchu03.zip](http://hcs64.com/files/romchu03.zip)
## Post #9
- Username: Plombo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 18, 2010 11:27 am
- Post datetime: 2011-01-17T19:43:45+00:00
- Post Title: Newer Wii romc compression format help [Solved]

> Reply from hcs
>
> Here's a decompressor: http://hcs64.com/files/romchu03.zip

Okay, you rock!  Just I was putting the finishing touches on my software to extract console ROMs from Wii NAND dumps, you came along and released a working decompressor for the one ROM it couldn't extract!  Thank you so much!

While you're here, I have some questions for you:

What Virtual Console game(s) use LZH8, and what files is it used to compress?
I've translated the puff8 source code to Python, and plan to do the same for lzh8_dec and romchu.  Is it okay with you if I release my Python versions under the GPL as part of the software project I mentioned above?
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-01-17T20:15:55+00:00
- Post Title: Newer Wii romc compression format help [Solved]

I've seen LZH8 used on some SNES VC titles, and their PCM things and emanuals.  The files I've tested with are from Der Langrisser, Uncharted Waters: New Horizons, Ogre Battle: March of the Black Queen, Bahamut Lagoon, Genghis Khan II: Clan of the Gray Wolf, and the Super Mario Collection disc.

You should know that the Huf8 format is widely supported by other compressors and decompressors, for instance [http://code.google.com/p/dsdecmp/](http://code.google.com/p/dsdecmp/) . It's from a family of compressions used clear back to GBA BIOS. LZH8 is a member of that family as well (type 0x40 as opposed to 0x28 and 0x24 for Huf8 and Huf4, 0x11 for LZSS, 0x10 for LZ77, 0x30 for RLE), though afaik it is newly introduced with the Wii.

romc is a family of compressions as well, type 0x01 is the LZ77 one that the old romc tools supported, type 0x02 is the lz77+huffman one that romchu supports, and there is a type 0x03 in the code but I haven't seen it used yet so I didn't bother reversing it.  I've seen the type 0x02 on all regions of Super Smash Bros, as well as Mario Party 2 Japanese and US (as noted in this thread).

I look forward to seeing the all-inclusive decompressor, feel free to refer to my code, as that's what it's there for!

[edit] And just for the heck of it, here's 0.4 with some comment cleanup and "public domain" explicitly stamped on it: [http://hcs64.com/files/romchu04.zip](http://hcs64.com/files/romchu04.zip)
[edit2] And 0.5 with a piddling little bug fix for bounds checking: [http://hcs64.com/files/romchu05.zip](http://hcs64.com/files/romchu05.zip)
## Post #11
- Username: Plombo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 18, 2010 11:27 am
- Post datetime: 2011-01-19T22:14:00+00:00
- Post Title: Newer Wii romc compression format help [Solved]

Thanks.  Do you know what compression is used for the Super Smash Bros. manual?
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-01-20T05:33:01+00:00
- Post Title: Newer Wii romc compression format help [Solved]

Same scheme as the romc, but different header format.

First 30 bits are compressed size, next two bits are compression type (2 here).  Note that this does not use the same bit ordering as the compression.

[edit]

Dur, on second thought this is exactly the same format as romc.  This has the nice effect of getting rid of that nonsensical 0x400000 multiplier, too.

[http://hcs64.com/files/romchu06.zip](http://hcs64.com/files/romchu06.zip)
