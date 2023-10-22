## Post #1
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-06T05:04:39+00:00
- Post Title: Zlib compression.....

Can anyone tell me why a compressed file, namely .res files in WWE XXI, will not compress back to their original filesize when using Zlib?  I've tried compression method 9(which is the best compression), using deflateInit2 with every parameter I can think of(including the newest RLE compression) and even recompiling Zlib.dll.  Is there something obvious I'm missing?  Surely, if the original file is compressed with Zlib you should be able to get it back to that size after decompression.  I've tried different versions of Zlib, too.  Any suggestions?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-06-06T19:18:13+00:00
- Post Title: Zlib compression.....

Well, there are a few things to consider: Different compression programs, even compressing using the same method, will often give you different results. Also, were you just decompressing, and then compressing immediately after, or did you edit the decompressed file?
## Post #3
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-06-06T20:17:02+00:00
- Post Title: Zlib compression.....

Just decompressing and immediately compressing.  There is a parameter of Zlib compression I'm just not understanding.
## Post #4
- Username: Storm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon May 23, 2005 3:32 am
- Post datetime: 2005-06-06T20:58:48+00:00
- Post Title: Zlib compression.....

I've noticed some of this when I edit files with MultiEx, the files I'm not editing, when rebuilding the archive, it sometimes gets bigger. I don't really know why it happens or how to fix it in any case. If you find out, please post.

P.S. What programming language are you using? or just command lines?
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-07T07:08:25+00:00
- Post Title: Zlib compression.....

> Reply from Storm
>
> I've noticed some of this when I edit files with MultiEx, the files I'm not editing, when rebuilding the archive, it sometimes gets bigger. I don't really know why it happens or how to fix it in any case. If you find out, please post.

P.S. What programming language are you using? or just command lines?

I think this has something to do with me being an idiot and there being a bug in MultiEx Commander. I have fixed that one though for the next release.
## Post #6
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-06-08T00:09:45+00:00
- Post Title: Zlib compression.....

Nice to hear!
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-06-08T00:17:38+00:00
- Post Title: Zlib compression.....

Sorry, that was me...
