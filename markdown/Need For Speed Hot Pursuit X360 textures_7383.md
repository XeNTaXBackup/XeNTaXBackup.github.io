## Post #1
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-09-19T20:17:40+00:00
- Post Title: Need For Speed Hot Pursuit X360 textures

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mnn
- Rank: advanced
- Number of posts: 66
- Joined date: Sun Jul 31, 2011 6:00 pm
- Post datetime: 2011-10-03T08:29:58+00:00
- Post Title: Need For Speed Hot Pursuit X360 textures

In case someone is interested, here's the format:

```
{
    int stuff1[8];
    int textureType; // mask 0x000000FF, 0x52 = DXT1, 0x53 = DX2/3, 0x54 = DXT4/5
    int size;   // 0-12 bits = height (+1), 13-25 = width (+1), 26-31 = flags
    int stuff2;
    int mipmaps; // bits 6-11
}
flag = size >> (13 * 2);
height = ((size >> 13) & 0x00001FFF) + 1;
width = ((size << 19) >> 19 & 0x0000FFFF) + 1;
mipmaps = (temp >> 6) & 0x0000FFFF;
```

If the width is less than 128 pixels, you need to align it to 128 pixels. The additional pixels are just black, they need to be cut out.

Untiling is necessary. I used code from [GTA IV Xbox 360 Texture Editor](http://forum.xentax.com/blog/?p=302) by Frosty (DXTDecoder.ConvertToLinearTexture).

Mipmaps are saved in a very weird way. I strongly suggest to ignore them and manually generate them when exporting to DDS.

This format is used also elsewhere (for example [[X360]NFS Shift textures](http://forum.xentax.com/viewtopic.php?f=18&t=4158))
