## Post #1
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-10-24T08:02:13+00:00
- Post Title: SCRT^ Format , what? O_x

Anyone has any kind of idea what this is for a kind of format?
i was browsing through a PSP rom file (smart bomb i think)
and stumbled upon something with a header that was SCRT^.
byte 8-11 contains a longword with the lenght of the segment (file)
and after that , another SCRT^ mark is found. 

ive tried googling, everything. the Global.PSP is infested with these
SCRT files , and they are very easy to rip thanks to the Length header.
but i have no idea what to make out of these files =o
[garrghh.gif](https://xentaxbackup.github.io/file/470_garrghh.gif)
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-10-25T14:51:04+00:00
- Post Title: SCRT^ Format , what? O_x

Hi mate,

I am unsure what they are - it is more probable that the header is just the SCRT part (not including the ^) - the ^ character may be like a version marker or something.

If I had to take a guess at what it is - I will say its a script of some sort - maybe each SCRT represents a programming method or function.

I didn't really find anything on Google either, but there was one thing called Securt CRT which had to do with communication to a Unix-based system - I don't know if this has any relevance at all but it probably doesn't.

Sorry I can't help further - it doesn't represent anything I have come across before. The hex in the screenshot doesn't really help much either - just looks like some kind of index or something (note the incrementing numbers every 12 or so bytes)

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2005-10-26T11:37:46+00:00
- Post Title: SCRT^ Format , what? O_x

I go for the theory that it is some kind of compiled script file
then, maybe its the level files =O . nothing else makes any sense.
