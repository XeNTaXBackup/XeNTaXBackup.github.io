## Post #1
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2016-08-05T05:05:33+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

Hi!  I'm currently trying to reverse engineer the music from Cryo Interactive's 1992 game KGB, re-released as Conspiracy.  In order to get to the music files, I have to decompress the files first.  The game uses a compression algorithm called SQX, that's exclusive to this game.  What's important is that it is very similar to a known format, HSQ (which is used by Dune and MegaRace).  Nevertheless, it is still slightly different and I could use your help.

Here's what we know:
* SQX is very similar to HSQ.  Both compression formats are based off of Lemple-Ziv and use Sliding Window RLE compression.

* Both formats have a six byte header, however SQX's is different.

* HSQ uses a checksum of 0xAB, which is calculated by adding the first six bytes of the header, to perform decompression.  From what it looks like, SQX doesn't use a checksum.

* Both formats use at least 18-byte chunks, a two-byte header that's used as a bitmap and the proceeding 16 or more bytes is the compressed data.
How do we know SQX is very similar to HSQ?

Because Cryo placed a song from Dune ("MORNING") in the assets for KGB and had it compressed in SQX instead of HSQ.  So we have the MORNING song file in SQX, HSQ and in uncompressed format, which allows us to compare between the formats.  Now, SQX is supported in the old OPL2/3 player RDOSPlay, but the source code is long gone, so we still don't know how the format works, however I did comfirm that the MORNING.SQX file does play correctly in RDOSPlay and sounds exactly like it's HSQ and uncompressed counterparts.  

To help with analysis, I've attached the HSQ, SQX and uncompressed SDB files to this thread.  You can easily see how similar SQX is to HSQ in a hex editor.  I also attached the source code to a program that handles HSQ decompression so you can see how that format works.  In addition, [here's a link](https://wiki.multimedia.cx/index.php?title=HNM_%281%29#Video_Block_171) that shows the logic for HSQ's algorithm.

I understand this is a really obscure game and an even more obscure file format.  But, if anyone can help out, it would mean so much to me.  Thanks in advance!
[sqx_example.zip](https://xentaxbackup.github.io/file/11486_sqx_example.zip)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-08-06T00:07:38+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

someone has posted a youtube playlist for this game here - [http://www.dosnostalgia.com/?p=664](http://www.dosnostalgia.com/?p=664)

i found the sourcecode for unhsq here - [https://sourceforge.net/p/dunerevival/c ... gs/unhsq.c](https://sourceforge.net/p/dunerevival/code/HEAD/tree/tools/hsq/hsq_by_bigs/unhsq.c)
it was missing from your post.

also, in another thread you said you haven't coded anything but hex-edited change? hardcode
## Post #3
- Username: MrSinistar
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Sep 30, 2012 5:20 am
- Post datetime: 2016-08-07T03:15:34+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

> Reply from WRS
>
> someone has posted a youtube playlist for this game here - http://www.dosnostalgia.com/?p=664

i found the sourcecode for unhsq here - https://sourceforge.net/p/dunerevival/c ... gs/unhsq.c
it was missing from your post.

also, in another thread you said you haven't coded anything but hex-edited change? hardcode

Sorry for forgetting to add the sourcecode to the initial post.

Yes, I created new music content for MegaRace, which uses a slightly updated version of the [OPL2 music engine (known as HERAD)](http://www.vgmpf.com/Wiki/index.php?title=HERAD) that Dune and KGB use, so I could potentially put custom music into those game with very little modification.  It fairly easy to hex-edit your own MIDI data into the music files, it just takes time because it's very tedious.  I used preexisting MegaRace data for the instruments.  I did the majority of reverse-engineering the HERAD music format by playing back hex-edited files in both MegaRace and RDOSPlay.

[https://www.youtube.com/watch?v=TqBJedId4g4](https://www.youtube.com/watch?v=TqBJedId4g4)

[https://www.youtube.com/watch?v=bS-kgYqVIbM](https://www.youtube.com/watch?v=bS-kgYqVIbM)

KGB is the only game remaining that I don't have direct access to the uncompressed music files.  There's some very interesting programming in some of the songs and I wanted to see how exactly those songs were created, in order to better document the music format.  Using something like DRO2MIDI, to convert the OPL register values into MIDI isn't going to be enough.
## Post #4
- Username: binarymaster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 20, 2016 1:27 am
- Post datetime: 2016-10-19T19:59:28+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

> Reply from MrSinistar
>
> * Both formats have a six byte header, however SQX's is different.

* HSQ uses a checksum of 0xAB, which is calculated by adding the first six bytes of the header, to perform decompression.  From what it looks like, SQX doesn't use a checksum.

* Both formats use at least 18-byte chunks, a two-byte header that's used as a bitmap and the proceeding 16 or more bytes is the compressed data.
It's obvious that these two compression algorithms are similar. Most bytes are the same till offset 0x240.

But SQX using different bit mask method, and probably improved due to smaller compressed size.
## Post #5
- Username: binarymaster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 20, 2016 1:27 am
- Post datetime: 2016-10-19T21:21:11+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

Also one interesting thing, according to the game files, there are different types of SQX depending on byte at offset 3.

Default queue bits are:
HSQ: 0xFF
SQX-0: 0x00
SQX-1: 0x55
SQX-2: 0xFF
## Post #6
- Username: binarymaster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 20, 2016 1:27 am
- Post datetime: 2016-10-20T00:33:53+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

Value at offset 5 specifies how many bits are used in counter.

Examples:
val = 3: 3 bits for count, 13 bits for offset
val = 4: 4 bits for count, 12 bits for offset
etc.

In SQX-0 algorithm the first bit is checked for zero. Other logic is same as HSQ except variable bits for count/offset.

SQX-1 has much more differences. (SQX-2 is not used in music files, I'm not planning to inspect it.)
## Post #7
- Username: binarymaster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 20, 2016 1:27 am
- Post datetime: 2017-02-28T08:36:46+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

I've implemented a decompression program, however the SQX-1 algorithm is still not finished.
The decompressed data at first looks good, but only for few bytes.

Attached a program source with test files (compressed and decompressed - ripped from game memory, running in DOSBox).
[UnHSQ.7z](https://xentaxbackup.github.io/file/12542_UnHSQ.7z)
## Post #8
- Username: binarymaster
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 20, 2016 1:27 am
- Post datetime: 2017-04-05T20:54:06+00:00
- Post Title: Help with SQX files from KGB / Conspiracy

Finally, the universal HSQ / SQX decompressor is done!

Big thanks goes to -=CHE@TER=- who helped a lot with disassembling the original unpacker code from KGB game   
[https://www.extractor.ru/ipb/index.php?showtopic=8767](https://www.extractor.ru/ipb/index.php?showtopic=8767)

I converted disassembly to Delphi code, and now it works excellent! Attached archive contains the source code and compiled Win32 binary executable.

Have a nice day!

/thread
[UnHSQ.7z](https://xentaxbackup.github.io/file/12746_UnHSQ.7z)
