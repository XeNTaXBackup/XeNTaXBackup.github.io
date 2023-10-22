## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-04T22:53:06+00:00
- Post Title: Return to Zork FLE file

Thanks to chrrox who figured out the archive format.

Any ideas about a way to view these FLE?

I included both an ingame screenshot as well as the original file.

Thanks
Andy
## Post #2
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-05T02:44:08+00:00
- Post Title: Return to Zork FLE file

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-12T18:35:08+00:00
- Post Title: Return to Zork FLE file

Return to Zork was made using the MADE engine. ScummVM is able to read that engine, but there's no outside viewer for file formats. 

There is code at this website (I think probably the graphics code)

[http://scummvm.svn.sourceforge.net/view ... ines/made/](http://scummvm.svn.sourceforge.net/viewvc/scummvm/scummvm/trunk/engines/made/)

I included a raw FLE file in the previous post in this topic. Hopefully there is someone out there that is able to use that code to make a viewer for that format outside of the game.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-17T05:06:57+00:00
- Post Title: Return to Zork FLE file

Yes, this is the code that should do the trick, someone adept in C might be able to whip up an extractor/converter. 

From resource.cpp:

```
        // Loads a "raw" picture as used in RtZ, LGoP2, Manhole:N&E and Rodney's Funscreen

        Common::MemoryReadStream *sourceS = new Common::MemoryReadStream(source, size);

        _hasPalette = (sourceS->readByte() != 0);
        byte cmdFlags = sourceS->readByte();
        byte pixelFlags = sourceS->readByte();
        byte maskFlags = sourceS->readByte();
        uint16 cmdOffs = sourceS->readUint16LE();
        uint16 pixelOffs = sourceS->readUint16LE();
        uint16 maskOffs = sourceS->readUint16LE();
        uint16 lineSize = sourceS->readUint16LE();
        /*uint16 u = */sourceS->readUint16LE();
        uint16 width = sourceS->readUint16LE();
        uint16 height = sourceS->readUint16LE();

        if (cmdFlags || pixelFlags || maskFlags) {
                warning("PictureResource::loadRaw() Graphic has flags set (%d, %d, %d)", cmdFlags, pixelFlags, maskFlags);
        }

        _paletteColorCount = (cmdOffs - 18) / 3; // 18 = sizeof header

        debug(2, "width = %d; height = %d\n", width, height);

        if (_hasPalette) {
                _picturePalette = new byte[_paletteColorCount * 3];
                sourceS->read(_picturePalette, _paletteColorCount * 3);
        }

        _picture = new Graphics::Surface();
        _picture->create(width, height, 1);

        decompressImage(source, *_picture, cmdOffs, pixelOffs, maskOffs, lineSize, cmdFlags, pixelFlags, maskFlags);

        delete sourceS;

}
```


From graphics.cpp:

```

        const int offsets[] = {
                0, 1, 2, 3,
                320, 321, 322, 323,
                640, 641, 642, 643,
                960, 961, 962, 963
        };

        uint16 width = surface.w;
        uint16 height = surface.h;

        byte *cmdBuffer = source + cmdOffs;
        ValueReader maskReader(source + maskOffs, (maskFlags & 2) != 0);
        ValueReader pixelReader(source + pixelOffs, (pixelFlags & 2) != 0);

        if ((maskFlags != 0) && (maskFlags != 2) && (pixelFlags != 0) && (pixelFlags != 2) && (cmdFlags != 0))
                error("decompressImage() Unsupported flags: cmdFlags = %02X; maskFlags = %02X, pixelFlags = %02X", cmdFlags, maskFlags, pixelFlags);

        byte *destPtr = (byte*)surface.getBasePtr(0, 0);

        byte lineBuf[640 * 4];
        byte bitBuf[40];

        int bitBufLastOfs = (((lineSize + 1) >> 1) << 1) - 2;
        int bitBufLastCount = ((width + 3) >> 2) & 7;
        if (bitBufLastCount == 0)
                bitBufLastCount = 8;

        while (height > 0) {

                int drawDestOfs = 0;

                memset(lineBuf, 0, sizeof(lineBuf));

                memcpy(bitBuf, cmdBuffer, lineSize);
                cmdBuffer += lineSize;

                for (uint16 bitBufOfs = 0; bitBufOfs < lineSize; bitBufOfs += 2) {

                        uint16 bits = READ_LE_UINT16(&bitBuf[bitBufOfs]);

                        int bitCount;
                        if (bitBufOfs == bitBufLastOfs)
                                bitCount = bitBufLastCount;
                        else
                                bitCount = 8;

                        for (int curCmd = 0; curCmd < bitCount; curCmd++) {
                                int cmd = bits & 3;
                                bits >>= 2;

                                byte pixels[4];
                                uint32 mask;

                                switch (cmd) {

                                case 0:
                                        pixels[0] = pixelReader.readPixel();
                                        for (int i = 0; i < 16; i++)
                                                lineBuf[drawDestOfs + offsets[i]] = pixels[0];
                                        break;

                                case 1:
                                        pixels[0] = pixelReader.readPixel();
                                        pixels[1] = pixelReader.readPixel();
                                        mask = maskReader.readUint16();
                                        for (int i = 0; i < 16; i++) {
                                                lineBuf[drawDestOfs + offsets[i]] = pixels[mask & 1];
                                                mask >>= 1;
                                        }
                                        break;

                                case 2:
                                        pixels[0] = pixelReader.readPixel();
                                        pixels[1] = pixelReader.readPixel();
                                        pixels[2] = pixelReader.readPixel();
                                        pixels[3] = pixelReader.readPixel();
                                        mask = maskReader.readUint32();
                                        for (int i = 0; i < 16; i++) {
                                                lineBuf[drawDestOfs + offsets[i]] = pixels[mask & 3];
                                                mask >>= 2;
                                        }
                                        break;

                                case 3:
                                        if (!deltaFrame) {
                                                // For EGA pictures: Pixels are read starting from a new byte
                                                maskReader.resetNibbleSwitch();
                                                // Yes, it reads from maskReader here
                                                for (int i = 0; i < 16; i++)
                                                        lineBuf[drawDestOfs + offsets[i]] = maskReader.readPixel();
                                        }
                                        break;

                                }

                                drawDestOfs += 4;

                        }

                }

                if (deltaFrame) {
                        for (int y = 0; y < 4 && height > 0; y++, height--) {
                                for (int x = 0; x < width; x++) {
                                        if (lineBuf[x + y * 320] != 0)
                                                *destPtr = lineBuf[x + y * 320];
                                        destPtr++;
                                }
                        }
                } else {
                        for (int y = 0; y < 4 && height > 0; y++, height--) {
                                memcpy(destPtr, &lineBuf[y * 320], width);
                                destPtr += width;
                        }
                }

        }

}
```


I've attached a tarball with the made source code. 
The format of FLE files can be learned from the loader in resource.cpp (PictureResource.LoadRaw function)
[made.tar.gz](https://xentaxbackup.github.io/file/2120_made.tar.gz)
## Post #5
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-12-05T15:50:15+00:00
- Post Title: Return to Zork FLE file

The contents of this post was deleted because of possible forum rules violation.
