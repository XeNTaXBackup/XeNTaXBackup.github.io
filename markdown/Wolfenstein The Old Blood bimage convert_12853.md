## Post #1
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2015-05-17T01:54:41+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

Wolfenstein The Old Blood file to convert fonts  ( bimage to dds )..

[http://www.mediafire.com/download/wl2tg ... _fonts.rar](http://www.mediafire.com/download/wl2tgj53kh47jlb/borderclamp_alpha_fonts.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-17T16:07:22+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

Arial_black_64df-bimage.JPG (76.26 KiB) Viewed 427 times
## Post #3
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2015-05-17T18:53:14+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

> Reply from shakotay2
>
> Arial_black_64df-bimage.JPG

How to
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-18T09:58:02+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

give it a header such like this:



X8B8G8R8.JPG (70.59 KiB) Viewed 416 times



Something is wrong, so it won't load normally. You'll have to use a tool like DXTBmp for example.
Or correct the header.
## Post #5
- Username: MuratG
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Oct 28, 2014 7:56 am
- Post datetime: 2015-05-18T21:23:57+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

bimage to dds convert damaged
## Post #6
- Username: avicii
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Aug 28, 2014 3:42 am
- Post datetime: 2015-05-25T19:26:22+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

hi dude can I ask you question ? Yeah sure =) , 

Real problem: I did edit to dds but not it didn't work. after doing like image. You should look at the image.

[http://i.hizliresim.com/ogjEGX.jpg](http://i.hizliresim.com/ogjEGX.jpg)

is there a different tool for this game ? 

and 

How ? - How do I fix it
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-25T19:56:30+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

> Reply from avicii
>
> Real problem: I did edit to dds but not it didn't work. after doing like image.same edits as I did?
You'll have to use DXTbmp to load the dds then since the header is not correct, as I wrote.

It's just a quickhack don't have the time for a full analysis, sry.

(I've pmed you my result.)
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-22T20:02:49+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

here is a Noesis script to open these *.bimage textures properly    
*updated Nov 16, 2016*


 tex_WolfensteinTheOldBlood_bimage.zip
(701 Bytes) Downloaded 98 times
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-23T06:29:50+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

if you claim the data to be RGBA32 then it's 4 bytes per pixel.
If you divide width and height by 2 (>> 1) everything looks fine.

(512*576*4= datasize)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-23T09:44:19+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

arggg! as far as i got was dividing by 2 and i had to convert the float to int for that to work  
i give up on this one, i'm not a programmer and i just don't understand how to properly use these >> 
the result i got is an image 512x576 and the canvas size looks good but the image data is still doubled  

i updated the previous attachment with the current updates
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-23T13:56:19+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

well, you shouldn't give up to soon  
You're on a very good way - but seems you didn't get my hint, obviously: >> 1
means shift right one bit, so the lines would be
imgWidth = bs.readInt() >> 1
imgHeight = bs.readInt() >> 1

Think of a binary value that is shifted right by one bit:
0b1110 >> 1: 0b0111

14 /2 = 7

(0b should be the binary prefix (as is 0x for hex) but I didn't check this with Noesis.)

Why should the image data be doubled? (size= 1179648 bytes)
Do you have two pics instead of one?
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-23T14:31:26+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

> Reply from shakotay2
>
> Why should the image data be doubled? (size= 1179648 bytes)
Do you have two pics instead of one?
this is the best result i can get whether using these >> or just dividing by 2

the image is doubled side by side, or is that how its supposed to look
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-23T18:30:55+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

well, what I could think of is that it is a 16 bit format here
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-23T20:36:18+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

this is what i was expecting these images to look like   


as you can see, if you stretch the width by 200 percent and center one side, the image looks correct.
the copyright and registered symbols have a perfect circle around them
## Post #15
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2016-07-23T20:43:32+00:00
- Post Title: Wolfenstein The Old Blood bimage convert

here are the fonts converted to dds 

(bimage header = 48 bytes)

I used texturefinder. First I set the correct resolution, then I take the number, for example, in futura_com_medium_jpn90 the resolution is 896 x 3583, I took the decimal numbers of resolution and I converted it to Hexadecimal 0x380 x 0xDFF, so the numbers that we need to put in the dds header is FFD0 and 8003 ( maybe this can help something hahaha)



64_df.bimage.jpg (75.19 KiB) Viewed 289 times


[http://www.mediafire.com/download/k2drc ... _fonts.rar](http://www.mediafire.com/download/k2drcjwb7zij5g6/borderclamp_alpha_fonts.rar)
## Post #16
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2016-11-14T16:41:56+00:00
- Post Title: Re: Wolfenstein The Old Blood bimage convert

[quote="AceWell"]this is my attempt at a Noesis script for these *.bimage textures    
*updated July 23, 2016*
Help me edit font ... How to convert your script font ???
## Post #17
- Username: InKviZ
- Rank: advanced
- Number of posts: 51
- Joined date: Mon Sep 29, 2014 12:57 am
- Post datetime: 2016-11-14T16:42:57+00:00
- Post Title: Re: Wolfenstein The Old Blood bimage convert

> Reply from AceWell
>
> this is my attempt at a Noesis script for these *.bimage textures    
*updated July 23, 2016*
tex_WolfensteinTheOldBlood_bimage.zip
i am reading the width and height from the original header and the canvas looks really large
while the image is smaller and duplicated 4 times across the top.   
i don't know if this is what the developers intended or if i just goofed

Help me edit font ... How to convert your script font ???
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-15T02:30:49+00:00
- Post Title: Re: Wolfenstein The Old Blood bimage convert

why post twice?   
the script is incomplete and i don't have a solution, you will have to find another way
## Post #19
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-11-16T17:20:26+00:00
- Post Title: Re: Wolfenstein The Old Blood bimage convert

Here is template for 010.

```
//--- 010 Editor v6.0.3 Binary Template
//
// File:
// Author:
// Revision:
// Purpose:
//--------------------------------------

BigEndian();

local int i;
local string s1;
local string s2;
local string s3;

struct BIMAGE {
        uint ID;
        uint Magic;
        uint Null;
        uint MainWidth;
        uint MainHeigth;
        uint Null1;
        uint Mipmaps;
        uint Null2;
        uint Par1;
        uint Par2;
        uint Par3;
        uint Par4;
        uint Null3;

for(i=0;i<Mipmaps;i++) {

struct Mipmap {
        uint MipmapNum;
        uint Null4;
        uint Width;
        uint Heigth;
        uint Mipmapsize;
        ubyte data[Mipmapsize];

        s1="Width =";
        s2="    Heigth =";
        s3="    Mipmap =";

Printf( "%s %u %s %u %s %u\n", s1, Width, s2, Heigth, s3, MipmapNum );
        } record;
    }
} record;
```

I will upload converted fonts later...

EDiT: Done + I update a template. You can edit them in GIMP and save as 8-bit Alpha.

```
http://www25.zippyshare.com/v/lrfvaCCT/file.html
```
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-17T02:45:51+00:00
- Post Title: Re: Wolfenstein The Old Blood bimage convert

Nice work, so the secret is they are 8-bit Alpha?   
Photoshop opens your dds file as "Alpha 1/8" and i see where the alpha channel is the
only one with anything in it, the RGB channels are all black. 

ok i fixed my Noesis python script to open "Alpha 1/8" or "8-bit alpha" image data  

```
    texFmt = noesis.NOESISTEX_RGBA32
```

[viewtopic.php?p=120610#p120610](http://forum.xentax.com/viewtopic.php?p=120610#p120610)
