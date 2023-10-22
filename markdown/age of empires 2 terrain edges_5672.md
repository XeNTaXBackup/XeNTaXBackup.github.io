## Post #1
- Username: SFera
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 30, 2010 8:13 am
- Post datetime: 2010-12-30T10:18:37+00:00
- Post Title: age of empires 2 terrain edges

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: SFera
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 30, 2010 8:13 am
- Post datetime: 2010-12-30T18:23:43+00:00
- Post Title: age of empires 2 terrain edges

ok I managed to parse the file

the final structure is as follows:

```
uint32: nr of tiles(31)
for (i=0;i<nr of blendingmodes)
{
  uint32: tilesize(2353, that`s 48*49 pixels);
  31bytes: tileflags(they are all 1);
  4*blocksize bytes which are 32 interleaved tiles representing 1 bit alpha masks, don't know how this is used for
  for (j=0;j<nr of tiles)
  {
    blocksize bytes: the actual tile pixels; starting from the top .. rendered in the isometric tile format
  }
}
```


I used Ida Pro first time i tried to debug this and because of the video mode I just couldn't switch to the debugger. Now I used olly and it worked just fine.

the rendered tiles look like this: 

and the 1bit masks look like this:
## Post #3
- Username: stodds90
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 18, 2011 4:53 am
- Post datetime: 2011-02-25T08:19:48+00:00
- Post Title: age of empires 2 terrain edges

The contents of this post was deleted because of possible forum rules violation.
