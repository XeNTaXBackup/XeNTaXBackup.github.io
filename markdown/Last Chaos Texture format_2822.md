## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-10-17T09:10:54+00:00
- Post Title: Last Chaos Texture format??

Could anyone help me to figure out the texture format of "Last Chaos".
The data doesn't look like compressed but something more than standard RGBA!?

Thanks!
[LastChaosTexture.rar](https://xentaxbackup.github.io/file/1374_LastChaosTexture.rar)
## Post #2
- Username: db.
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 10, 2007 10:12 am
- Post datetime: 2007-10-17T13:33:59+00:00
- Post Title: Last Chaos Texture format??

[http://gustavobraga.com/english/?cat=9](http://gustavobraga.com/english/?cat=9)

i came across this. dunno if it will heplp.

im guessing a program called txmake was made to convert it from its original state.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-10-17T14:48:36+00:00
- Post Title: Last Chaos Texture format??

Thanks db., so Last Chaos use renderman own texture *.tx ??

I can't found the format of .tx neither, and I don't think txmake is free as well !?

Any more help?
## Post #4
- Username: db.
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 10, 2007 10:12 am
- Post datetime: 2007-10-17T15:01:56+00:00
- Post Title: Last Chaos Texture format??

ill look into a secondary program but they have a trials
[https://renderman.pixar.com/products/tools/index.htm](https://renderman.pixar.com/products/tools/index.htm)
## Post #5
- Username: db.
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 10, 2007 10:12 am
- Post datetime: 2007-10-17T15:58:26+00:00
- Post Title: Last Chaos Texture format??

hmm, looked into it and as far as i can tell so far its only done in rendermans .

[http://www.2shared.com/file/2392037/28b ... ntree.html](http://www.2shared.com/file/2392037/28b3303a/rmantree.html) hopefully that will help.
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-10-18T09:36:35+00:00
- Post Title: Last Chaos Texture format??

Hi db., none of your programs work, I can only get error message!

Anyway, here is what I know about this texture format: 

it is basically uncompressed RGB(A)?? full colored image with different mipmap together.

I use hw_bu_000.tex as example:

Header are 0x2C bytes then image size follow(yellow color in the image), so at 0x2C->00020000 = 128X128X8
Second image size at 0x20030->0x8000 = 64X64X8

Red color in the image are red(?) layer, and green color for green(?) layer. But blue and alpha didn't look correct?? (the texture with every 6th byte as blue color show in the image below)

Any help please!
[hex_tex.jpg](https://xentaxbackup.github.io/file/1375_hex_tex.jpg)
## Post #7
- Username: db.
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 10, 2007 10:12 am
- Post datetime: 2007-10-18T13:26:18+00:00
- Post Title: Last Chaos Texture format??

do you think they could of used renderman, then compressed it? so far this is the only lead i ended up with tracking down .tex formats.
## Post #8
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-18T19:21:02+00:00
- Post Title: Last Chaos Texture format??

> Reply from db.
>
> do you think they could of used renderman, then compressed it? so far this is the only lead i ended up with tracking down .tex formats.

With such obvious patterns, I'd doubt it's compressed to be honest...
## Post #9
- Username: db.
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 10, 2007 10:12 am
- Post datetime: 2007-10-19T06:10:10+00:00
- Post Title: Last Chaos Texture format??

> Reply from NKCSS
>
> db. wrote:do you think they could of used renderman, then compressed it? so far this is the only lead i ended up with tracking down .tex formats.

With such obvious patterns, I'd doubt it's compressed to be honest...

the exe in  command promt has compression available and a few other commands, but from what ive seen , it wants to use tiff files, dunno if it uses any others.[ just saying theres an option for it] 

im rather stummped :\
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-11-05T16:16:42+00:00
- Post Title: Last Chaos Texture format??

Could anyone expert take a look at these texture!?
I had decoded the 3D model files, but without texture, they are useless!
[healer.jpg](https://xentaxbackup.github.io/file/1387_healer.jpg)
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-11-19T00:19:05+00:00
- Post Title: Last Chaos Texture format??

This doesn't really look like uncompressed RGB(A). Maybe it's compressed or they use a palette.
EDIT: Though there wouldn't be such repetitions with compression.
Most likely it uses a palette.
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-11-21T09:48:35+00:00
- Post Title: Last Chaos Texture format??

One of my friend found out that the header is actually "Serious Sam" format. You can compare _TAG_ef.tex with any SS tex for sure!

Unfortunately most of these tex's header(Last Chaos) are encrypted! But they seem only headers are encrypted(same for the 3D models part).

If you take a closer look on those format. Sometimes they have mip-map. I guess the format should be something like these:

```
0x28-0x2B (dword)     size of whole image (all mip-map together)
..
{
 dword    mip-map size
 word     col Red
 word     col Green
 word     col blue
 word     col Alpha
}
..
```


for examples 

```
 
    00000000h: 54 56 45 52 04 00 00 00 54 44 41 54 0D 00 00 00 ; TVER....TDAT....
    00000010h: 00 04 00 00 00 04 00 00 07 00 00 00 04 00 00 00 ; ................
    00000020h: 01 00 00 00 46 52 4D 43 D4 0A 00 00 00 08 00 00 ; ....FRMC  ......

0x2C-0x2F -> 0x800 which is 16 * 16 * 8(8 bytes each color)
mip-map 1 @ 0x002C 16*16*8
mip-map 2 @ 0x0830 8*8*8
mip-map 3 @ 0x0A34 4*4*8
mip-map 4 @ 0x0AB8 2*2*8
mip-map 5 @ 0x0ADC 1*1*8
mip-map 6 @ 0x0AE8 1*1*8
mip-map 7 @ 0x0AF4 1*1*8 
0x28-0x2B (dword) ->0xAD4, after offset 0x2C + 0xAD4 = 0xB00
which is footer "ANIMADAT"

:hw_bu_000.tex
    00000000h: 54 56 45 52 04 00 01 00 54 44 41 54 3E 3f 14 12 ; TVER....TDAT>?..
    00000010h: 81 80 57 55 C4 C1 9A 98 0D 06 DD DB 4E 49 20 1E ; ?WU鐘?..椳NI .
    00000020h: 8C 8C 63 61 46 52 4D 53 E0 AA 02 00 00 00 02 00 ; ?caFRMC鄋......
 
0x2C-0x2F -> 0x20000 which is 128 * 128 * 8 !!!
mip-map 1 @ 0x0000002C 128*128*8
mip-map 2 @ 0x00020030 64*64*8
mip-map 3 @ 0x00028034 32*32*8
mip-map 4 @ 0x0002A038 16*16*8
mip-map 5 @ 0x0002A83C 8*8*8
mip-map 6 @ 0x0002AA40 4*4*8
mip-map 7 @ 0x0002AAC4 2*2*8
mip-map 8 @ 0x0002AAE8 1*1*8
mip-map 9 @ 0x0002AAF4 1*1*8
mip-map 10 @ 0x0002AB00 1*1*8
0x28-0x2B -> 0x2AAE0, after offset 0x2C + 0x2AAE0 = 0x2AB0C
again which is footer "ANIMADAT"

```


Each color pixel is 8 bytes(sometimes 16 bytes eg: hw_face_000.tex). for the format I am guessing, I have R and G correct. So I am really confused if they use palette!

Any help is appreciated!
## Post #13
- Username: spintz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 19, 2008 11:02 am
- Post datetime: 2008-08-30T00:45:31+00:00
- Post Title: Last Chaos Texture format??

The texture data looks like DDS Compressed texture data, like DXT1, DXT3 or DXT5
## Post #14
- Username: TinyGuy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 24, 2009 6:43 pm
- Post datetime: 2009-03-25T10:31:02+00:00
- Post Title: Last Chaos Texture format??

Hello.
I know this thread is very old, but I've done some research about Last Chaos file formats recently.

Here's my notes about Last Chaos *.TEX file format:

> char version_chunk[4]	: "TVER"
>
> int version		: 0x00010004 (this version has encoded header data)
>
> char data_chunk[4]	: "TDAT"
>
> unsigned int enc_width	: texture width; decode with XOR 0x12143D3E
>
> unsigned int enc_shift  : Value for Bitwise Right-Shift; decode with XOR 0x55578081
>
> unsigned int enc_height	: texture height; decode with XOR 0x989AC3C4
>
> unsigned int enc_mipmap : mipmaps count; decode with XOR 0xDBDD0607
>
> unsigned int enc_bits	: texture bits; decode with XOR 0x1E20494A
>
> unsigned int enc_uknown	: seems to be always 1; decode with XOR 0x61638C8D
>
> char format_chunk[4]	: "FRMC" for compressed texture; "FRMS" for uncompressed
>
> int anim_offset		: offset to ANIMADAT header
>
> 
>
> If format_chunk is "FRMC" then we have:
>
> 
>
> repeat "enc_mipmap" times
>
> {
>
> int size		: texture data size in bytes 
>
> unsigned char data[size]: texture data (it's DTX1 or DTX3 data)
>
> }
>
> 
>
> For "FRMS" format we just got data (RGB or RGBA) without size; we need to compute it manualy
>
> or use anim_offset.
>
> 
>
> -------------------------------------------------------------------------------------
>
> NOTE: After decoding Width and Height you need to do bitwise operation:
>
> 
>
>  enc_width >>= enc_shift
>
>  enc_height >>= enc_shift
>
> 
>
> Texture bits values are not casual. 
>
> 
>
> For "FRMC" format it's:
>
> 
>
> if enc_bits is 4 or 13 then texture data is compressed with DTX1 (24 bits/ no alpha)
>
> for another values its compressed with DTX3 (32 bits/ with alpha) 
>
> 
>
> For "FRMS":
>
> 
>
> if enc_bits is 0 or 2 then texture data is RGB otherwise its RGBA.
>
> -------------------------------------------------------------------------------------
>
> -------------------------------------------------------------------------------------
>
> What if version is 0x00000004? 
>
> 
>
> It's not encoded. Only the data sequence is a bit different.

And [here](http://www.filefactory.com/file/af7ge11/n/textoolv07_zip) you can download my TEXTool which can export last chaos textures to tga and vice versa.

Im working on model viewer and exporter. If someone is interested about it please pm me.
Here's my progress:
[](http://img90.imageshack.us/my.php?image=modelviewer1.jpg) [](http://img50.imageshack.us/my.php?image=healerskeleton.jpg)
## Post #15
- Username: Ghostt
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 19, 2009 11:19 pm
- Post datetime: 2009-04-19T18:21:32+00:00
- Post Title: Last Chaos Texture format??

Sended you a pm 

Very interested to do some reskins
## Post #16
- Username: TinyGuy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 24, 2009 6:43 pm
- Post datetime: 2009-06-04T08:09:42+00:00
- Post Title: Re: Last Chaos Texture format??

Latest build of my Last Chaos Model Viewer can be found here: [http://chaosviewer.gofreeserve.com/](http://chaosviewer.gofreeserve.com/)
Thanks Ghostt for support   

Enjoy
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T21:21:15+00:00
- Post Title: Re: Last Chaos Texture format??

Nice going people!
## Post #18
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-09-10T22:32:52+00:00
- Post Title: Re: Last Chaos Texture format??

Just saw that this project is abandoned. That is a shame. Hope you are doing some other viewers
