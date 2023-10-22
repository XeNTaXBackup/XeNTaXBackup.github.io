## Post #1
- Username: Nick W
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 25, 2009 10:04 pm
- Post datetime: 2009-05-30T02:38:19+00:00
- Post Title: PS2 texture unswizzling (4-bit textures)

To make a long story short, I'm working on the SVR image format and I'm having trouble unswizzling 4-bit textures. I've already got 8-bit texture unswizzling working fine.

The image on the left is what it should look like, the image on the right is how it currently works with my unswizzle code.

[http://img39.imageshack.us/img39/3479/accordcorrect.png](http://img39.imageshack.us/img39/3479/accordcorrect.png)
[http://img39.imageshack.us/img39/4348/a ... orrect.png](http://img39.imageshack.us/img39/4348/accordincorrect.png)

I'm currently using [Sparky's Swizzle Code](http://playstation2-linux.com/download/p2lsd/sparkys_swizzle_code.html) for this, obviously modified so it unswizzles rather than swizzles again.

Here is the code I'm currently using (C#):

```
        public static void UnSwizzle4(byte[] Buf, int Width, int Height, int Where)
        {
            // Don't swizzle if size if width or height is less than 128
            if (Width < 128 || Height < 128)
                return;

            // Make a copy of the swizzled input and clear buffer
            byte[] Swizzled = new byte[Buf.Length - Where];
            Array.Copy(Buf, Where, Swizzled, 0, Swizzled.Length);

            for (int y = 0; y < Height; y++)
            {
                for (int x = 0; x < Width; x++)
                {
                    // get the pen
                    int index = y * Width + x;
                    //byte uPen = (byte)(Swizzled[index >> 1] >> ((index & 1) * 4) & 0xF);

                    // swizzle
                    int pageX = x & (~0x7f);
                    int pageY = y & (~0x7f);

                    int pages_horz = (Width + 127) / 128;
                    int pages_vert = (Height + 127) / 128;

                    int page_number = (pageY / 128) * pages_horz + (pageX / 128);

                    int page32Y = (page_number / pages_vert) * 32;
                    int page32X = (page_number % pages_vert) * 64;

                    int page_location = page32Y * Height * 2 + page32X * 4;

                    int locX = x & 0x7f;
                    int locY = y & 0x7f;

                    int block_location = ((locX & (~0x1f)) >> 1) * Height + (locY & (~0xf)) * 2;
                    int swap_selector = (((y + 2) >> 2) & 0x1) * 4;
                    int posY = (((y & (~3)) >> 1) + (y & 1)) & 0x7;

                    int column_location = posY * Height * 2 + ((x + swap_selector) & 0x7) * 4;

                    int byte_num = (x >> 3) & 3;     // 0,1,2,3
                    int bits_set = (y >> 1) & 1;     // 0,1            (lower/upper 4 bits)

                    byte uPen = (byte)(Swizzled[page_location + block_location + column_location + byte_num] >> ((index & 1) * 4) & 0xF);
                    Buf[Where + (index >> 1)] = (byte)((Buf[Where + (index >> 1)] & -bits_set) | (uPen << (bits_set * 4)));
                }
            }
        }
```


Here's the SVR of that file, if it helps at all (CLUT starts at 0x20 and is ARGB8888, image data at 0x60):
[http://www.puyonexus.net/files/misc/accord_dress.svr](http://www.puyonexus.net/files/misc/accord_dress.svr)
## Post #2
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-21T03:36:09+00:00
- Post Title: PS2 texture unswizzling (4-bit textures)

I'm in the same exact boat, and every bit of source code I've found doesn't work, although the source code from Puyo Tools and Sparky's Swizzle Code (they are the same thing and not sure who is the original publisher of the code) has been the closest one so far.
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2013-11-11T05:05:08+00:00
- Post Title: PS2 texture unswizzling (4-bit textures)

Check this. It's sort of a mess but it for sure works. It's based on Puyo Tools. [https://github.com/neko68k/rtftool/blob ... p6t_v2.cpp](https://github.com/neko68k/rtftool/blob/master/RTFTool/rtfview/p6t_v2.cpp)
## Post #4
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2017-11-07T08:28:58+00:00
- Post Title: PS2 texture unswizzling (4-bit textures)

After 8 years of this originally being posted, I can finally provide a concrete answer to 4-bit PS2 texture unswizzling. I wrote it in C# and is based on Delphi code originally by Dageron. Full credit goes to him for being smart enough to know how this stuff works!

A permanent link to the code can be found [here](https://gist.github.com/Fireboyd78/1546f5c86ebce52ce05e7837c697dc72). If you use this in an open-source project, a link back to the gist would be appreciated. But do make sure you give full credit to Dageron, as he's the one who made this possible in the first place!

Happy unswizzling!
## Post #5
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2017-11-12T23:11:21+00:00
- Post Title: PS2 texture unswizzling (4-bit textures)

The

> //if ((mw % 32) > 0)
>
>     //    mw = ((mw / 32) * 32) + 32;
part is for alignment to multiples of 32.

Though the typical implementation would be:

```

```

instead of having the remainder check.
