## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T19:46:44+00:00
- Post Title: Using offzip on archives

If I can extract an archive using offzip, does that mean writing the bms script would be easy?
It should probably give me some clues that make it easier.

(I don't know how offzip works)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-08-08T21:06:26+00:00
- Post Title: Using offzip on archives

well the output gives you the offset to the compressed data AND the sizes of both the compressed and uncompressed data.. so you can use those to look for relevant fields?

is this what you mean? offzip itself can often be used to just extract stuff from an unknown archive if you dont mind that the dumped files have different names (they are offsets)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-08T22:00:40+00:00
- Post Title: Using offzip on archives

Does using offzip immediately tell us the compression used?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-08T22:19:43+00:00
- Post Title: Using offzip on archives

offzip is only zlib
