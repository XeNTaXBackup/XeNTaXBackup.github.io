## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-07-08T11:45:06+00:00
- Post Title: Extract wav from anno?

Could someone refer me to a program that can extract the .WAV file from .ANNO files?

[http://www.sendspace.com/file/8nvz8b](http://www.sendspace.com/file/8nvz8b)
## Post #2
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-07-10T19:52:38+00:00
- Post Title: Extract wav from anno?

Here's the properties of the files:

[http://www.annosoft.com/sapi_lipsync/do ... ormat.html](http://www.annosoft.com/sapi_lipsync/docs/group__anno__format.html)
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-10T23:40:07+00:00
- Post Title: Extract wav from anno?

It's clear that the wav is not actually in the .anno, it is only referenced from it.  It's too small for it to be otherwise.
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-07-11T03:06:16+00:00
- Post Title: Extract wav from anno?

Blagh, turns out they're all inside a rather massive FSB file. Unfortunately all the tools for FSB's that I found are annoyingly formatted and unusable to an idiot like me (meaning they're stuck in .class thingies). Any ideas?
## Post #5
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-29T13:52:39+00:00
- Post Title: Extract wav from anno?

My guess is that you have to compile them. I'm not a coder, so I could be completely wrong.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-31T03:27:41+00:00
- Post Title: Extract wav from anno?

.class files are already compiled Java, you need a JVM to run them.
A few (non-Java) programs to try: towav ([http://www.ctpax-x.ru/index.php?goto=files&show=24](http://www.ctpax-x.ru/index.php?goto=files&show=24)), fsbext ([http://aluigi.org/papers.htm](http://aluigi.org/papers.htm))

If you just need to split up FSBs, so that they can be played in vgmstream ([http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html)) or something, try my program fsbii ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)).
