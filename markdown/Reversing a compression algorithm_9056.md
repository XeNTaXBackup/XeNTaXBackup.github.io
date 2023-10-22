## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-09T19:58:27+00:00
- Post Title: Reversing a compression algorithm

Any step-by-step tutorial on looking at stepping through an exe while it's running and figuring out where it's decompressing an archive?

And how to determine what it's doing at a particular block is actually a decompression algorithm?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-06-13T07:03:51+00:00
- Post Title: Reversing a compression algorithm

> Reply from finale00
>
> ...and figuring out where it's decompressing an archive?Provided that it is possible to load (and start) the exe via debugger you could try to find the data to be decompressed in RAM and set a memory breakpoint on it. After pressing "run" in the debugger the breakpoint should be hit and the address of the decompressing code revealed.

It might be required to set several (normal) breakpoints in the exe to get the data loaded which shall be decompressed .
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-13T17:34:09+00:00
- Post Title: Reversing a compression algorithm

I'm using ollydbg. Is that what most people use?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-06-13T20:10:24+00:00
- Post Title: Reversing a compression algorithm

> Reply from finale00
>
> I'm using ollydbg. Is that what most people use?I don't know but imho it's one of the best "free" debuggers (maybe the best). Another choice could be IDA but that's not for free. (This is what most professionals use I think.)

(Sometimes I'm using Cheat engine which has a useful memory BP feature but its focus is more on game cheating than on debugging.)
