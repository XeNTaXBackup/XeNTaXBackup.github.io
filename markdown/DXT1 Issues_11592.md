## Post #1
- Username: antidote
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Apr 02, 2010 11:37 pm
- Post datetime: 2014-06-13T04:40:46+00:00
- Post Title: DXT1 Issues

I've been trying to write my own png2txtr converter for Metroid Prime, and I have most image formats supported, however DXT1 is giving me some odd swizzling issues,
This is my code so far:

```
    unsigned h = input.get_height();
    unsigned paddedW = (w + 3) & ~3;
    unsigned paddedH = (h + 3) & ~3;
    char*  rgbaBuffer = new char[(w*h)<<2];
    memset(rgbaBuffer, 0, (w*h)<<2);

    int iv =0;
    for (int y = 0; y < h; y++)
    {
        for (int x = 0; x < w; x++)
        {
            png::rgba_pixel pixel = input.get_pixel(x, y);
            rgbaBuffer[(y*(w<<2))+(x<<2) + 0] = pixel.red;
            rgbaBuffer[(y*(w<<2))+(x<<2) + 1] = pixel.green;
            rgbaBuffer[(y*(w<<2))+(x<<2) + 2] = pixel.blue;
            rgbaBuffer[(y*(w<<2))+(x<<2) + 3] = pixel.alpha;
        }
    }

    short* compressedData = new short[(w*h) >> 2];
    tx_compress_dxtn(4, w, h, (const GLubyte*)rgbaBuffer, GL_COMPRESSED_RGBA_S3TC_DXT1_EXT, (GLubyte*)compressedData);
    int stride = input.get_width();
    #define OFFSET(x,y) (((y)/4)*stride+((x)/4)*4)
    Athena::io::BinaryWriter writer(new Uint8[w*h/2], w*h/2);
    writer.setEndian(Athena::Endian::BigEndian);
    writer.writeUint32((int)TXTRFile::DXT1);
    writer.writeUint16(w);
    writer.writeUint16(h);
    writer.writeUint32(1);
    for (int y = 0; y < h; y += 8)
    {
        for (int x = 0; x < w; x += 8)
        {
            for (int t = 0; t < 4; ++t)
            {
                short color;
                int mx = x+(t&1)*4;
                int my = y+(!!(t&2))*4;

                color = compressedData[OFFSET(mx, my)+0];
                writer.writeUint16(color);
                color = compressedData[OFFSET(mx, my)+1];
                writer.writeUint16(color);
                color = compressedData[OFFSET(mx, my)+2];
                writer.writeUint16(color);
                color = compressedData[OFFSET(mx, my)+3];
                writer.writeUint16(color);
            }
        }
    }
    delete[] rgbaBuffer;
    delete[] compressedData;
    writer.save("test.txtr");

```


Here is the image before compression:

And here is the result:


Athena is my IO library I wrote to aid my hacking endeavors for those curious.
