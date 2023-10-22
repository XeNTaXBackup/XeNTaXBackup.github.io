## Post #1
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-11-28T18:10:24+00:00
- Post Title: Biohazard HD Remaster (PS3) .ARC

Hello guys, I'm trying to understand the Biohazard files, the conteiner have the .arc extension, and there a possibly .zlib compression. I used Offzip to extract, and extracted two files: EventMes_e106_eng.dmg and RoomMes_r106_eng.dmg, two text files, so far so good.
So, I used the compression .zlib in autoit (zlib.dll), but the structure became different, freezing in-game test...
Testing without compression, freezing too...

(freezing only happens in the part of the edited file, firsts dialogues.)

Here is some information about the file we got:

> Endianness -> Big Endian
>
> 
>
> *HEADER 16 BYTES*
>
> Signature: {0}SFH
>
> Unknown: 0x00010001
>
> Size ARC: 0x00000F4F
>
> Unknown: 0x00000000
>
> *******************
>
> *ARC*
>
> File Signature: {0}CRA
>
> Version: {0x00 08} = (8)
>
> Number of Files: {0x00 02} = 2 Files
>
> ---------------------------------------------------
>
> For each File:
>
> File Name: 64 Bytes
>
> Code of Extension: 4 Bytes (0X242BB29A) = .dmg
>
> Size Comp:		4 bytes (0x00000179)
>
> Size Decomp:		4 Bytes (0x00002EEA)
>
> Offset (-0x10):			4 bytes (0X00000058) 
>
> ---------------------------------------------------
>
> For each File in pack:
>
> Math "Offset" += 0x10
>
> Go To Offset
>
> Read "Size Comp Bytes"
>
> ---------------------------------------------------
>
> "Size ARC" += 0x10
>
> Go to "Size ARC"
>
> Unknown Bytes - 32 Bytes

Our objective (my group) is to extract the .dmg to translate the dialogues, and then reinsert them in .arc.
If anyone knows how works these .arc files, please help us.

File:
[http://www.mediafire.com/download/qqb7i ... s_r106.arc](http://www.mediafire.com/download/qqb7irrloxhr7qf/mes_r106.arc)

PS: In each .arc file, has some bytes who point to the end of the file that appears to be md5:
## Post #2
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2014-11-30T14:36:27+00:00
- Post Title: Biohazard HD Remaster (PS3) .ARC

This tool by Sectus should be able to handle them.
[www.tzarsectus.com/tools/ARCtool.rar](http://www.tzarsectus.com/tools/ARCtool.rar)
## Post #3
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2014-11-30T18:38:00+00:00
- Post Title: Biohazard HD Remaster (PS3) .ARC

Thanks, but my problem is in insertion. My group has already managed to extract.
