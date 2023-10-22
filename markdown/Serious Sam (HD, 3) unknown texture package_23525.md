## Post #1
- Username: 0ther1
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Apr 30, 2020 10:56 am
- Post datetime: 2021-02-27T16:07:51+00:00
- Post Title: Serious Sam (HD, 3) unknown texture package

Textures in Serious Engine 3-3.5 (Serious Sam HD and 3) are either compressed with DXT or uncompressed BGR/BGRA, but some of them have flag "packed". Here's 1024x256 texture exported with Serious Editor (official game tools):
[](https://fastpic.ru/view/114/2021/0227/ea239a7a3ed8296bf8f1a3ac0dd2db17.png.html)
And here what I've got using uncompressed BGRA texture data:
[](https://fastpic.ru/view/114/2021/0227/99fc42c5dee95ebb9a4c5e482a89c405.png.html)
It looks like outlines of same picture but smaller and a whole bunch (also under every smaller copy are even smaller mip-maps but that's expected, they are stored in texture data), on picture I used black background for visibility, in reality there are same alpha channel. I've compared 2 different textures with same size and they have same texture data length so it's unlikely a compression? Also, even textures compressed with DXT can have this flag and will produce mess with just plain DXT decompression. Any ideas?

EDITED:
Never mind, figured it out by disassembling. In short - for BGR/BGRA data separated in blocks, first goes block of every pixel's B color, next G, R and A if has alpha. For DXT compressed almost same, but first goes block of first colors, then block of second colors and block of indices, and DXT3/5 another set of blocks
