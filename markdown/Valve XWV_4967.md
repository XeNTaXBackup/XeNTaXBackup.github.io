## Post #1
- Username: Omnicoder
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Aug 13, 2009 6:42 am
- Post datetime: 2010-09-02T22:17:11+00:00
- Post Title: Valve XWV

Been working on the sound files from Valve's 360 games. 

Here's what I got so far:

```
DWORD magic1 = 4
DWORD magic2 = 48
DWORD magic3 = (known values 156, 172, 192, 324) increases with file size
DWORD magic4 = 2048 (header size?)
DWORD magic5 = (filesize - magic4)
DWORD magic6 = (kv 268288, 204288, 243200, 471040) proportionally increases with file size (double file size doubles this)
DWORD magic7 = -1
DWORD magic8 = 0
DWORD magic9 = 16
DWORD magic10 = 17826305
DWORD magic11 = 1258356736
DWORD magic12 = (known values 6144, 7680, 5632, 2 files of vastly different sizes both had 7680)
DWORD magic13 = (kv 14848, 13312, 13824) (2 files of different sizes both had 13312, bigger files have had smaller numbers)
DWORD magic14 = (kv 20992, 19968)
<more magics, always seem to be similar between files and slightly bigger in bigger files>

At offset of magic4: Always "<" 
```


I'm assuming its somehow related to the WAV file format but haven't really noticed any correlation.
Pretty much shooting in the dark here so any help would be appreciated.

[Example file](http://www.mediafire.com/?5b9kleoooj3byca)
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-09-03T05:37:47+00:00
- Post Title: Valve XWV

I'd say its good bet its XMA and seemingly some blocking/filler in the data. No sign of sample rate values in quick look, possibly held elsewhere or defined differently.
## Post #3
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2010-09-03T13:01:32+00:00
- Post Title: Valve XWV

> Reply from Omnicoder
>
> Been working on the sound files from Valve's 360 games. 

Here's what I got so far:
Code: Select allDWORD id = 1482118688 "XWV " (Xbox Wave (Little Endian) or Valve Wave Xbox (Big Endian))
DWORD magic1 = 4
DWORD magic2 = 48
DWORD magic3 = (known values 156, 172, 192, 324) increases with file size
DWORD magic4 = 2048 (header size?)
DWORD magic5 = (filesize - magic4)
DWORD magic6 = (kv 268288, 204288, 243200, 471040) proportionally increases with file size (double file size doubles this)
DWORD magic7 = -1
DWORD magic8 = 0
DWORD magic9 = 16
DWORD magic10 = 17826305
DWORD magic11 = 1258356736
DWORD magic12 = (known values 6144, 7680, 5632, 2 files of vastly different sizes both had 7680)
DWORD magic13 = (kv 14848, 13312, 13824) (2 files of different sizes both had 13312, bigger files have had smaller numbers)
DWORD magic14 = (kv 20992, 19968)
<more magics, always seem to be similar between files and slightly bigger in bigger files>
One thing I noticed: the file seems to be divided into blocks of 2048 B size. Not only the header has 2048=0x800 B:
from 0x800-0x1000 is (I assume) the 1st data packet (the end is "padded" with 0xff Bytes),
from 0x100-0x1800 is then the 2nd data packet (again: filled up with 0xff bytes at the end) .... and so on.
So you have a data size of (magic5=)94208=2048 * 46. If this is correct, then the sample file has 46 data packets
And if you look at the  DWORDS from 0x30(magic12) to 0xe8, then you have there 46 (similar and 'accumulative' looking) entries... so one entry for each of the 46 data packets.

This strongly reminds me of the [DPDS-Chunk](http://msdn.microsoft.com/en-us/library/ee415832%28VS.85%29.aspx) from the xWMA-Format: there you have as well ONE DWORD for each data packet... each entry describes the buffer size needed for the according data packet in an accumulative way. I.e. entry0=size needed for decompressed data packet 0(in the example: 0x2a00), entry1=size needed for decompressed data packets 0 AND 1 ( in the example: 0x4400) and so on.

If this assumption is correct, then the last entry (at Pos. 0xe8) should contain the size of the whole decompressed data of the file... in case of the sample file, this would be 0x3fc00=261120 Byte....  but that's just an assumption   
BTW: at Pos 0x18 (magic6) you have the same value: 0x3fc00=261120 ... so magic6 would be the size of the decompressed data of the file.
## Post #4
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2011-01-14T15:05:43+00:00
- Post Title: Valve XWV

Hi, good work, i wanted to add spanish voices from pc to 360, but i cant do it because i dont know how to work with this audio and to repack the *.360.zip
## Post #5
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-01-04T20:25:58+00:00
- Post Title: Valve XWV

[https://developer.valvesoftware.com/wik ... ile_Format](https://developer.valvesoftware.com/wiki/XWV_File_Format)
## Post #6
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-03-01T18:31:46+00:00
- Post Title: Valve XWV

Any progress?
## Post #7
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-05-19T18:17:55+00:00
- Post Title: Valve XWV

> Reply from Gromber
>
> Any progress? someone interested in add pc voices to 360 english version?
## Post #8
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-10-11T18:53:07+00:00
- Post Title: Valve XWV

I can convert valve XWB to xma to use with towav thanks to XMA transform script, but now i want to know how convert xma created from .wav with xma2encode to XWB to try to test in the console.

Thanks
## Post #9
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-12-20T20:22:29+00:00
- Post Title: Valve XWV

any idea?
## Post #10
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2013-02-01T19:28:46+00:00
- Post Title: Valve XWV

> Reply from Gromber
>
> any idea?
