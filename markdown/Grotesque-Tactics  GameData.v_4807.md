## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-07-25T10:51:17+00:00
- Post Title: Grotesque-Tactics  GameData.v

Looks a crypted file i attach the first 10mb's (of 400mb's)
Any idea?
[GameData.v - 10.00MB](http://www.zshare.net/download/78661055e1f0eed6/)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-25T12:14:09+00:00
- Post Title: Grotesque-Tactics  GameData.v

yeah its an easy one i did this when it was still in beta.

```
get size asize
filexor 0x55
string name + .zip
log name 0 size
```
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-07-25T13:58:20+00:00
- Post Title: Grotesque-Tactics  GameData.v

Works great thanks!! i see the 0x55 in the hex code now
55 55 55 55 55 55 55 55
