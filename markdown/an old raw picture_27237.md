## Post #1
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2023-09-23T18:17:17+00:00
- Post Title: an old raw picture

Hi, attached is a raw picture of a red heart from an old amiga game but I haven't figured out how to properly display it.

Best I could do 



What's to figure out:
 - resolution
 - number of colors
 - palette 

The last 32bytes at the end of file could be palette, but 32 does not seem enough. 

Any help, tips?
[HEART.RAW1.zip](https://xentaxbackup.github.io/file/24375_HEART.RAW1.zip)
## Post #2
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-09-24T03:20:55+00:00
- Post Title: an old raw picture

Does this look right? Tis four bitplanes, each 320x192, with indeed the palette starting at 7800h with 16-bit palette entries (in bit increasing index order: r4,g4,b4,x4) The bitplanes are stored in big endian order (x coordinate 0 is bit 7, and x coordinate 7 is bit 0). Do you have an in-game reference image from anonymous game? Memory layout is (using a pseudo language):

```
uint1 bitplane0[320*192];
uint1 bitplane1[320*192];
uint1 bitplane2[320*192];
uint1 bitplane3[320*192];

struct r4x4b4g4 // little endian bit order here
{
    uint4 r; // byte 0, bits 0 through 3, red comes first
    uint4 x; // byte 0, bits 4 through 7, ignored bits (0's)
    uint4 b; // byte 1, bits 0 through 3
    uint4 g; // byte 1, bits 4 through 7
};
r4x4b4g4 palette[16]; // @7800h

```


See Amiga ACBM [https://codetapper.com/amiga/maptapper/ ... /gfx-mode/](https://codetapper.com/amiga/maptapper/documentation/gfx/gfx-mode/).
[Heart-4x320x192.jpg](https://xentaxbackup.github.io/file/24376_Heart-4x320x192.jpg)
## Post #3
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2023-09-25T09:27:04+00:00
- Post Title: an old raw picture

Than you so much for your help.   

Your picture looks very right. How did you do it?

Reference:


Based on the information you provided,

I split one palette entry (2bytes) into 4x4bit color components but then the highest resulting number is 15.

```
00 3B 07 C2-05 90 03 60-01 11 03 34-05 56 09 9A

```


r:0xF g:0xA b:0x5
r:0xD g:0xD b:0xD
r:0x2 g:0x2 b:0x5
r:0x0 g:0x4 b:0x9

Am I interpreting the values correctly?
How do I convert these into standard RBG values?
## Post #4
- Username: piken
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 25, 2021 9:55 pm
- Post datetime: 2023-09-26T10:18:37+00:00
- Post Title: an old raw picture

> Your picture looks very right. How did you do it?

I used a hacky little C++ utility I'm working on, but you can do the same with other (user friendly) tools like Maptapper (pictured below, albeit with wrong palette) and Binxelview. Expanding the palette is a tougher aspect, as I'm not seeing this option in Maptapper itself, but if you convert the palette to more typical RGB form, maybe the Palette options/menu hold promise.

> I split one palette entry (2bytes) into 4x4bit color components but then the highest resulting number is 15. Am I interpreting the values correctly?

Close, just reversed. The two pertinent palette indices are 6 for the heart and 12 for the background. So index 6 should have value red=0xA (or 170 of 255).

```
1: r:0xD g:0xD b:0xD
2: r:0x5 g:0x2 b:0x2
3: r:0x9 g:0x4 b:0x0
4: r:0xB g:0x7 b:0x0
5: r:0xD g:0xA b:0x3
6: r:0xA g:0x0 b:0x0
...

```


> How do I convert these into standard RGB values?

Just multiply by 255/15.
[Maptapper-Magicland-Dizzy.png](https://xentaxbackup.github.io/file/24385_Maptapper-Magicland-Dizzy.png)
