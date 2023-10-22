## Post #1
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-02-28T04:43:32+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

This is kinda the continuation of [this thread](http://forum.xentax.com/viewtopic.php?f=10&t=10174).

There is a new compression format for TR9. But before continuing, let's see the layout of a CDRM file (which was intrudced in TRU, TMYK!).

```
  u32 magic; // Always "CDRM", so 0x4344524d in BE, 0x4d524443 in LE
  u32 version; // Always 0 for TR9? Was 0x2 for some files in DX3 I think.
  u32 count; // number of blocks
  u32 pad; // pretty much everything is 16 byte aligned

CDRM BlockHeader (repeaded "count" times, 16 byte aligned at the end)
  u32 var1
    24 MSB = uncompressedSize; //size of uncompressed data chunk, max 0x40000
     8 LSB = blockType; // 1 is uncompressed, 2 is zlib, 3 is the new one
  u32 compressedSize; //size of the compressed data block

Data blocks (of "compressedSize" length, "count" number of blocks, each 16 byte aligned between each other)

```


OK so now an example of the new type of blocks.


You see that there is one block of type 3, with uncompressed size of 28952 bytes, and a compressed size of 20552 bytes.

If you look at offset 0x20, it's the start of the data. We obviously see that it's not a valid zlib header; it starts with 0xFF. But we see that the first 3 bytes are very similar to the bytes of the uncompressed size, just one line over (well except for 0x00 that became 0xFF). I looked at a bunch of CDRM files (not all) and they all share that pattern.

Let's look at another CDRM header.


This one has 2 blocks, the first one with the max uncompressed size of 0x40000. For the first block, the observation I previously made does't work. But it does work for the last block, which isn't the max uncompressed size! Look:


0x004158 <-> 0xFF4158

I tried to see if I could reconstruct the zlib header without success. So now the question is, what is it? What other compression method is usually used in game archives?

(I posted extracts of the game files as images, I hope it's OK   )
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-02-28T06:27:18+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

Cut block and try use

```
http://aluigi.altervista.org/papers/bms/comtype_scan2.bat
```
## Post #3
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-03-01T03:54:01+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

> Reply from Ekey
>
> Cut block and try use
Code: Select allhttp://aluigi.altervista.org/papers/bms/comtype_scan2.bms
http://aluigi.altervista.org/papers/bms/comtype_scan2.bat

Thanks for the link, didn't know about this tool. Looks very useful!

I tried it but unfortuanately didn't have any positive results. Guess we will have to wait for the PC version to unlock in order to poke around.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-01T09:48:08+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

Well for PS3 used ZLIB, seems for XBOX used inflate ?

Here simple files [http://www.sendspace.com/file/ohklwk](http://www.sendspace.com/file/ohklwk)

Uncompressed files have PS3T header and compressed again lol. Data begin from offset 0x24
## Post #5
- Username: sephiroth99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 24, 2011 3:23 am
- Post datetime: 2013-03-05T07:07:39+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

So the PC version uses zlib too (block type 2), so only the xbox version has the new block type 3.

Guess it's not really useful to try and reverse this compression stuff. oh well
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-09T20:50:26+00:00
- Post Title: Tomb Raider (2013) Compressed DRM (CDRM)

I don't have the xbox files but my guess (xbox + first byte equal to 0xff) is that the version for this platform uses xmemdecompress.
