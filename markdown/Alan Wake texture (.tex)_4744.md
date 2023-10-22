## Post #1
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-07-12T18:40:00+00:00
- Post Title: Alan Wake texture (.tex)

The game use textures with .tex extension. The header(32byte) contain the dimensions etc, but I'm 100% sure, that this is a DDS without header. But these files are compressed, and I don't know how. Maybe LZO, but I had no luck with that.
[tex.zip](https://xentaxbackup.github.io/file/3230_tex.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-12T19:20:48+00:00
- Post Title: Alan Wake texture (.tex)

looks like a standard xbox swizzled dds.
if you make a header for it you can use the sdk to unswizzle the image.
## Post #3
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-07-14T13:24:30+00:00
- Post Title: Alan Wake texture (.tex)

But how? The Xbox360 SDK already have.
## Post #4
- Username: Hamidvip
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Jul 31, 2011 3:52 pm
- Post datetime: 2014-05-26T11:45:38+00:00
- Post Title: Alan Wake texture (.tex)

> Reply from chrrox
>
> looks like a standard xbox swizzled dds.
if you make a header for it you can use the sdk to unswizzle the image.

How do I convert tex?
What a tool?
