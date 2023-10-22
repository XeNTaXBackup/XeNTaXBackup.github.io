## Post #1
- Username: danny
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Apr 11, 2011 6:16 pm
- Post datetime: 2012-02-10T12:35:32+00:00
- Post Title: Help me with .pak in game

I need the code for decompress the .pak file

The pak. file is here

[http://www.mediafire.com/?yi8bcj90tyyhxbv](http://www.mediafire.com/?yi8bcj90tyyhxbv)
## Post #2
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-02-11T08:40:22+00:00
- Post Title: Help me with .pak in game

Hi
This quickbms script can unpack the archive
Its very noob cuz i dont know all the things

```
math OFFSET = 0xBCEC
do
 getdstring UNK 0x9
 get NAMESIZE byte
 getdstring NAME NAMESIZE
 get SIZE long
 log NAME OFFSET SIZE
 math OFFSET += SIZE
while OFFSET < ASIZE
```
