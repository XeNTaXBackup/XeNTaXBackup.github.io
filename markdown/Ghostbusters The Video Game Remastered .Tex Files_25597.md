## Post #1
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-07-07T19:28:44+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

Hi i want to ask how to edit a .tex file or remake a .tex file , i have found and program that makes .tex files into .dds but i haven't found a program that turns the .dds file into .tex file
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-09T11:27:35+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

Please upload a few sample TEX files.

And tell us which program did you use to convert TEX to DDS.
## Post #3
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-07-09T12:47:03+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

the program i used is found in this topic

[viewtopic.php?t=4392](https://forum.xentax.com/viewtopic.php?t=4392)

and here are some .tex files from Ghostbusters The Video Game Remastered

[https://www.mediafire.com/file/58dyijon ... s.rar/file](https://www.mediafire.com/file/58dyijonvho4x09/.tex_files.rar/file)

and also in the game W64ART02.POD File if you open the materials file and open a random .mtb file is going to referring .tga files

janine_outfit02.mtb

  ±`»@²?u ΪΊΑσart\char\npc\janine\sweater\body_bump.tga )Ϋ§ΒT2ΐcΏβξ‹yart\char\npc\janine\sweater\body_diff.tga γoΜpγWέ[qσϊ•6art\char\npc\janine\sweater\body_spec.tga ΒϊWdAyφ?AΫ~a  /SL    
            normal          char\npc\janine\sweater\body_bump.tga                                              diffuse         char\npc\janine\sweater\body_diff.tga
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T10:02:50+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

It appears the format is partially known [http://wiki.xentax.com/index.php/Ghostb ... stered_TEX](http://wiki.xentax.com/index.php/Ghostbusters:_The_Video_Game_Remastered_TEX)
But there are some unknown fields there (e.g. hash and CRC)
Until someone will fully reverse engineer this, new TEX files may not work in game after replacing original ones.
## Post #5
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-07-26T20:32:49+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

Unfortunately that tex to dds converter doesn't seem to work for the remastered version, only the diffuse texture converts fine but other ones like the normal, AO and specular are all corrupted and cannot be opened. Any help?
## Post #6
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-08-05T18:58:56+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

> Reply from AxelNoir ↑Wed Jul 27, 2022 4:32 am at Wed Jul 27, 2022 4:32 am
>
> 
Unfortunately that tex to dds converter doesn't seem to work for the remastered version, only the diffuse texture converts fine but other ones like the normal, AO and specular are all corrupted and cannot be opened. Any help?

The tool itself is broken and produces corrupt DDS files for both versions of the game due to not initialising fields correctly. [Here](https://gist.github.com/barncastle/8429b6d3130fca582d1564cdbe47fb8e) is a fixed version + source - the exe is at the end of the page. I've tested it against the sample files and a few files from the original 2009 version of the game and the original logic is working correctly.

FWIW, the original game doesn't use the "CRC" field, it is reserved, and skips the "hash" value so you might get away with not setting those when replacing files in the remastered version since it's almost an identical format (excluding the "CRC" field).

Also the "nulls" after the hash are actually a byte + padding. Each hash is followed by a boolean which, if is true, indicates that there is another hash to be read. This repeats until a 0 byte after a hash, then the game 4-byte aligns the pointer. This is based on the original game but is probably valid here too.

```
    
    if ( file->ReadByte() != 0 ) // read boolean, if true another hash is present
    {
        while ( true ) // repeat until a terminating "false" value occurs
        {
            if ( file->ReadByte() == 0 ) // read bytes until a 0
            {
                file->ReadData(&buffer, 16); // read another hash
		
                if ( file->ReadByte() == 0 ) // read another boolean and repeat
                    break;
            }
        }
    }
    
    // read until 4-byte aligned
    for ( long pos = file->GetPosition(); (pos & 3) != 0; pos = file->GetPosition() )
        file->ReadByte();

```
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2022-08-07T11:41:55+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

This is great, thank you! I'll try it when I get a chance
## Post #8
- Username: sakis720
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jul 05, 2022 6:51 pm
- Post datetime: 2022-09-24T08:36:11+00:00
- Post Title: Ghostbusters The Video Game Remastered .Tex Files

I don't know if this is useful 

ghost.exe:

texture on the video card.  Please lower your graphics settings.       tried to select streaming texture '%s' but data wasn't loaded
  paletted (24)   paletted (32)   8-bit w/ opac map   32-bit      16-bit (565)    16-bit (4444)   PS2 paletted (24)       PS2 paletted (4)        PS2 paletted (32)       PS2 32-bit      PSP 32-bit      PSP 16-bit+alpha        PSP 16-bit      PSP DXT3        PSP Paletted (24)       PSP Paletted (32)       PSP paletted (4)        GC compressed   GC 32-bit       GC paletted (4) GC paletted (24)        GC paletted (32)        XBOX DXT3       XBOX paletted (24)      XBOX paletted (32)      XBOX 32-bit     Win32 DXT1      Win32 DXT3      Win32 DXT5      Win32 XY Normal Map     Render texture  Render cube map Cube map 32-bit XBOX cube map paletted (24)     XBOX2 32-bit    XBOX2 DXT1      XBOX2 DXT3      XBOX2 DXT5      XBOX2 cube map 8888     XBOX2 cube map 8888 lin XBOX2 cube map DXT1     XBOX2 DXN       XBOX2 XY Normal Map     XBOX2 YUY2 Little Endian Linear PS3 32-bit      PS3 DXT1        PS3 DXT3        PS3 DXT5        PS3 cube map 8888       PS3 XY Normal Map       Wii cube map 8888       NX XY Normal Map        NX ASTC RGBA 4x4        NX ASTC RGBA 8x8        NX ASTC RGBA 4x4 Cubemap        NX RGBA Cubemap NX RGBA 8-bit Grayscale GC 8-bit Grayscale      GC 8-bit Grayscale+Alpha        XboxOne 32-bit  XboxOne DXT1    XboxOne DXT3    XboxOne DXT5    XboxOne 32-bit Cubemap  XboxOne DXT1 Cubemap    XboxOne XY Normalmap    PS4 32-bit      PS4 BC1 PS4 BC2 PS4 BC3 PS4 32-bit Cubemap      PS4 BC1 Cubemap PS4 XY Normalmap        (unknown format)
