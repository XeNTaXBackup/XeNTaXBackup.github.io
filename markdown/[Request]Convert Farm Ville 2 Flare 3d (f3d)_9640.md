## Post #1
- Username: caramel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 12, 2011 2:47 am
- Post datetime: 2012-09-15T21:49:17+00:00
- Post Title: [Request]Convert Farm Ville 2 Flare 3d (f3d)

[http://www.flare3d.com/blog/2012/09/06/ ... y-flare3d/](http://www.flare3d.com/blog/2012/09/06/farmville-2-powered-by-flare3d/)


[http://www.flare3d.com/](http://www.flare3d.com/)


I think that it is encrypted. header files has changed from the original

f3d export with 3ds max



farm ville model




farm ville 2 asset (f3d/jxr)

[http://www.mediafire.com/?ild59gb879ag6y7](http://www.mediafire.com/?ild59gb879ag6y7)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-15T23:03:05+00:00
- Post Title: [Request]Convert Farm Ville 2 Flare 3d (f3d)

It's just compressed with zlib, but I don't know where the size is.
When I run it through offzip it tosses out something nice but I want to decompress it in noesis.

But the c3d's are putting a different format so they likely went with a different one.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-16T00:05:35+00:00
- Post Title: [Request]Convert Farm Ville 2 Flare 3d (f3d)

you can use noesis like offzip.
just look at my example for the zlib tutorial,

```
    decompSize = rapi.getInflatedSize(cmpData)
    decompData += rapi.decompInflate(cmpData, decompSize)
    bs.seek(0, NOESEEK_ABS)
    bs = NoeBitStream(decompData, NOE_LITTLEENDIAN)
```
