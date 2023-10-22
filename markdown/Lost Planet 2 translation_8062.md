## Post #1
- Username: Marusero
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jan 15, 2012 4:12 am
- Post datetime: 2012-01-16T13:08:30+00:00
- Post Title: Lost Planet 2 translation

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Marusero
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jan 15, 2012 4:12 am
- Post datetime: 2012-01-17T23:21:09+00:00
- Post Title: Lost Planet 2 translation

Anyone?
## Post #3
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2012-01-18T20:24:02+00:00
- Post Title: Lost Planet 2 translation

What I got so far (probably won't continue):

New line character: 0x0A (be careful when editing text in windows, it will add another type of new line character: 0x0D if I remember correctly)

Sometimes there are DUMMY or HARDUMMY parts, probably placeholders

String data structure (after, what looks to be, the header)

for each string:

4 bytes 0x00 (not always 4 bytes?)
x byte Pascal string



Suggestion:
Edit the text manually with a hex editor (make a string a byte longer than it was and test it on the console
maybe there is no description about the offsets in the header, but there probably is   )
