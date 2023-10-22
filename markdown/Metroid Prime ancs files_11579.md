## Post #1
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-06-08T02:42:02+00:00
- Post Title: Metroid Prime ancs files

I've been trying for a while to crack the ANCS format for Metroid Prime, it contains scenegraph information for models, such as it's skeleton (CINF), skinning(CSKR) and animations (ANIM), and I have it mostly figured out, however there is one section that I can't seem to figure out. It's the PAS4 section, it seems to define particles and I can see a definite pattern, however I can't seem to make the pattern fit the header.
I've attached a few examples of ANCS with PAS4.

Any help would be appreciated.


As you can see, there is a definite pattern, but I can never make it work for some reason.
[ANCS.zip](https://xentaxbackup.github.io/file/7449_ANCS.zip)
## Post #2
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-06-13T03:58:52+00:00
- Post Title: Metroid Prime ancs files

I've been taking a closer look at PAS4 and there seems to be a fairly static size depending on the first integer after the magic, will need to investigate further before making that assumption though.
Also, there is a list of SWHC IDs in some of the ANCS files I've looked at, and I've now accounted for that as well.
## Post #3
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-06-16T01:37:50+00:00
- Post Title: Metroid Prime ancs files

Anyone?
Please I really need help with this.
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-06-17T12:44:00+00:00
- Post Title: Metroid Prime ancs files

Perhaps MrAdults would know, Noesis can extract the models.
## Post #5
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2016-06-26T06:06:08+00:00
- Post Title: Metroid Prime ancs files

Wow, I forgot about this thread, ANCS has long since been figured out, as a matter of fact we now have the ability to extract every animation in the game as well.
