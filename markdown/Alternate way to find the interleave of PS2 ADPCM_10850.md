## Post #1
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-10-06T23:27:22+00:00
- Post Title: Alternate way to find the interleave of PS2 ADPCM?

The thing is I followed the method posted by snakemeat to calculate it by looking for another occurrence of the first 0x10 bytes of data, but it looks like these files from Spongebob Squarepants: The Movie are one of those instances where it doesn't work.

So my question is, is there another way to manually find the interleave of PS2 ADPCM? I can upload samples if need be.
## Post #2
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-10-07T18:45:46+00:00
- Post Title: Alternate way to find the interleave of PS2 ADPCM?

Nevermind, it does work for this game, it's just very... irregular
## Post #3
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-10-07T19:24:59+00:00
- Post Title: Alternate way to find the interleave of PS2 ADPCM?

Ok, nevermind that nevermind post, because I have a new problem now. I KNOW I have the right interleave because the music plays spot on, however, vgmstream is only converting half the song (and yes, I did add the ss2 header beforehand). It's weird because the decoded file is perfect but then it just stops abruptly right dead center of the normal runtime, what could I be doing wrong?


EDIT

Ok, apparently it has something to do with the channels, because when I set it to 1 channel I get a perfect runtime (but i know this game's music is NOT in mono) and when I set it to 3+, I get a shorter runtime, is that supposed to happen?

EDIT#2

Ok, another thing I noticed, apparently you can use the end offset as an interleave. In fact, using snakemeat's method, any thing past the first match for the second 0x10 bytes works as an interleave which, to my knowledge, is unheard of.
