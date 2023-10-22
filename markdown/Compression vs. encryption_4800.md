## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-24T21:59:40+00:00
- Post Title: Compression vs. encryption?

[out]
## Post #2
- Username: shekofte
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-24T22:35:17+00:00
- Post Title: Compression vs. encryption?

Compressed files can't be compressed considerably again.
Also the histogram should be quite uniformly distributed.
## Post #3
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-24T23:04:04+00:00
- Post Title: Compression vs. encryption?

[out]
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-24T23:39:59+00:00
- Post Title: Compression vs. encryption?

If you take the simplest case of a XOR encryption with only 1 byte the distribution stays uniform of course.
That's why these ones are easy to come by without any disassembling. Series of zeros become series of the xor byte.

In general if you see runs of data in the file you can bet it (or at least that part) isn't compressed.

More sophisticated encryptions use a function to modify the xor key after each round similar to a pseudo-random number generator. Thus it depends on the function that is used how random the output is.

It would be really interesting to investigate if there is a way to detect encryption and compression with static mathematical analysis.
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2010-07-25T01:34:56+00:00
- Post Title: Compression vs. encryption?

[out]
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-07-25T12:35:36+00:00
- Post Title: Compression vs. encryption?

Well that's pretty hard. You might try scanning the exe with [http://www.peid.info/](http://www.peid.info/) and it's Krypto plugin.
