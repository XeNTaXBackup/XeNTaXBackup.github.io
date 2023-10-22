## Post #1
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-12-22T22:59:29+00:00
- Post Title: Nexon .hfs files (Vindictus)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-22T23:02:03+00:00
- Post Title: Nexon .hfs files (Vindictus)

There is a tool here to extract them also this topic already existed please search next time.
[http://www.gamevixenzone.com/gvz/viewforum.php?f=164](http://www.gamevixenzone.com/gvz/viewforum.php?f=164)
## Post #3
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-12-22T23:12:48+00:00
- Post Title: Nexon .hfs files (Vindictus)

Can you maybe upload the tool to another place? I'm registered on that site, but I can't view the tools.
## Post #4
- Username: AzuiSleet
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 17, 2011 4:52 pm
- Post datetime: 2011-01-17T09:09:01+00:00
- Post Title: Nexon .hfs files (Vindictus)

I've posted the information on the format on the wiki., including the tool.

[http://wiki.xentax.com/index.php/Vindictus](http://wiki.xentax.com/index.php/Vindictus)

Many of the particulars are on the page, but the basics are:
- source episode 1
- lots of xors, with the key in filesystem_stdio (packed with Themida)

The last couple unknowns with the format are:
- the name of the archives (likely a 160-bit hash)
- the second-pass signature (likely crc32, xored?)
