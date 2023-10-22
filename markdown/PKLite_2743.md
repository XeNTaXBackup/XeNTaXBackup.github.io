## Post #1
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2007-08-08T04:01:31+00:00
- Post Title: PKLite

Hi guys,

Does anyone have the source code to something that can decompress PKLite compressed exe's?  I know that Tron can handle them, as can UNP and Unpklite - but I'm sure someone out there's worked out how it works and has rolled into a project of their own...it would make me very happy!

Thanks in advance!
## Post #2
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2007-08-08T08:01:02+00:00
- Post Title: PKLite

I think the only way to reliably uncompress them is to run them (maybe through some kind of x86 emulator) and intercept the final far jump to the "real" program entry point.
At least that's how UNP etc. do it.
