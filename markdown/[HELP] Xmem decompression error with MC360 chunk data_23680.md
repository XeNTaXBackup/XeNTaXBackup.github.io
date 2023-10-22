## Post #1
- Username: theunholyone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 20, 2021 4:37 am
- Post datetime: 2021-04-03T16:22:58+00:00
- Post Title: [HELP] Xmem decompression error with MC360 chunk data

The data can be decompresses using the official XDK Xmemdecompress API but fails with MSPACK_ERR_DECRUNCH when using quickbms implementation in Linux or Mac, which uses libmspack lzx_decompress with window size 17 and a modified read function from UEViewer.
The file does not use native compression and has a standard 0xFF header. 

(libmspack impl: [https://github.com/kyz/libmspack/blob/m ... ack/lzxd.c](https://github.com/kyz/libmspack/blob/master/libmspack/mspack/lzxd.c))
(UEViewer modified sys_read function [https://github.com/gildor2/UEViewer/blo ... on.cpp#L90](https://github.com/gildor2/UEViewer/blob/master/Unreal/UnCoreCompression.cpp#L90))

The script used is the following:

```
comtype xmemdecompress

get ZSize long
get Size long
math ZSize &= 0x7fffffff
clog result Offset ZSize Size

```

And the file is: [https://www.mediafire.com/file/5od3897o ... k.dat/file](https://www.mediafire.com/file/5od3897o5bxvkzr/compressed_chunk.dat/file)

For clarification, all other types of files such as savegames decompress perfectly, but all chunk data that I've tried fails. I'm going to try debug or at least identify the problematic lzx blocks, but I thought posting it here would be a good idea in case someone has any clue of what might be happening.  

(Crossposting from ZenHax: [https://zenhax.com/viewtopic.php?f=9&t=15062](https://zenhax.com/viewtopic.php?f=9&t=15062))
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-02T10:47:58+00:00
- Post Title: [HELP] Xmem decompression error with MC360 chunk data

It is standard xmemlzx.  If you use offset + 8 as the starting point, it will work.  I'm not sure what 'Size' refers to, but the decompressed size is 0x21BF of that chunk.
## Post #3
- Username: theunholyone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 20, 2021 4:37 am
- Post datetime: 2021-06-09T18:56:38+00:00
- Post Title: [HELP] Xmem decompression error with MC360 chunk data

Yes, it is. The issue is that the quickbms implementation that doesn't rely on the XDK (which is the one used in Linux and Mac) fails to decompress the file.
