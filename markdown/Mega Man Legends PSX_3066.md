## Post #1
- Username: ShatteredStrife
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 20, 2008 3:30 am
- Post datetime: 2008-06-20T07:22:38+00:00
- Post Title: Mega Man Legends PSX

This is my first attempt at reverse engineering a file format, so my apologies up-front if my questions come across as rather basic.

I've been working on extracting data from the .bin archives on the Mega Man Legends PSX disc. I copied the .bin files from the CDDATA directory over to my machine, took hex editor in hand, and have had some success. At this point I've been able to extract a few images, but something is kind of strange.

The data doesn't seem to be organized in any way that makes sense aside from being divided into regular 2KB chunks. While what seem to be file entries are always aligned to a chunk, the header that accompanies each one is wildly inconsistent. After a month or so of trying various approaches, I've finally gotten to the point where I'm well and truly stuck. I scoured the Internet for info and came across both this forum as well as Mirex's homepage (home of Unmass, which has Mega Man Legends file support).

I'm starting to wonder if there's something fundamentally wrong with my approach, since Unmass can't open any .bin file that I give it. By luck, Ikeness posted a small collection of Legends files that he was working on in a thread here ([viewtopic.php?=&p=19359](http://forum.xentax.com/viewtopic.php?=&p=19359)). Not only are the contents of his .bin file totally different from the one that I copied, but Unmass recognizes it just fine. He also had several other files in the group that are apparently from the disc, but I don't see anywhere on my copy.

About the best I can find is that PSX discs are apparently recorded in CD-ROM XA/Mode-2, are interleaved with 2KB chunks (which sounds familiar from my earlier findings), and can apparently give Windows fits when trying to copy individual files. I've tried using ISOBuster and some other problems that claim to handle that format properly, but they always give me the same result as when I've copied the files manually.

Does anyone have some insight on what's going on here? Very sincere thanks in advance for any help. I've attached both Ikeness' .bin file and the one that I'm able to copy.
[INIT_DAT.zip](https://xentaxbackup.github.io/file/1549_INIT_DAT.zip)
## Post #2
- Username: ShatteredStrife
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 20, 2008 3:30 am
- Post datetime: 2008-06-24T03:47:53+00:00
- Post Title: Mega Man Legends PSX

As a slight update, I've started looking at the starting sectors of consecutive files on the disc with ISOBuster, then ripping the range of sectors that constitute a file with CDRWin. That seems to give me slightly different (better?) results than just copying the files with Windows Explorer. 

For instance, I can copy .str files to my hard drive that way now. The .bin files that I pull over are slightly different, but still nothing like I've seen posted here and certainly still incompatible with a program like Unmass. I've emailed the author of Unmass for info about what he was testing against. His page hasn't been updated since 2007, though, so I'm not sure what my chances of success are there.

Still looking for help with common issues encountered when trying to copy files from a PSX CD. If anyone knows of a good online resource, I'd be in their debt.
