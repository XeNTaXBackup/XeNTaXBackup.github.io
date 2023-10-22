## Post #1
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-20T05:34:32+00:00
- Post Title: Compressed Texture Help

Does anyone recognize this compression?
[hero_mouth_24.rar](https://xentaxbackup.github.io/file/370_hero_mouth_24.rar)
## Post #2
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-20T05:35:44+00:00
- Post Title: Compressed Texture Help

This should be what it decompresses to.
[hero_mouth_low.rar](https://xentaxbackup.github.io/file/371_hero_mouth_low.rar)
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-07-21T01:55:08+00:00
- Post Title: Compressed Texture Help

How can the larger file be the compressed file?  I think you have it backwards.
## Post #4
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-21T03:16:21+00:00
- Post Title: Compressed Texture Help

> Reply from brienj
>
> How can the larger file be the compressed file?  I think you have it backwards.

There are two types of textures-- a low res and a high res.  The high res compression has not been figured out.
## Post #5
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-21T04:49:45+00:00
- Post Title: Compressed Texture Help

Yep. The game stores them both in one file. The low-res is plain uncompressed dds. This was easy to extract. But we're having the a horrible time figuring out the Hi-res section. 

The game does dump them out to a cache. But a lot of times it also mixes it with any decal textures you have.

I also suspect it's some type of RLE compression due to being able to see bits of the texture still present.
## Post #6
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-07-27T09:59:00+00:00
- Post Title: Compressed Texture Help

Turns out it's LZO compression. But without headers.
