## Post #1
- Username: micTronic
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Dec 16, 2020 6:28 am
- Post datetime: 2023-04-25T09:34:29+00:00
- Post Title: Help understanding image format (Cougar engine - Moment of Silence / 15 Days / Overclocked)

Hi,
I am trying to understand some of the images used in point & click adventure games using the Cougar engine:

The Moment of Silence
Overclocked: A history of violence
15 Days

I've been able to unpack the top-level resource files as documented by bacter somewhere on Xentax, but when looking at some .image, .view or .geometry files inside the archives, they contain image data in a format that I haven't yet been able to understand. I have seen a few formats, but I wouldn't call myself an expert.  

A file [like this one](https://www.mediafire.com/file/c6ltyx8nvryb4vi/012_1.zip/file) exists for each scene / view. It contains basically multiple images, starting at the offsets 180, 524540, 557316, 688428, 754000 (these have a small header) and 758108.
The last "image" actually seems to be a depth map as often used for z-hiding in point&clicks, but the others should be actual images. However, their format is really unusual. I can confirm that they are images by visulizing their raw pictures. For example, the first image contains the whole scene, as seen here and compared to an image screenshot from the actual game:

[https://imgur.com/a/RvkA88X](https://imgur.com/a/RvkA88X)
(I skipped a few bytes and interpreted as 32-bit color to make the shape appear more clearly).

The size is 1024 * 512 (also found at offset 64 in the file). The first data block is exactly that many bytes long, but it has these strange white "stripes" (8 byte of data, 8 byte of something else?). The stripes are often, but not always 0xFF. Also, I have no idea what color model is used. Since the ingame image is 32-bit color, and the game uses just 1 byte per pixel, and much of the data is "blank", there has to be some type of compression I assume.

I noticed some floats in the header of the file, and a single float in the image header. I thought that the 16 byte blocks could have something to do with a vector quantization method or wavelets, but there is no codebook / lookup table to be found anywhere. Also, I'm not familiar with such types of encoding.

I am wondering if anyone has seen such a format before, or has an idea how to read it?
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-05-22T06:46:54+00:00
- Post Title: Help understanding image format (Cougar engine - Moment of Silence / 15 Days / Overclocked)

> these strange white "stripes" (8 byte of data, 8 byte of something else?). The stripes are often, but not always 0xFF.

It's [DXT2](https://en.wikipedia.org/wiki/S3_Texture_Compression#DXT2_and_DXT3) ([a.k.a. BC2](https://learn.microsoft.com/en-us/windows/win32/direct3d10/d3d10-graphics-programming-guide-resources-block-compression#bc2)). The 8 byte stripes of 0xFF are fully opaque alpha, and the next 8 bytes is color data (4x4 blocks each, compatible with DXT1 if you skip 8 bytes over the alpha). If you decode starting from @0xB4 with a width wrap of 1024 pixels, you'll get this below.

The raw texture cooker [viewtopic.php?t=16461](https://forum.xentax.com/viewtopic.php?t=16461) can help.
[Cougar Engine Mountain of Silence color 0xB4 DXT2 1024x512.jpg](https://xentaxbackup.github.io/file/23829_Cougar Engine Mountain of Silence color 0xB4 DXT2 1024x512.jpg)
## Post #3
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-05-22T08:52:01+00:00
- Post Title: Help understanding image format (Cougar engine - Moment of Silence / 15 Days / Overclocked)

> The last "image" actually seems to be a depth map

(after some more spelunking) And you're right about that too - displaying 0xB9168 as float32, 512x1024, with a 16.0x factor per pixel and black-body heat colormap:
[Cougar Engine Mountain of Silence depth map 0xB9168 float32 1024x512.jpg](https://xentaxbackup.github.io/file/23830_Cougar Engine Mountain of Silence depth map 0xB9168 float32 1024x512.jpg)
