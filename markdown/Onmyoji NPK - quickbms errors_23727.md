## Post #1
- Username: UsoppFanGirl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Apr 08, 2021 11:13 pm
- Post datetime: 2021-04-09T22:12:23+00:00
- Post Title: Onmyoji NPK - quickbms errors

All was swell and dandy unpacking my Onmyoji npk file when i got hit with a "memory allocation error" on Quickbms. I'm on a laptop with shitty CPU, so it figures. My family has a few other computers (not laptops), but I dont know if they have the memory required to unpack these files. Does anyone here know how much memory at minimum a computer would need to unpack?
## Post #2
- Username: UsoppFanGirl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Apr 08, 2021 11:13 pm
- Post datetime: 2021-04-09T22:33:37+00:00
- Post Title: Onmyoji NPK - quickbms errors

Quickbms gave me some errors while i was trying to unpack some onmyoji npk files. 
These were the errors:

Error: the compressed zlib/deflate input is wrong or incomplete (-3)
Info:  algorithm   1
       offset      0000000000000000
       input size  0x0000000002e30fb8 48435128
       output size 0x00000000000032fa 13050
       result      0xffffffffffffffff -1

Error: uncompressed data (-1) bigger than allocated buffer (48435000)
       It usually means that data is not compressed or uses another algorithm

Is there any way to fix this error?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-10T08:48:47+00:00
- Post Title: Onmyoji NPK - quickbms errors

First of all, don't create duplicate topics for the same case.

As for your first issue, memory allocation really depends on the archives you are trying to unpack.
If the archives are big, then you need a lot of memory.

As for zlib issue, it may be caused, because some custom zlib routine was used to pack data
or because NPK file format has changed and script may be outdated.
## Post #4
- Username: UsoppFanGirl
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Apr 08, 2021 11:13 pm
- Post datetime: 2021-04-12T02:34:22+00:00
- Post Title: Onmyoji NPK - quickbms errors

my archives are only around 90 mb and 33 mb, which I don't think would take up a lot of memory, although I'm not sure about that.How can I solve th zlib issue?
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-12T07:10:25+00:00
- Post Title: Onmyoji NPK - quickbms errors

So in my opinion script may be wrong or outdated. You need to ask script's author to adjust it to your files.
