## Post #1
- Username: Stickman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 17, 2013 6:23 am
- Post datetime: 2013-04-09T21:23:12+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

Hello,
I am currently trying to rip the graphics from Atlus' wonderful game "Trauma Center: Second Opinion".
The graphic files have the extension *.tpx, which i personally never heard of, and I couldn't find anything useful on Google.

Please note that I have no experience in game file researching, so all the assumptions I'm going to make are mere guesses.

After looking at some of the files in a hex editor, I noticed that a lot of these files have values like 256 or 512 (unsigned 16-bit) at offsets 0x06 and 0x0E, so I think that these are width and height. (however, I am not sure...) I also noticed that these files contain a null-terminated string at offset 0x2C that looks very similar or is equal to the filename.

I did some experiments on the file "sprite\bustup\chr01_02.tpx" and attempted reading the image-file using the following piece of C# code:

```
        {
            FileStream str = File.OpenRead(args[0]);
            BitStream bs = new BitStream(str);
            bs.BaseStream.Position = 6;                 //this is just a guess for the width offset
            ushort width = bs.ReadUInt16();
            bs.BaseStream.Position = 14;                //this is just a guess for the height offset
            ushort height = bs.ReadUInt16();

            int bitGuess = width * height * 2;          //I'm assuming 16bit coloring, so the size of a pixel should be 2 bytes
            int offGuess = (int)(str.Length - bitGuess);      //(Length Of File - Assumed size of the picture)

            //width *= 2;
            Bitmap bmp = new Bitmap(width, height);

            bs.Seek((uint)offGuess);

            uint r, g, b, a;
            for (int y = 0; y < height; y++)
            {
                for (int x = 0; x < width; x++)
                {
                    r = bs.bitstream_read(5) * 8;      //This should convert RGBA5551 to 32-bit
                    g = bs.bitstream_read(5) * 8;      //bitstream_read(x) reads x bits
                    b = bs.bitstream_read(5) * 8;
                    a = bs.bitstream_read(1);
                    bmp.SetPixel(x, y, Color.FromArgb((byte)r, (byte)g, (byte)b));
                    if (bs.BaseStream.Position == bs.BaseStream.Length) break;
                }
                if (bs.BaseStream.Position == bs.BaseStream.Length) break;
            }
            bmp.Save("test.png");
        }

```


However, this code obviously can't be correct with the little information I have.
The following image is output:



One of the game characters is clearly recognizable, but the colors are definetly wrong, and the image has a weird scanline effect.

I got rid of the scanlines by multiplying the image witdh with 2 (That line is commented in the code), but then he looks kind of squeezed:



The colors, i couldn't figure out. I tried ARGB4444, RGBA5551, ARGB1555 and RGB565, but none of them led to a good result.

I think I can't provide sample files, because I don't want to violate the rules.

I would be happy if someone could help me, a newbie with this.

TL;DR: I need help with the *.tpx files of Trauma Center: Second Opinion.
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-04-12T14:45:03+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

Most Wii games have TPL files for their images. It's possible that your images are only slightly altered tpl files. So you should have a look at this: [http://hitmen.c02.at/files/yagcd/yagcd/ ... l#sec15.35](http://hitmen.c02.at/files/yagcd/yagcd/chap15.html#sec15.35) Dumping some textures with an emulator (dolphin) could be helpful too. This way you can compare your rips with the real image.
I guess posting a screenshot of just the header (in hexeditor) would be ok.

EDIT: And dont forget tools like tileggd for testing.
## Post #3
- Username: Stickman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 17, 2013 6:23 am
- Post datetime: 2013-04-14T17:21:51+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

Thanks for you response, TPL was a good approach.   
The files in question seem to be some kind of container for TPL files.
I've seen the magic number and the header size inside the files (I've marked that in the attached screenshot), so I went ahead and wrote a tool which looks for the magic number and cuts off everything before it.

I tried converting the resulting file using TplMii and it basically worked, however the colors were all wrong. I tried using TiledGGD and was able to reproduce the exact image TplMii outputted, however I tried various combinations of options in TiledGGD, and none of them worked. I think the palette is tiled as well in some evil way.

Using the tool I wrote, I was able to figure out what the height,width and format of the TPL are. The values I got were 512 x 512 with an 8 bit color index, 8x4 tiles (format 9). I encountered a problem when I tried to read the Palette Header format. The document you posted lists 0, 1 and 2 as possible values for the format, however all these files seem to have 255 as a Palette Header format value.

Screenshot of the file in a hex editor:
[](http://image-upload.de/file/eJNSXY/e4324bd4d2.jpg)
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-04-16T18:27:26+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

So it seems to be a new palette format. That's bad because I have no idea about how to interpret it:)
From the screenshot I can see that the palette has 256 entries. You could have a look at the size of the palette to see how many bytes represent one pixel (I would do it myself but its a bit tedious with just the screenshot).
And maybe dumping the same image you converted with dolphin (somewhere in the options is a dump textures entry) to compare them would give some hints.
Just out of curiosity I would like to see one of your converted images. Could you post one?
## Post #5
- Username: Stickman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 17, 2013 6:23 am
- Post datetime: 2013-04-17T00:24:42+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

I assume one color uses 4 bytes in the palette.
Inside the TPL file I'm doing experiments on, the palette starts at offset 288 and the image data starts at 1376, so there are 1088 bytes space for the palette. 255x4=1020, so that seems to be the most logical assumption for me.

I tried dumping the textures using Dolphin 3.5 and got something I didn't expect. All the textures which came from TPX files ended up in greyscale. (Of course they're not like that in-game  )

Here is how my conversion attempts look like: (left is 3-byte-color palette, right is 4-byte)

[](http://image-upload.de/file/OBkeak/3ddf323871.png)
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-04-17T07:05:56+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

Ok, I would guess, since the palette header says 256 entries and there is enough space, the palette is 4 byte per pixel, 32bit or RGBA32 (called RGBA8 in the sourcefiles of libwiisharp). But somehow I think that's wrong. The image seems to be a grayscale image judging from your results. Since you said the ingame images aren't grey the image could be blended over another image to archive this effect. It would be a transparent image with different intensity.
TPLMii is using libwiisharp ([https://code.google.com/p/libwiisharp/s ... TPL.cs?r=3](https://code.google.com/p/libwiisharp/source/browse/trunk/libWiiSharp/TPL.cs?r=3)). When I read this right TPLmii will revert to RGB5A3 or RGB5A4 since the paletteformat is 0xff or "none". So that's definitely wrong. You could try to change the paletteformat to IA8 (format 0) inside a cutted out tpl and see what tplmii will make out of it.

PS. Quite helpful to understand the image formats [http://wiki.tockdom.com/wiki/Image_Formats](http://wiki.tockdom.com/wiki/Image_Formats)
## Post #7
- Username: howardlau
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 06, 2018 11:02 pm
- Post datetime: 2018-10-06T15:09:33+00:00
- Post Title: [Wii] Trauma Center: Second Opinion - *.tpx files

I spent some time studying this weird format and I figured out that this is a container for tpl files. You can easily determine how to extract tpls from tpx files. The palette is processed in the following manner: the first two bytes are the g and r of the first palette entry, the following two bytes are the g and r of the second entry and so on... When you finish reading all g and r of the entries, the a and b bytes follow. In other words, the rgba of a color are split into two parts and stored separately. Hopefully you can understand!
