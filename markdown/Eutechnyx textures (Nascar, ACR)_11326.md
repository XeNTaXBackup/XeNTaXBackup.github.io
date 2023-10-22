## Post #1
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-16T19:48:26+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

Using aluigi's [nascar_2013_arcc_files.bms](http://aluigi.altervista.org/papers/bms/others/nascar_2013_arcc_files.bms) script, I modified it a bit to extract only textures, and to add the missing DDS header.
UPDATE: The first 2 isses were solved thanks to deepshit.
1. Some textures are fine, some have interleaved black lines, others have black lines in mipmaps
2. Most files are bigger than what you would expect considering texture resolution, compression, and mipmap count - I'm thinking this could be related to the first issue



Below are links to a few samples and the modified script.

[Original_textures.zip](https://mega.co.nz/#!Sc1FQIYa!A-zwsfNoQgkNOIJItcDCaZrOncRjM0fbfQfHSfa_dCA)
[Rebuilt_header.zip](https://mega.co.nz/#!LJ8mzCxb!k0S97XRmnuNrAzwvIJgWCj5s3qePOFFq4qA0Lscep3w)
[nascar_13-14_textures.zip](https://xentaxbackup.github.io/file/7137_nascar_13-14_textures.zip)
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-03-16T20:32:04+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

They seem like xbox360 swizzled dds.
This might be a help :
[viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-17T08:50:25+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

I'm not very familiar with swizzling (just have a basic idea) but could that really be the case considering that
a. these are from a PC game
b. only maps and mipmaps smaller than 64px are affected
## Post #4
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-03-17T10:04:49+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

Xbox swizzle algorithm aligns textures on 4KB and because of that any texture smaller than 128px becomes like what you see.
In your case I guess the textures are just aligned for swizzling but not swizzled.
that makes it easy to rebuild the textures.

Here is how : (for size < 128)
1.Remove the header (first 24 bytes)
2.Each mipmap takes : ((Width + 3)/4)*((Height + 3)/4) * blockSize Bytes (DXT1 blocksize = 8 and DXT3|5 blockSize = 16)
3.All parts are aligned to 256bytes.you should calculate mipmap pitch (Width /4 *  blocksize) and copy that amount until the end of mipmap.
4.Now the mipmap is constructed. Repeat for other mipmaps.

There might be some program to do it but I'm not aware of it.
## Post #5
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-17T22:26:13+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

Thanks, #3 really helped.
It turns out DXT1 lines are aligned by 256 bytes and DXT5 by 512 bytes, so it's related to the block size.
I also found that there's a block*1024 byte alignment for each mipmap (8192 for DXT1 and 16384 for DXT5).

I've updated the script to extract DXT1, DXT3 and DXT5 maps properly.
Next I'll add support for uncompressed textures.


P.S. I've seen that formula before on [msdn](http://msdn.microsoft.com/en-us/library/windows/desktop/bb205578%28v=vs.85%29.aspx) but I've never undestood the logic behind it.
I mean, for a mipmap of 128x64 compressed with DXT1 the formula becomes (128+3)/4 * (64 + 3)/4 * 8 = 4388.5, which is clearly not true because the mipmap size is 4096 bytes. So what gives?
## Post #6
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-03-18T08:08:35+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

> Reply from Chipicao
>
> 
I also found that there's a block*1024 byte alignment for each mipmap (8192 for DXT1 and 16384 for DXT5).
That's exactly according to formula on #1.

> Reply from Chipicao
>
> 
P.S. I've seen that formula before on msdn but I've never undestood the logic behind it.
I mean, for a mipmap of 128x64 compressed with DXT1 the formula becomes (128+3)/4 * (64 + 3)/4 * 8 = 4388.5, which is clearly not true because the mipmap size is 4096 bytes. So what gives?
(128+3) / 4 =32
(64 +3)  /4  =16
32 * 16 = 512
512 * 8 = 4096

The division doesn't calculate floating points
## Post #7
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-18T08:57:03+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

> Reply from deepshit
>
> That's exactly according to formula on #1.No, it's blockSize*1024 regardless of mipmap size.

> Reply from deepshit
>
> The division doesn't calculate floating points Thanks, that explains it.
## Post #8
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-18T21:16:18+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

I have updated the script once more:
- support for A8R8G8B8 DDS textures
- extension is always replaced with .dds
- textures are extracted in a folder with the same name as the ARC file

That should do it. If anyone finds other issues please let me know.
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-27T15:38:40+00:00
- Post Title: Eutechnyx textures (Nascar, ACR)

I have started researching textures from Auto Club Revolution.

As opposed to Nascar, they are already extracted in .tex files, but the format is similar. There are no more alignments and each mip-map is individually compressed with zlib.   
Here's a script I made to convert them to normal DDS. It supports DXT1-5, A8R8G8B8 and an additional G16B16 type.
[ACR_tex_conv.zip](https://xentaxbackup.github.io/file/7138_ACR_tex_conv.zip)
