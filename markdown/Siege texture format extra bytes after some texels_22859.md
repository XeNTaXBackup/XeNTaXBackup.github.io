## Post #1
- Username: killahtree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 13, 2020 12:00 am
- Post datetime: 2020-10-18T22:25:02+00:00
- Post Title: Siege texture format extra bytes after some texels

I've dumped some textures from the forge archives, and am getting poor results actually displaying them.

They appear oddly in Rawtex, and I've discovered that it has an extra byte beside some texels, I have yet to find an actual pattern to this. But essentially it looks like this:
8 bytes, BC1 texel
1 byte, shit
8 bytes, BC1 texel

It isn't an AB pattern, there can be many texels before the shit byte, or few. Skipping the shit byte gives a normal BC1 texel, but I can't find a way to do that programmatically. Its value doesn't correlate to anything, AFAICT. Sometimes it's zero, others not.

I've attached two textures from the forges, in the event that anyone can help.

Thanks.
[examples.zip](https://xentaxbackup.github.io/file/18855_examples.zip)
