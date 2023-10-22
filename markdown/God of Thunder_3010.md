## Post #1
- Username: Cheez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 16, 2008 3:45 am
- Post datetime: 2008-04-15T20:51:28+00:00
- Post Title: God of Thunder

It's a pretty old DOS game, old enough that it's now freeware ([here](http://www.adeptsoftware.com/got/)), and something has been eating at me for ages. I can extract the sounds in voc format in any plain old file ripping program, but the format of anything else, including music, eludes me. I'm not sure if the exe files have anything in them, but for sure got.res had the voc files and whatever else may be in there. I hope there's a way to tear this thing apart and discover not only the files but what format they may be in. I have 0 knowledge in this area.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-18T19:48:52+00:00
- Post Title: God of Thunder

Music is Adlib. graphics unknown so far, im investigating.

the problem here is that the mainarchive IS compressed.

however, only the VOX sounds are raw. (because they would gain nothing on the compression anyways)

but the graphics and music score data is compressed. im trying to circumvent it by
running the game in DosBOX and memory dump it, and then scan the raw mem dump.

ill be back.

Edit:
i found out a name of one of the involved in this game is Jason Blochowiak, he happened to have created
an Adlib format named IMF (ID Software Music File) , so my guess is that this is the format they use
for this game aswell.

HOWEVER, i cant rip it out yet =D . im working on it.

graphics files are still a puzzle.
## Post #3
- Username: Cheez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 16, 2008 3:45 am
- Post datetime: 2008-04-18T20:47:45+00:00
- Post Title: God of Thunder

That's awesome, and it told me a few things I never even knew before.
## Post #4
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2008-04-24T00:09:20+00:00
- Post Title: God of Thunder

Hi,
I've made an extractor for the DAT file. The directory is "encrypted" with XORing and the single files are compressed with a variation of the LZSS algorithm.
I'll try to get the code cleaned up and upload it this weekend.
## Post #5
- Username: Cheez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 16, 2008 3:45 am
- Post datetime: 2008-04-29T09:04:39+00:00
- Post Title: God of Thunder

that'd be awesome, thanks.
## Post #6
- Username: Cheez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 16, 2008 3:45 am
- Post datetime: 2008-07-08T19:26:08+00:00
- Post Title: God of Thunder

uh, I take it by the silence that nobody knows enough about it to say anything?
## Post #7
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2008-07-09T03:39:45+00:00
- Post Title: God of Thunder

Some guy named Grom PE has put a complete extractor + source up.

[http://grompe.org.ru/](http://grompe.org.ru/)
## Post #8
- Username: Cheez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Apr 16, 2008 3:45 am
- Post datetime: 2008-07-09T03:56:39+00:00
- Post Title: God of Thunder

oh, thank you very much for that link... I don't know how you found this.
