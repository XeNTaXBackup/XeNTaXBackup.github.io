## Post #1
- Username: Taarna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 22, 2008 7:36 pm
- Post datetime: 2008-04-22T12:06:43+00:00
- Post Title: CCS File - Some progress

First of all, you should know I am not a programmer. Even my HTML is old these days. That said, I'll continue to the subject in question.

It would seem the TMP graphic format within these CCS files is not far off base, if at all, from CyberConnect2's older form from the previous set of .hack games, CMP. In a fit of tired boredom, and some frustration of finally getting TO the CCS files, only to be stopped there, I renamed one of the CCS files from the root directory of the CVM to data.bin and let a program I had laying around, .hackpics, have a go at it. Lo and behold, before my eyes is the default desktop background, displayed perfectly. I went on to extract all of the desktop images and CrimsonVS cards, for fun. It all worked, excellently.

So, I figure... .hackpics comes with source, maybe some nice folks here can figure out how this works, and perhaps even go on to extract the models. Well, it would be nice, there's so many I'd like to sit and examine.... Anyway!

[.hackpics download](http://www.zophar.net/utilities/download/hackpics.zip)

So, if you haven't done this before, data.cvm is actually simple to deal with. Copy to harddrive, rename to data.iso and open with MagicIso. Other programs may work, but I can say that Daemon Tools did not, in this case.

Now, not everything, of course, is graphics data... But the MENU folder or the CRIMSONVS folder is a good source of 2D data, and for CCS that contain basic 3D data, try the EQ folder.

Good luck! I do hope I've been helpful, and please let me know if there's anything I can add, or files I can provide.
## Post #2
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2008-04-28T20:00:32+00:00
- Post Title: CCS File - Some progress

> So, I figure... .hackpics comes with source, maybe some nice folks here can figure out how this works, and perhaps even go on to extract the models.

I've been researching the CCS files myself for some time. (See the several threads on CCS files on this forum)
A single CCS files contains many other files (model, animation, textures etc) and what this program does is just to look for image data (They all start with CCCC0300) and the corresponding palette data (CCCC0400). 

Therefore, it can't be really used to get any info on models, but it seems that model files are called MDL by the CCS files and start with CCCC0800(at least that's what I think).
However, even though that may be true, the content of these MDL files makes no sense to me at all. No Vertex count, individual dwords form nonsensical Float numbers and there seems to be some weird recurring byte pattern.
In the end, I'm just too inexperienced so I gave up for now.
