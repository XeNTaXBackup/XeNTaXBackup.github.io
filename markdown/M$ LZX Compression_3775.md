## Post #1
- Username: xeriuz
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 09, 2009 7:19 pm
- Post datetime: 2009-10-11T21:22:28+00:00
- Post Title: M$ LZX Compression

Hello! Someone, please, send me a pm link to xcompress32.dll. It is very necessary. Already a month unsuccessfully looking for. There is a huge desire to explore the resources x360 games. Thank you! 
P.S. We have successfully written XBOX360 ISO Creator!   
Sorry for my bad English.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-11T22:22:46+00:00
- Post Title: M$ LZX Compression

I guess you are referring to xcompress.lib which is available only in the xbox 360 sdk where are linked the XMemCompress and XMemDecompress functions
## Post #3
- Username: xeriuz
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 09, 2009 7:19 pm
- Post datetime: 2009-10-11T22:35:00+00:00
- Post Title: M$ LZX Compression

I'm not a programmer. I have xdk, but I do not know how to use a static library. I failed to compile xcompress.lib and xcompress.h in a dynamic library. If you can help, I'll be very grateful.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-12T11:32:32+00:00
- Post Title: M$ LZX Compression

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: xeriuz
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 09, 2009 7:19 pm
- Post datetime: 2009-10-12T12:07:05+00:00
- Post Title: M$ LZX Compression

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-10-12T14:32:11+00:00
- Post Title: M$ LZX Compression

Is it possible to provide xcompress.h file? How can we call xcompress.dll from VB? Thanks a lot.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-12T15:16:12+00:00
- Post Title: M$ LZX Compression

@xeriuz
XMemDecompress is already supported in QuickBMS from version 0.2.4 released over 20 days ago

@zeeh
re-read the 2nd and 3rd post of this thread
## Post #8
- Username: xeriuz
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 09, 2009 7:19 pm
- Post datetime: 2009-10-13T19:04:44+00:00
- Post Title: M$ LZX Compression

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-13T19:19:15+00:00
- Post Title: M$ LZX Compression

if you use "clog NAME 0 SIZE SIZE" you will get an error for sure because you tell quickbms that the uncompressed data has the same size of the compressed one :)

for the big endian mode it's enough to place "endian big" at the beginning of the script (you can change the endianess in any moment).

anyway in this case there is something missing because the file is not a simple raw compressed data but I see something like an header.
the problem is that I don't see where starts the lzx data, first because the 32bit values at offset 0x20 and 0x28 "could" be the uncompressed and compressed size but is not possible because the lzx stream doesn't start at offset 0x44.
I have tested some offsets but I get ever an error in XMemDecompress that crashes which means that it's not lzx data
## Post #10
- Username: xeriuz
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 09, 2009 7:19 pm
- Post datetime: 2009-10-13T20:50:34+00:00
- Post Title: M$ LZX Compression

Maybe a used function Transporent Decompress or removed header compression? This file was taken from the game Overlord (X360). It's a shame. I was hoping that unpack and pack it will be possible with the help of MS LZX Compression
## Post #11
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2010-09-05T15:16:55+00:00
- Post Title: M$ LZX Compression

Please anybody upload xcompress.lib somewhere
## Post #12
- Username: nerdyluke
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 29, 2013 11:46 pm
- Post datetime: 2016-09-20T12:14:33+00:00
- Post Title: M$ LZX Compression

> Reply from JeffT
>
> Please anybody upload xcompress.lib somewhere
Same here, can anyone point me to xcompress.h/xcompress.lib/xcompress.dll please? Thanks
## Post #13
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-09-20T12:24:28+00:00
- Post Title: M$ LZX Compression

> Reply from nerdyluke
>
> JeffT wrote:Please anybody upload xcompress.lib somewhere
Same here, can anyone point me to xcompress.h/xcompress.lib/xcompress.dll please? Thanks
Unfortunately no, these are propriety, part of Microsoft's Xbox 360 SDK. The libraries themselves are only available to Microsoft's partners with licensing rights to use them. If you wish to have these, I recommend you contact Microsoft themselves. Such content is not permitted on this forum. As a result, this thread serves no purpose and will be locked.

Cheers.
