## Post #1
- Username: FunteX
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Aug 20, 2006 5:45 am
- Post datetime: 2007-02-10T19:47:34+00:00
- Post Title: Insomniac games, and a sort of file hiding

hi there 


theres a question that has annoyed me for long now.
how can files be hidden on a optical media, and still showing that 4 gb is stored on the media?

i'm trying to figure out how Insomniac Games has hidden all the game files in the ratchet and clank series except R&C2. only the boot script, IOP module and the executable is visible, and the rest is hidden.

someone who has seen this before and maybe have a solution on the issue?


thanks in advance
FunteX
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-02-10T19:53:50+00:00
- Post Title: Insomniac games, and a sort of file hiding

Have you set up your browser to see hidden files and folders?
## Post #3
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-02-24T16:03:53+00:00
- Post Title: Insomniac games, and a sort of file hiding

At the risk of thread necro, it wouldn't be extraordinarily difficult.
The files you see are only visible because there's another invisible bit of data that says "File XXX is located at locations XXX-XXXX on the disc. Other file XXX is located at locations XXXX-XXXX. This is usually called a Master Files Table or MFT for short. It's also found in hard disks and most archive formats. Conceivably the developers could have just left entries for the boot sector and executable, etc. and manually had instructions inside the executable to look in specific locations on the disc for what it needs.
