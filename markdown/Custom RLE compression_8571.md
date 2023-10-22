## Post #1
- Username: qbasic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 17, 2012 4:49 am
- Post datetime: 2012-03-16T21:11:15+00:00
- Post Title: Custom RLE compression

Hi.

I have a troubles with some RLE algo. I want to find it's name, if it is public well-known algorithm, or I need compression for it.

Here is reconstructed sources of decompression routine, I can attach samples too.

Compressed data haven't any headers, just RLE data itself. 

May be somebosy meeted it.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T09:06:36+00:00
- Post Title: Custom RLE compression

yeah upload some samples, I will scan them with quickbms to know if the compression algorithm is recognized (it's easier than looking at many source code files).

maybe it's just lzo, that "17" sounds familiar
## Post #3
- Username: qbasic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 17, 2012 4:49 am
- Post datetime: 2012-03-19T10:48:27+00:00
- Post Title: Custom RLE compression

Hm.. Can you tell me, how to recognize compression algo?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T11:32:30+00:00
- Post Title: Custom RLE compression

some can be guessed or you can give just an opinion by watching the data with a hex editor (like zlib).

others can be scanned and then you must check the resulted decompressed files to know if you recognize data with a sense.

anyway if you are interested in quickbms and the comtype scanner:
[http://aluigi.org/quickbms/comtype_scan.htm](http://aluigi.org/quickbms/comtype_scan.htm)
## Post #5
- Username: qbasic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Mar 17, 2012 4:49 am
- Post datetime: 2012-03-19T11:53:31+00:00
- Post Title: Custom RLE compression

Tyvm, its algo # 8.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-19T11:54:28+00:00
- Post Title: Custom RLE compression

COMP_LZO1X, so yes I guessed it correctly :)
