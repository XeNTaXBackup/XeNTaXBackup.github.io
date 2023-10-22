## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-11T00:52:02+00:00
- Post Title: Drift City Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-03-11T02:52:42+00:00
- Post Title: Drift City Online

the files which contain the "NayaPack" signature at their beginning are simply XORed with a fixed key of 0x5a bytes:

```
31 85 76 39 34 3d 30 e8 67 36 36 32 3e 33 34 3b
11 15 16 16 14 13 1d 18 11 03 06 0c 04 03 06 08
2e 55 26 23 2a 23 2e 28 21 21 26 27 2e 00 2d 2d
cf a5 06 02 04 0f 07 18 e1 15 36 18 60 13 1a 19
11 15 16 10 12 13 17 38 f1 25
```

the XORing is offset based so, for example, the byte at offset 0x20 of DriftLauncher.apc must be XORed with the byte at offset 0x20 of the key.

for the rest the structure of the decoded file is very simple:
4 bytes: absolute offset of the 16 bit table containing the size of all the compressed chunks
4 bytes: number of compressed chunks
4 bytes: probably the total decompressed size of the file
4 bytes: size of the filename (n)
n: filename

the chunks are compressed with the classical zlib deflate (windowbits 15) and have a maximum size of 16384 bytes
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-12T10:22:46+00:00
- Post Title: Drift City Online

Thanks a lot it worked perfectly 
I un xored the file no problem now I will try to extract the archives basing it off your other wonderful extractors 
[drift.rar](https://xentaxbackup.github.io/file/2012_drift.rar)

[drift.rar](https://xentaxbackup.github.io/file/2011_drift.rar)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-02T00:01:30+00:00
- Post Title: Drift City Online

I almost wrote a script with your help but how do I represent the chunks in your tool when decrypting a file?

```
get DUMMY long
getdstring VERSION 10
get FILES long

goto 0
filexor "0x01 0x05 0x06 0x02 0x04 0x03 0x07 0x08 0x01 0x05 0x06 0x0f 0x04 0x03 0x07 0x0c 0x31 0x85 0x76 0x39 0x34 0x3d 0x30 0xe8 0x67 0x36 0x36 0x32 0x3e 0x33 0x34 0x3b 0x11 0x15 0x16 0x16 0x14 0x13 0x1d 0x18 0x11 0x03 0x06 0x0c 0x04 0x03 0x06 0x08 0x2e 0x55 0x26 0x23 0x2a 0x23 0x2e 0x28 0x21 0x21 0x26 0x27 0x2e 0x00 0x2d 0x2d 0xcf 0xa5 0x06 0x02 0x04 0x0f 0x07 0x18 0xe1 0x15 0x36 0x18 0x60 0x13 0x1a 0x19 0x11 0x15 0x16 0x10 0x12 0x13 0x17 0x38 0xf1 0x25"
getdstring DUMMY1 32

    for i = 0 < FILES
    get OFFSET long
    get ZSIZE long # "this should be number of chunks"
    get SIZE long
    get NAMESIZE long
    getdstring NAME NAMESIZE
    
    clog NAME OFFSET ZSIZE SIZE
    next i
```

script is attached above also
[Init.rar](https://xentaxbackup.github.io/file/2010_Init.rar)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-02T09:46:15+00:00
- Post Title: Drift City Online

unfortunately at the moment there is no way to handle multiple chunks.
for doing it should be needed an instruction which tells QuickBMS to use the "append" mode so that the output file will not be overwritten but built piece by piece (chunk1+chunk2+chunk3+...chunkN).
I will think how to implement this "append" solution for the next release.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-03T14:36:09+00:00
- Post Title: Drift City Online

ok I have added the "Append" command (acts like a switch) in the new version of QuickBMS and I have created the [script](http://aluigi.org/papers/bms/drift_city.bms)

PS: remember to use the -o option otherwise it will continue to ask if you want to overwrite the files
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-03T16:35:42+00:00
- Post Title: Drift City Online

That works great 
Thanks so much for the new feature.
## Post #8
- Username: elegantvogue
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 25, 2010 9:11 pm
- Post datetime: 2010-02-26T10:30:05+00:00
- Post Title: Drift City Online

we can unpack the files, for example  Localize.agt   but the game doesnt load now...


Is there any way to repack the files and make .agt file again after editing them?
## Post #9
- Username: gametack
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 10, 2010 8:07 pm
- Post datetime: 2010-06-10T12:12:31+00:00
- Post Title: Drift City Online

have you tried a storage unpacker and repacker called soifs, it cannot unpack agt files but it should be able to repack if you were able to extract the files yourself and edit it. i dont know if it will work for drift city, it works for gunbound, a game which also use to be on ijji.
basically it allows you to assign a name to the storage file you are creating, assign it a size and then you drag or import your extracted files into it and you compact it and boom the agt file is made. if you want you can try it
