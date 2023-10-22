## Post #1
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-10-15T11:45:22+00:00
- Post Title: Doom 3 BFG - sound.idxma ??

Please help me to convert it to ogg and back if possible ?

```
https://dl.dropbox.com/u/38234344/TEST%20SOUND.rar
```
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-10-15T18:00:51+00:00
- Post Title: Doom 3 BFG - sound.idxma ??

how did you unpack it?
## Post #3
- Username: ViToTiV
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 11, 2009 12:38 am
- Post datetime: 2012-10-17T08:15:34+00:00
- Post Title: Doom 3 BFG - sound.idxma ??

michalss, аnd conversely, I want to convert ogg to idxma, for replace original sound)
it seems like a normal xWMA sound (xWMAEncode.exe tool), but different header.

OrangeC,
file structure:

4 byte - unknown, probably header
4 byte - offset to files table (big endian)

files table:
4 byte - files count (big endian)
for each file:
4 byte - filename length (little endian... what a hell?  )
filename
4 byte - file begin offset (big endian)
4 byte - file length (big endian)
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-10-17T08:45:32+00:00
- Post Title: Doom 3 BFG - sound.idxma ??

Can you help me with it also alpha is looking into the format. My problem is i have complete dabbing on PC but i want to conversion to X360.  So i you can help it would be great as i can also spend something for it
