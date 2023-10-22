## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-23T16:55:38+00:00
- Post Title: Decompressing very large files with unknown output size

How do I work with these files?

My memory usage goes boom when it runs into a file that's like several hundred MB's and once it's done memory usage drops back to like nothing.

What are some techniques I can use?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-23T21:16:36+00:00
- Post Title: Decompressing very large files with unknown output size

> Reply from finale00
>
> What are some techniques I can use?(just a transitory remembrance, didn't use it for a long time:)
maybe "memory mapping" the file could help?

(In WinAPI the function's called CreateFileMapping())
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-02-24T18:25:20+00:00
- Post Title: Decompressing very large files with unknown output size

Can you decompress them in chunks? If so, there's no reason to do the whole file in one shot.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-24T21:20:26+00:00
- Post Title: Decompressing very large files with unknown output size

lol you're right; and the code (I copied off the examples that came with the library) is already decompressing about one MB at a time and writing to a memory stream...
