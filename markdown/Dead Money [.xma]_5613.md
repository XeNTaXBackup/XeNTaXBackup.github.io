## Post #1
- Username: FlyingShip
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 24, 2010 11:55 pm
- Post datetime: 2010-12-23T10:12:53+00:00
- Post Title: Dead Money [.xma]

Hey,
please help me with that file.
The header looks like a correct:


But "towav" and "xmaencode" don't convert it.
What's wrong?
[mus_dlc01_american_swing.xma](http://fileshare.in.ua/4008216)
## Post #2
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-12-23T17:29:20+00:00
- Post Title: Dead Money [.xma]

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: FlyingShip
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 24, 2010 11:55 pm
- Post datetime: 2010-12-23T20:13:00+00:00
- Post Title: Dead Money [.xma]

Thanks, works great.
Is there a bms script for that header replace? Or something else?
## Post #4
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-12-23T23:37:18+00:00
- Post Title: Dead Money [.xma]

You have to cut the old header manually fist. Deleted everything before the start of the stream (six bytes for the string fc01c001). Then there is a XMA header script in Alpha23s thread.
## Post #5
- Username: FlyingShip
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 24, 2010 11:55 pm
- Post datetime: 2010-12-24T15:48:18+00:00
- Post Title: Dead Money [.xma]

Thanks again, it's clear for me now.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-24T16:28:00+00:00
- Post Title: Dead Money [.xma]

Or just use my script here: [viewtopic.php?f=13&t=4450&p=46390#p46390](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=46390#p46390)
I've written it once to manipulate the extracted XMA files from FSB containers to toWAV-decodable files, but obviously it works on these files too.
