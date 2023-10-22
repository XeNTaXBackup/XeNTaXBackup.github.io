## Post #1
- Username: stulker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 16, 2013 11:15 pm
- Post datetime: 2013-05-16T20:25:35+00:00
- Post Title: help to know compression method name

i need help to know name of compression or if possible code sample, to make my own tool.

my research compression:
at end of file(dword): C5280300 -> offset of file header
19 00 00 00 -> size of compressed header
F2 74 BB FB EE 2E 37 19 7F 94 BD 7A E8 2F A4 19 0A 8E D3 1F 18 09 BD 80 00 -> compressed header

thanks in advance

attached :
file compressed
tool to open compressed file
notes about my research
[archives.rar](https://xentaxbackup.github.io/file/6402_archives.rar)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-21T19:14:10+00:00
- Post Title: help to know compression method name

I launched comtype_scan2.bat/bms against that sequence of bytes you said in your post and the result is that 72.dmp is correct.
So the algorithm is LZAH (src/compression/de_lzah.c in quickbms)
## Post #3
- Username: stulker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 16, 2013 11:15 pm
- Post datetime: 2013-05-22T18:06:36+00:00
- Post Title: help to know compression method name

thanks ,
48.dmp, lzhuf.c too works fine!, but only have decompress u,u


i found lzhuf.c with compress methods if any is interested
[https://github.com/vonj/snippets/blob/master/lzhuf.c](https://github.com/vonj/snippets/blob/master/lzhuf.c)
