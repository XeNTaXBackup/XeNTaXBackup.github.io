## Post #1
- Username: snakum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 08, 2005 9:06 pm
- Post datetime: 2005-09-08T13:19:00+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

hello 

i need a software or something to open .tex for this game     

this is the file 

[http://www.megaupload.com/?d=01K0685A](http://www.megaupload.com/?d=01K0685A)

ps: my english is weak sorry
## Post #2
- Username: snakum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 08, 2005 9:06 pm
- Post datetime: 2005-09-09T07:38:31+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

nobody can help me????
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-09-09T08:23:25+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

Patience is a virtue. 

I have looked at the file breifly, and it is some kind of image format. Have not figured out what format yet.
## Post #4
- Username: snakum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 08, 2005 9:06 pm
- Post datetime: 2005-09-09T09:15:03+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

ok thanks man i will wait
## Post #5
- Username: snakum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 08, 2005 9:06 pm
- Post datetime: 2005-09-10T07:47:14+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

i don't know which software can open that i tried so many but now i really need ur help
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-11T13:54:36+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

OK the structure is something like this...

```
| Brian Lara International Cricket 2005 (PS2) *.tex |
+---------------------------------------------------+

// This format is an image which stores many mipmaps.
// Each mipmap is half the dimensions of the previous image.
// eg if the first mipmap is 256*128, the next one is 128*64, then 64*32, etc.

2 - Image Width?
2 - Image Height?
2 - Unknown (5)
2 - Number Of Mipmaps (4)

// for each mipmap
  X - Pixel Data
  
8? - Unknown (there are 8 bytes somewhere here, earlier, or divided for each mipmap)

// for each color (256)
  1 - Red
  1 - Green
  1 - Blue
  1 - Alpha (unused?)
```


I havn't coded anything up yet though, so I can't fully confirm it, but it seems pretty reasonable.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: snakum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 08, 2005 9:06 pm
- Post datetime: 2005-09-13T07:45:15+00:00
- Post Title: Brian Lara international Cricket 2005 [Ps2] .tex

thanx a lot for ur help tell me if u coded something i m still waiting
