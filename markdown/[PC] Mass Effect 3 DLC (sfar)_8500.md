## Post #1
- Username: filipmosner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 30, 2008 2:17 am
- Post datetime: 2012-03-08T00:19:32+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Hi,

Does anyone know how to unpack/pack filetype sfar (e.g. DLC From Ashes)? We need for translate.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2012-03-08T17:03:05+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Inside the file we can see

> RAFS   >      G   r     amzl
Maybe is some LZMA?
## Post #3
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2012-03-10T13:02:56+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Rick have already made an unpacker, although it works only with little endian (PC), the xbox files are the same with the exception of Big Endian.

[Rick ME3 tools](http://svn.gib.me/builds/masseffect3/)
## Post #4
- Username: com123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2011 12:39 am
- Post datetime: 2012-03-11T10:58:18+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

> Reply from peshkohacka
>
> Rick have already made an unpacker, although it works only with little endian (PC), the xbox files are the same with the exception of Big Endian.

Rick ME3 tools

PCConsoleTOC.bin is not open.....
## Post #5
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-11T12:10:05+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

> Reply from peshkohacka
>
> Rick have already made an unpacker, although it works only with little endian (PC), the xbox files are the same with the exception of Big Endian.

Rick ME3 toolsThat's not true, my SFAR handling code detects endianness appropriately. If it's actually not working, please let me know and/or provide cuts.
## Post #6
- Username: filipmosner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 30, 2008 2:17 am
- Post datetime: 2012-03-11T12:38:42+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Rick, can u send me mini-manual for decode and encode sfar file? Thanx.
## Post #7
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-03-11T13:52:27+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Rick could you add repack support? Thanks!
## Post #8
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-12T11:26:53+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

And what about a PackSFXArchive? I'd like to repack the DLC in order to delete the unused bik movies and lang files that I don't use.
## Post #9
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2012-03-12T18:24:54+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> peshkohacka wrote:Rick have already made an unpacker, although it works only with little endian (PC), the xbox files are the same with the exception of Big Endian.

Rick ME3 toolsThat's not true, my SFAR handling code detects endianness appropriately. If it's actually not working, please let me know and/or provide cuts.

Compiled the latest commit (rev40) still throwing "NotImplementedException" when tries to find out the Compression Scheme. [This](http://www.mediafire.com/?2cymda762mph5sj) are 2 small .sfar archives with 360s endianness.
## Post #10
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-13T07:12:26+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Ah yeah, I don't have LZX implemented. PC files only use LZMA. I'll look into it.
## Post #11
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-13T09:18:14+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Is SFAR an acronym for SFx ARchive?
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-13T13:43:53+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> Is SFAR an acronym for SFx ARchive?Most likely, "SFX" -- internal project name for Mass Effect.
## Post #13
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-03-13T15:00:04+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Rick, are you working on packing support? Because if so, I wouldn't like to the the same work over again. And you're much more familiar with the file formats, than I am.
## Post #14
- Username: peshkohacka
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jan 22, 2009 6:20 am
- Post datetime: 2012-03-13T15:42:08+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> Ah yeah, I don't have LZX implemented. PC files only use LZMA. I'll look into it.

Sorry about the misunderstanding i should have clarify that i had endian problems i had was with the very first commits, and now only the lzx appears to be problem.
## Post #15
- Username: filipmosner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 30, 2008 2:17 am
- Post datetime: 2012-03-16T16:20:11+00:00
- Post Title: [PC] Mass Effect 3 DLC (sfar)

Rick Good job with sfar unpack! Any idea, how translate DLCs, how insert translated tlk file?
## Post #16
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-16T19:43:28+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from filipmosner
>
> Rick Good job with sfar unpack! Any idea, how translate DLCs, how insert translated tlk file?
You don't need to insert translation, the DLC package already contains lot of langs like english, italian, german, french etc... you just need to select the audio/subtitle language ingame
## Post #17
- Username: filipmosner
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 30, 2008 2:17 am
- Post datetime: 2012-03-16T19:58:56+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Yes, but, i want another language which is not in in  the game.
## Post #18
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-16T21:54:28+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I've tried putting all DLC CookedPCConsole files on BioWare\CookedPCConsole but it didn't work. If I only knew better the .sfar structure, i only know that's some sort of lzma archive
## Post #19
- Username: oveja
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Feb 24, 2011 4:35 am
- Post datetime: 2012-03-24T05:45:47+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

any news?
## Post #20
- Username: otacon172
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 24, 2012 2:15 pm
- Post datetime: 2012-03-24T06:28:09+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Chinese people have succeeded in Repack sfar file. 
[http://img51.imageshack.us/img51/2595/2 ... 651592.jpg](http://img51.imageshack.us/img51/2595/20120319202651592.jpg)
[http://img42.imageshack.us/img42/2948/2 ... 65104c.jpg](http://img42.imageshack.us/img42/2948/2012031920265104c.jpg)
However I do not know how to Repack

Here is a Chinese patch. 
《质量效应3》3DM轩辕汉化组汉化补丁v2.0
[http://dl.3dmgame.com/201203/18213.html](http://dl.3dmgame.com/201203/18213.html)
## Post #21
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-03-24T09:12:31+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

That "thing" from 3DM seems like an on-the-fly patcher. At least when I tried it, it didn't modify DLC's SFAR.
## Post #22
- Username: newtonseple
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 25, 2012 6:54 pm
- Post datetime: 2012-03-25T11:14:42+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

So, do we need to repack it to mod the DLC? I saw a directory structure like this in the Default.sfar archive:

__UNKNOWN
----B55019CBF9D3DA65D55B321C0019697C (file)
BIOGame
----DLC
--------DLC_HEN_PR
------------CookedPCConsole
----------------(Tons of game files, including the .bin file i wish to mod)
------------Movies
----------------(Files)
------------PCConsoleTOC.bin

I tried replacing the original DLC_HEN_PR folder with the one from the archive, but then the game complained about it being "corrupt". I also thought about merging the files with the original game files, but then they would not be in the TOC.

Bottom line, do we need a repacker to mod the DLC, or is there a way to make ME3 read the unpacked DLC?
## Post #23
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-28T10:18:15+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

i'm trying to understand what's doing the UnpackSFXArchive and i'm stuck in the Hash value: what kind of hashing function is that? it's like a MD5 but when I try to hash a file by myself i get a different value.
i.e.

```
     hash inside the sfar:       5C05233F1C158647D276114DFBDF8C99
     hash coded with md5sum.exe: 2F262611252CA78B31C475388BC88462

```
## Post #24
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-03-28T10:44:04+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Because the whole path is MD5 hashed, not only filename:

/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc
## Post #25
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-28T11:34:31+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from mnn
>
> Because the whole path is MD5 hashed, not only filename:

/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc

so it's not the file itself, it's just the filename?

I've just tested the string "/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc" on this site [http://www.adamek.biz/md5-generator.php](http://www.adamek.biz/md5-generator.php) and the result is: fe5412ac7cf7420e439c28c0b557d49c

It's still different from 5C05233F1C158647D276114DFBDF8C99
## Post #26
- Username: com123
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2011 12:39 am
- Post datetime: 2012-03-28T19:04:40+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> mnn wrote:Because the whole path is MD5 hashed, not only filename:

/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc

so it's not the file itself, it's just the filename?

I've just tested the string "/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc" on this site http://www.adamek.biz/md5-generator.php and the result is: fe5412ac7cf7420e439c28c0b557d49c

It's still different from 5C05233F1C158647D276114DFBDF8C99

MD5_SHA-1
[http://download.cnet.com/MD5-SHA-1-Chec ... 11445.html](http://download.cnet.com/MD5-SHA-1-Checksum-Utility/3000-2092_4-10911445.html)
## Post #27
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-28T21:59:59+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from com123
>
> leroyjenkins wrote:mnn wrote:Because the whole path is MD5 hashed, not only filename:

/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc

so it's not the file itself, it's just the filename?

I've just tested the string "/BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc" on this site http://www.adamek.biz/md5-generator.php and the result is: fe5412ac7cf7420e439c28c0b557d49c

It's still different from 5C05233F1C158647D276114DFBDF8C99

MD5_SHA-1
http://download.cnet.com/MD5-SHA-1-Chec ... 11445.html

With the program the result it's 43CCD770944381A3F991DBBD2B5E0519 !!!
Maybe it's not only the file content or filepath, maybe they added a salt variable with the input....
## Post #28
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-03-29T05:21:22+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Filename hash of /BIOGame/DLC/DLC_HEN_PR/CookedPCConsole/BioH_Liara_03_Explore.pcc is 3F23055C4786151C4D1176D2998CDFFB. Apparently the path is normalized first - lower case, only ASCII characters + other stuff:

```

switch (s)
{
    case 0x008C: return (char)0x9C;
    case 0x009F: return (char)0xFF;

    case 0x00D0:
    case 0x00DF:
    case 0x00F0:
    case 0x00F7: return c;
}

if ((c >= 'A' && c <= 'Z') ||
    (c >= 'A' && c <= '?'))
{
    return char.ToLowerInvariant(c);
}

return c;
```
## Post #29
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-29T09:53:44+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Yeah, it worked! I made a simple test using FileNameHash class:

```
FileNameHash temp2 = FileNameHash.Compute(temp1);
Console.WriteLine("Filename: {0}\n  Funnyhash: {1}\n",temp1,temp2.ToString());

```

and the result is correct!!! Thanks mnn
## Post #30
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-29T17:00:53+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Guys I have another question regarding the UnpackSFXArchive: when it's time to decompress with lzma the program passes some kind of properties to the LZMA.Decompress function, it pass exactly this 5 bytes: 5D 00 00 01 00. Now my question is, what's the meaning of this bytes? I've searched on google but I've found nothing about it. Also I've tried to use the LZMA.Compress with default settings and it gaves me similar bytes: 5D 00 10 00 00.
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-03-29T22:18:28+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

You should take a look at the [LZMA SDK](http://www.7-zip.org/sdk.html), ie in C\LzmaEnc.h.
## Post #32
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-03-30T09:14:42+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> You should take a look at the LZMA SDK, ie in C\LzmaEnc.h.
Thank you, I've found the correct parameters to encode correctly. It just use the default parameters and level 1 to encode. Thanks again
## Post #33
- Username: ethanhunt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 30, 2012 5:52 pm
- Post datetime: 2012-03-30T10:47:02+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> Is SFAR an acronym for SFx ARchive?

Yes sfx archive is only that tool to extract the sfar file.There are more game not need to extract just click and play.
## Post #34
- Username: Scorpick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 31, 2012 10:10 pm
- Post datetime: 2012-03-31T14:19:13+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> You should take a look at the LZMA SDK, ie in C\LzmaEnc.h.

Hello, I successfully used Rick's tool to decompress the sfar file, but I don't know how to compress the output then, because it's a folder and the LZMA SDK can only compress a file.
Any ideas? Thanks.
## Post #35
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-01T13:04:44+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I'm having problems using the LZMA.Compress to compress data above 16mb. Anybody knows what kind of functions are inside lzma_32(64).dll?
## Post #36
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-01T23:02:11+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> I'm having problems using the LZMA.Compress to compress data above 16mb. Anybody knows what kind of functions are inside lzma_32(64).dll?If you mean my native DLLs, they're straight up exported LzmaCompress/LzmaUncompress from LzmaLib.c.

Edit: wait, why are you even trying to compress data sizes that large? The default maximum block size is 0x010000 bytes.
## Post #37
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-02T00:39:06+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> wait, why are you even trying to compress data sizes that large? The default maximum block size is 0x010000 bytes.
Yes I know that the max block size is 65536 Bytes. I've found a solution for that problem and I created a "sfar like" packer. It's sfar like because it copy the structure of the sfar file that I learned looking inside the From Ashes DLC sfar file and the code of the unpackSFXArchive. The problem is that the created sfar doesn't work in the game, it always gives me an error when it checks the downloadable content.

Also I don't know how to process the compressed blocks that are bigger than the uncompressed blocks.
i.e. when I compress \DLC_OnlinePassHidCE_ITA.afc

```
    block: 65536 B, tlen: 985647 B, filepos: 65536 B, csize 61865 B
    blocknum: 299
    block: 65536 B, tlen: 920111 B, filepos: 131072 B, csize 62495 B
    blocknum: 300
    block: 65536 B, tlen: 854575 B, filepos: 196608 B, csize 61755 B
    blocknum: 301
    block: 65536 B, tlen: 789039 B, filepos: 262144 B, csize 61806 B
    blocknum: 302
    block: 65536 B, tlen: 723503 B, filepos: 327680 B, csize 61536 B
    blocknum: 303
    block: 65536 B, tlen: 657967 B, filepos: 393216 B, csize 56386 B
    blocknum: 304
    block: 65536 B, tlen: 592431 B, filepos: 458752 B, csize 61428 B
    blocknum: 305
    block: 65536 B, tlen: 526895 B, filepos: 524288 B, csize 61383 B
    blocknum: 306
    block: 65536 B, tlen: 461359 B, filepos: 589824 B, csize 62324 B
    blocknum: 307
    block: 65536 B, tlen: 395823 B, filepos: 655360 B, csize 60677 B
    blocknum: 308
    block: 65536 B, tlen: 330287 B, filepos: 720896 B, csize 62094 B
    blocknum: 309
    block: 65536 B, tlen: 264751 B, filepos: 786432 B, csize 61656 B
    blocknum: 310
    block: 65536 B, tlen: 199215 B, filepos: 851968 B, csize 61342 B
    blocknum: 311
    block: 65536 B, tlen: 133679 B, filepos: 917504 B, csize 61237 B
    blocknum: 312
    block: 65536 B, tlen: 68143 B, filepos: 983040 B, csize 62964 B
    blocknum: 313
    block: 65536 B, tlen: 2607 B, filepos: 1048576 B, csize 61497 B
    blocknum: 314
    block: 2607 B, tlen: 0 B, filepos: 1051183 B, csize 2612 B
   Total Uncompressed: 1051183 B, Total Compressed: 985057 B

```

the last compressed block (2612 Bytes) is larger than the uncompressed block (2607 Bytes), which one should i write into the file? If I leave the compressed block the unpackSFXArchive gives me a InputEOF error:

```
uncompressedSize: 2607, actalUncompressedSize: 2567, compressedSize: 2607, actualCompressedSize 2607
```
## Post #38
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-03T12:14:16+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I've almost succeeded to create a sfar packer exe! If I pack the DLC_OnlinePassHidCE (the N7 DLC) it works without problems, but when I repack the "From Ashes" DLC the game freezes after I load a previous game. Notice that the game doesn't warn me anymore when it loads the file! If you want to try I'm posting this link [http://www.mediafire.com/?edn4p6okkq24jl9](http://www.mediafire.com/?edn4p6okkq24jl9)
Any help and advice is useful, thanks
## Post #39
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-04T08:46:53+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Anybody knows what's the structure of PCConsoleTOC.bin? I think it's connected to the problem I have because using a hex editor to open it i saw a list of files related to the files inside the dlc.
## Post #40
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-04T10:14:55+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

leroyjenkins: Modifying PCConsoleTOC.bin shouldn't be necessary to modify/repack Default.sfar.
## Post #41
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-04T13:05:32+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

If you change any file sizes you definitely need to update PCConsoleTOC.bin, as sizes are listed there, if the size is wrong the game will fail to load the file properly.
## Post #42
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-04T14:47:05+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Rick: Well, I'm not updating PCConsoleTOC.bin, but I am modifying a file within SFAR file (thus different filesize), and the game works as it should.
## Post #43
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-04T14:57:46+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

The odd thing that happens to me is if I unpack/repack the N7 DLC (about 56mb, no videos inside) the game works, but if I do the same thing on the From Ashes the game crashes after I load a savegame... Maybe it's only me, that's why I ask you, if you have tried my repacker does it the same trick to you?
## Post #44
- Username: Scorpick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 31, 2012 10:10 pm
- Post datetime: 2012-04-04T18:03:24+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I tried to unpack/repack DLCs.
DLC_OnlinePassHidCE works fine.
DLC_HEN_PR doesn't work. The game crashes during downloadable content check.

I noticed that after unpack/repack the size of sfar file is different, maybe there is a problem.
I can't help you in this because I am no programmer.
But why the other DLC works? Have you tried it in multiplayer?
## Post #45
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-04T20:50:35+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

How can I update/edit PCConsoleTOC.bin? With hex editor?
## Post #46
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-04T21:36:15+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

leroyjenkins: No, I have my own SFAR packer.
## Post #47
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-05T10:28:33+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I made an updated version of my sfar Packer, now it works for me, I hope it works for you.
I tested with Win7 Ultimate x64: [http://www.mediafire.com/?cmiapy1ndoyv207](http://www.mediafire.com/?cmiapy1ndoyv207)
## Post #48
- Username: Scorpick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Mar 31, 2012 10:10 pm
- Post datetime: 2012-04-05T10:58:36+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> I made an updated version of my sfar Packer, now it works for me, I hope it works for you.
I tested with Win7 Ultimate x64: http://www.mediafire.com/?cmiapy1ndoyv207

Thank you, it works fine now. Tested on From Ashes savegame.
## Post #49
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-05T11:05:38+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

I'm posting a new one (D'oh) which works for win xp too: [http://www.mediafire.com/?dvloc1ym11rpqwm](http://www.mediafire.com/?dvloc1ym11rpqwm). Maybe I have to create a new thread for this
## Post #50
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-05T17:08:42+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> I made an updated version of my sfar Packer, now it works for me, I hope it works for you.
I tested with Win7 Ultimate x64: http://www.mediafire.com/?cmiapy1ndoyv207

Link broken.
## Post #51
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-05T17:26:51+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from ballsofsteel
>
> leroyjenkins wrote:I made an updated version of my sfar Packer, now it works for me, I hope it works for you.
I tested with Win7 Ultimate x64: http://www.mediafire.com/?cmiapy1ndoyv207

Link broken.

download it from here: [http://www.mediafire.com/?dvloc1ym11rpqwm](http://www.mediafire.com/?dvloc1ym11rpqwm)
## Post #52
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-05T18:13:52+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Well, I unpacked Default.sfar (589.839kb) with Rick's unpacker, translated some lines with Mass Effect 2 tlk tool, then I repacked default folder with AK86SfarPacker.0.99.1. I replaced old Default.sfar with the new one (257.452kb).  After game checked downloadable content, I tried to load a save game but game crashed.
## Post #53
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-05T18:54:50+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from ballsofsteel
>
> Well, I unpacked Default.sfar (589.839kb) with Rick's unpacker, translated some lines with Mass Effect 2 tlk tool, then I repacked default folder with AK86SfarPacker.0.99.1. I replaced old Default.sfar with the new one (257.452kb).  After game checked downloadable content, I tried to load a save game but game crashed.

That's odd, if you haven't delete any file the size must be similar to the original. Also, like Rick said before 
> Reply from Rick
>
> If you change any file sizes you definitely need to update PCConsoleTOC.bin, as sizes are listed there, if the size is wrong the game will fail to load the file properly.
## Post #54
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-05T19:07:25+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

"If you change any file sizes you definitely need to update PCConsoleTOC.bin, as sizes are listed there, if the size is wrong the game will fail to load the file properly."

How can I update PCConsoleTOC.bin?
## Post #55
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-05T22:15:02+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Sorry I don't know how to modify it, I haven't find any program to edit it.
## Post #56
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-06T13:13:57+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Guys: original size of DLC_HEN_PR_INT.tlk is 55 110 bytes - size of translated file is 58 420 bytes (using my own TLK editor). Game functions as normal. I haven't seen your packer code, but it must produce somehow malformed SFAR file.
## Post #57
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-06T13:30:44+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from mnn
>
> Guys: original size of DLC_HEN_PR_INT.tlk is 55 110 bytes - size of translated file is 58 420 bytes (using my own TLK editor). Game functions as normal. I haven't seen your packer code, but it must produce somehow malformed SFAR file.

I repeat, like Rick said before, if you change a file dimension you have to modify PCConsoleTOC.bin because inside it there is a list of the packed files + their dimensions and other stuff.

Try this:
- open From Ashes PCConsoleTOC.bin with a hex editor
- go to offset 0x3518 (watch out is hex, not decimal number!)
- change the value 46 D7 (reversed because is little endian is D746, in decimal is 55110, the dimension of the file)
  to 34 E4 (again, reversed is E434, in decimal is 58420, the new dimension)
- save the file, compress all and try
## Post #58
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-06T14:21:54+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> I repeat, like Rick said before, if you change a file dimension you have to modify PCConsoleTOC.bin because inside it there is a list of the packed files + their dimensions and other stuff.
Do I really have show you proof?

```
http://img805.imageshack.us/img805/8895/masseffect3201204061620.jpg
http://img853.imageshack.us/img853/8895/masseffect3201204061620.jpg
http://img32.imageshack.us/img32/8895/masseffect3201204061620.jpg
http://img27.imageshack.us/img27/7564/masseffect3201204061621.jpg
http://img803.imageshack.us/img803/7564/masseffect3201204061621.jpg
```


I'm not saying it shouldn't be modified, I'm saying it's not necessary. If you properly modify SFAR file, then the game will accept it (and use it, of course).
[PCConsoleTOC.zip](https://xentaxbackup.github.io/file/5265_PCConsoleTOC.zip)
## Post #59
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-06T14:32:58+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Ok so it's not needed. I've only unpack/repack the dlc to delete the unuseful extras .bik files, I haven't edited or added anything. But why do you say that my packer produce a malformed sfar file? I've tested and it works.
## Post #60
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-06T14:46:52+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Because, you've said game crashes, when you modify SFAR file.

Also you shouldn't remove any files from SFAR, because other files might reference them. If you want to get rid of movies, you should replace them with blank ones (I'm sure you find working ones somewhere).
## Post #61
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-06T15:35:59+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Yes I said that but I fixed the problem and now it works, also I've only deleted movies that they're not used in the game. Have a look at Lifepod_FullScene.bik, dlcmiddle.bik and flashback1.bik, they are just a pre-rendered useless videos.
## Post #62
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-06T22:13:22+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

@mnn, can you send me your repacker? Please. I guess, I'm missing something.
## Post #63
- Username: aotobus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 09, 2012 12:27 am
- Post datetime: 2012-04-08T16:31:01+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> Yes I said that but I fixed the problem and now it works, also I've only deleted movies that they're not used in the game. Have a look at Lifepod_FullScene.bik, dlcmiddle.bik and flashback1.bik, they are just a pre-rendered useless videos.

I have tried your tools in Win7x64 in my laptop,i use the 53.7 MB default.sfar
when i unpack it ,i got a 151 MB folder,but after repack it ,the size is only 4691KB.

Can anybody help me ?
## Post #64
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-08T17:59:11+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

If it's not working, please pass me your final compressed file to see where's the problem
## Post #65
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-09T14:52:26+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

A new (and hopefully working this time) version (0.99.2) of the sfar Packer is here: [http://www.mediafire.com/?qyzdci68fx6cf](http://www.mediafire.com/?qyzdci68fx6cf)
## Post #66
- Username: aotobus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 09, 2012 12:27 am
- Post datetime: 2012-04-10T16:24:18+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> A new (and hopefully working this time) version (0.99.2) of the sfar Packer is here: http://www.mediafire.com/?qyzdci68fx6cf

can you PM me your E-mail?i'll send the .sfar i got for you .

the new one 0.2 in my Win7 x64 also got a 257M sfar which should be more than 500M,and the 50M one become 5M
## Post #67
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-10T19:30:54+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> A new (and hopefully working this time) version (0.99.2) of the sfar Packer is here: http://www.mediafire.com/?qyzdci68fx6cf

Resurgence DLC sfar file: 215mb
Unpacked file folder: 672mb
Repacked sfar: 18,7mb   

Compressed file: [http://depositfiles.com/files/jfqsh2cmo](http://depositfiles.com/files/jfqsh2cmo)
## Post #68
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-10T23:53:59+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Ok guys I've localized (not solved) where is the problem, it may take a couple of days, depending on how much free time I'll have   
Stay tuned
## Post #69
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-11T20:46:03+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

New version of my sfar packer 0.99.3 is here: [http://www.mediafire.com/?qyzdci68fx6cf](http://www.mediafire.com/?qyzdci68fx6cf)
Warning: this version produce a working sfar file, but is not unpackable with Gibbed.MassEffect3.SFXArchiveUnpack
Hope it works!
## Post #70
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-11T20:49:50+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Well, that's rather unsatisfying solution.
## Post #71
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-11T21:04:06+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from mnn
>
> Well, that's rather unsatisfying solution.
I know, until I find a solution to why the lzma.dll doesn't compress properly, I've switched to a C# function. It works but it's not compatible with the decompress function of Rick's SFXArchiveUnpack.
## Post #72
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-11T21:10:25+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

LZMA.dll compresses correctly for me.
## Post #73
- Username: ballsofsteel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 05, 2012 4:22 am
- Post datetime: 2012-04-12T15:11:04+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Thank you! It works and I didn't even touch pcconsoletoc.bin!

[http://b1204.hizliresim.com/w/d/4cj0n.png](http://b1204.hizliresim.com/w/d/4cj0n.png)

[http://b1204.hizliresim.com/w/d/4cj78.png](http://b1204.hizliresim.com/w/d/4cj78.png)
## Post #74
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-12T15:34:27+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

leroyjenkins: See? Modifying PCConsole.bin is not necessary.
## Post #75
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-12T15:49:04+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from ballsofsteel
>
> Thank you! It works and I didn't even touch pcconsoletoc.bin!

http://b1204.hizliresim.com/w/d/4cj0n.png

http://b1204.hizliresim.com/w/d/4cj78.png
You welcome! Glad to see it's working!
## Post #76
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-04-12T19:15:18+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from mnn
>
> leroyjenkins: See? Modifying PCConsole.bin is not necessary..tlk files are not referenced by PCConsoleTOC.bin, so of course not.
## Post #77
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-12T20:00:08+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

My last and final effort is the DLC Manager 1.0 here: [http://www.mediafire.com/?1emlze8ilpfgft5](http://www.mediafire.com/?1emlze8ilpfgft5)
With it you can both Compress a folder to a .sfar file or Decompress a sfar file to a folder, just drag & drop!
## Post #78
- Username: LaCi85
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 06, 2012 10:40 pm
- Post datetime: 2012-04-12T20:55:56+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

leroyjenkins:
It is a fine tool but for localization purposes I would need a tool that can switch files into sfar format and don't need to unpack and then repack the full sfar.
I think it's possible 'mnn' created such a tool for their localization project.
So if you could possibly create one that could enable this, me and my localization team would be very grateful.
## Post #79
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-12T21:08:36+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from LaCi85
>
> leroyjenkins:
It is a fine tool but for localization purposes I would need a tool that can switch files into sfar format and don't need to unpack and then repack the full sfar.
I think it's possible 'mnn' created such a tool for their localization project but he hasn't published it.
So if you could possibly create one that could enable this, me and my localization team would be very grateful.
Hmm, when you say switch you mean overwrite? and what kind of files are we talking about, like .tlk files? I think that's possible but I need more specific informations
## Post #80
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:38:32+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Review the new forum rules. [viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
## Post #81
- Username: LaCi85
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 06, 2012 10:40 pm
- Post datetime: 2012-04-12T22:50:58+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Yes I'm sorry I will send private message.
## Post #82
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2012-04-13T12:14:23+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from Rick
>
> .tlk files are not referenced by PCConsoleTOC.bin, so of course not.
However, by looking at contents PCConsoleTOC.bin, I believe they are.
## Post #83
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-18T22:43:39+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

A new version of sfar Packer/Unpacker 1.0.1 is here, now compatible with Gibbed.MassEffect3.SFXArchiveUnpack
[http://www.mediafire.com/?ecgok33aglf8mcy](http://www.mediafire.com/?ecgok33aglf8mcy)
## Post #84
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-04-25T14:57:47+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

My last effort, a sfar Explorer that uses a graphical user interface, here's a preview:
[](http://imageshack.us/photo/my-images/31/dlcexplorerimg1.jpg/)

And here you can download the first version v1.0.1.0: [http://www.mediafire.com/?nwkwo87kmw57lpr](http://www.mediafire.com/?nwkwo87kmw57lpr)
## Post #85
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-11-30T15:43:56+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

Can somebody tell me where exactly the compressed data starts? I want to write a decompressor with QuickBMS.
## Post #86
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-11-30T16:25:49+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from leroyjenkins
>
> My last effort, a sfar Explorer that uses a graphical user interface, here's a preview:


And here you can download the first version v1.0.1.0: http://www.mediafire.com/?nwkwo87kmw57lpr

Does it support also X360 version pls ? Need repack sfar files for loc purpose
## Post #87
- Username: leroyjenkins
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Feb 28, 2012 4:35 pm
- Post datetime: 2012-12-24T11:10:41+00:00
- Post Title: Re: [PC] Mass Effect 3 DLC (sfar)

> Reply from michalss
>
> Does it support also X360 version pls ? Need repack sfar files for loc purpose

Sorry, I don't have an Xbox360, can't help you.
