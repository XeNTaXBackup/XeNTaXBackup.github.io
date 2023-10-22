## Post #1
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2023-06-28T23:12:37+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

Hello,

I've extracted a bunch of DDS textures from Mario + Rabbids: Sparks of Hope, but these particular .dds files can't be opened in any tool I got so far, irfanview, photoshop, noesis, dds converter. My guess is that either Ubisoft did some annoying customization again or the DX10 header extension is currently just not widely supported.

If I interpret the values correctly, its a version 4, 32 bit structure, 8R8G8B8A format. Edit: Nope, this line is wrong, right now no idea what the hell it is.
I've included a screenshot of the first bytes and some sample files. Does anyone know a viewer/editor that can read these?

[https://mega.nz/file/N3wgwZrT#t37sVsZ37 ... iHk9_JAzjI](https://mega.nz/file/N3wgwZrT#t37sVsZ37qlWaPf0x0-B06tPclS11xbi1iHk9_JAzjI) 




SparksOfHope_DDS_Headers.png (10.73 KiB) Viewed 135 times
## Post #2
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-29T09:36:24+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

chr_her_rabbidmario_dress_d.dds:
         dwWidth: 512
        dwHeight: 512
         dwPitch: 53248

Data size is only 73728 bytes, so this can't be a 32-bit raw texture. Not enough bytes (w*h*4).
dwPitch is usually (width * num_channels), so header data doesn't make sense either.
Tried loading with much smaller dimensions, but doesn't look correct.

Stored dxgiFormat is either 174 or 175 (0xAE or 0xAF).  This isn't a valid DX 10 format, valid range is usually 1-99.
Tried changing the dxgiFormat value to something valid, but nothing loaded.
## Post #3
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-06-29T18:58:09+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

But it might help to know the gaming platform first these files came from (desktop, mobile, game console, etc..).
This game is exclusively on Nintendo Switch?  What kind of textures are usually found on this platform?  I'm not familiar with it.
## Post #4
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2023-06-29T20:03:13+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

This game is indeed switch exclusive, using the snowdrop engine afaik.
Today I've downloaded it's predecessor, Mario & Rabbids Kingdom Battle, to see if theres anything interesting in there. Unfortunately these dds files seem to use the same nonstandard format and might not help much for now.
[https://mega.nz/file/Q7oUQJZa#PJK955dyx ... dGd49WyTCw](https://mega.nz/file/Q7oUQJZa#PJK955dyxYiPTbNFY3Xk27Nrtd3l5SJwXdGd49WyTCw)

The texture format should be similar to the one in Ubisofts The Division games, but I can't find anyone who managed to convert those, either.

I saw some models from the older game uploaded on models-resource, so someone must have had success at least. I'll try to DM them and hope they are still active.
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-29T21:16:46+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

It's switch swizzled astc compressed images in dds container. You can open them directly from sdfdata or already extracted with Switch Toolbox.
For example, chr_her_rabbidmario_dress_d: [https://i.imgur.com/0HtTFL9.png](https://i.imgur.com/0HtTFL9.png)
## Post #6
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2023-06-29T21:37:32+00:00
- Post Title: Mario - Sparks of Hope: weird unreadable DDS format

Ah, I'm new to switch toolbox, didn't know there was an image preview window. So I save these out one by one as png then. Lets hope it works for all of em.

There's also a few dds files in the "blendshapes" folders, apparently encoding vertex animation data? Do they support converting these too?
