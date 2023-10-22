## Post #1
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-05-26T21:46:07+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-26T22:04:22+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

I'd like to see those tga's but can't download from rapidshare/megaupload as it's blacklisted here.

If you could mirror or just attach I'll take a look.

Good night.
## Post #3
- Username: Balder
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-27T00:22:44+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T03:11:36+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Thanks for the mirror, chrrox. I also think that this is some kind of compression I'm sure that's not a tga header and some experiments I did interpreting bytes like colours lead to random figures.

The signature "TGZ" at the beggining could induce to think that this is tar compression but it's structure doesn't match at all. (Nor gzip or similar ones)

If you could provide the equivalent of some of the images (TEN40S21C,... or any other) as a screenshot taken from the game in a format like png or bmp I can try to find out something. But I'm not sure I'll manage to do that. In fact, it would be enough if you know what one of those tgas represents in the game. I can take the screenshot for you (if you don't know how to do this).

For example, if we know the height and width of the image we can maybe find those value as a header in the compressed one, and width*height will give us an idea of the compression rate.

Again, I have only experience with decoding images with palette codes and don't expect a miracle.

see you guys!
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-27T03:35:46+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

If you upload the main game exe i can try to figure out what the compression used is.
## Post #6
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-05-27T10:33:23+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

I will be uploading the exe then here.

I think the largest images are extremely wide 360 panorama images. It would be hard to figure out which one goes to which scene. They would be very wide so that you can spin around in a complete 360 picture.
## Post #7
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-05-27T10:41:42+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-05-27T17:07:14+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Great, so let's see if chrrox can reverse engineer that .exe to tell us what compression it's used
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-05T00:03:35+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

There is a compressed and uncompressed ico file in the games install directory.
I am not sure of the compression used.
here are the files attached.
[rtz.ico.rar](https://xentaxbackup.github.io/file/2075_rtz.ico.rar)
## Post #10
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-05T02:45:37+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-07T19:01:15+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: lordskylark
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-07T23:37:34+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

I had to get some time, but here's the low down. 

I took a look at the assembly code and found the decompress routine. I then realized that it was standard LZSS compression. 

The executable uncompresses the bitmap data and fills in a BITMAPHEADER to show the actual .BMP file (not TGA). So basically, the .TGA files are Art files, with the magic word TGZ (Texture Graphics Zipped or something). 

```
uint32 Original size of bitmap data
uint32 Width of image
uint32 Heigth of image
Byte[n] Bitmap data (LZSS compressed)

```


If I take the bitmap data and show it this is what you get for the first screen of the game (near the Temple):



3.tga.jpg (464.92 KiB) Viewed 635 times



Missing colours, but it show how the executable rotates the image when needed to give the 360 degrees impression in the game. Okay, so I took another look at the executable and noticed that it filled in a .BMP header with standard values for each image, and filling up the colour table in the .BMP with 0 (the bitmap values are also the RGB values! 16 bitcounts!)

So, I recreated the header and inserted that before my uncompressed bitmap data:



3.tga_final.jpg (604.76 KiB) Viewed 633 times



BINGO! 

Now for coolness, let's rotate it and make it smaller to fit here:



3.tga_final_rotated.jpg (293.39 KiB) Viewed 620 times




Thus, I decided to make a quick and dirty tool, and wrote a quickbms script to do the uncompression, wrapping it in a small GUI: unTGZ



untgz.jpg (372.02 KiB) Viewed 616 times



(oh here's the bms script : )

```
comtype lzss
get SIZE asize
math SIZE -= 16
get UNC_SIZE long
get WIDTH long
get HEIGHT long
savepos OFFSET
get NAME filename
string NAME += ".dec"
clog NAME OFFSET SIZE UNC_SIZE

```


And here's unTGZ:


 untgz.zip
(83.86 KiB) Downloaded 82 times



It's usage it simple. Point to a .TGA file, click Uncompress and quickbms will bother you will questions. it will uncompress the data for you and you'll see a preview. That means you will now find a .BMP file also in that folder with the unpacked image data! 

Have fun! 



EA20S11C.JPG (196.53 KiB) Viewed 609 times
## Post #13
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-08T00:12:23+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Amazing! I can't wait to put it to use.
## Post #14
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-08T05:25:38+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

There is a problem, and I'm not sure if it's the viewer or how the images are stored, but...

All the photos need to be rotated 180 degrees, and flipped horizontally...

This is how they all come out
[AB2EB21C.TGA.jpg](https://xentaxbackup.github.io/file/2084_AB2EB21C.TGA.jpg)
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-08T06:37:47+00:00
- Post Title: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Well, thats just a minor problem, considering the effort that was put in the work. 

I think the executable rotates the imagedata. In BMP files image data is stored "upside down". I don't rotate the data, but just put it in the .BMP files. I'll see if I can change that in unTGZ when I get the time. 

By the way, I'm 99% sure the programmers of Zork have used this code to achieve the decompression: 

```
 * Copyright (c) 2000 Apple Computer, Inc. All rights reserved.
 *
 * @APPLE_LICENSE_HEADER_START@
 * 
 * Copyright (c) 1999-2003 Apple Computer, Inc.  All Rights Reserved.
 * 
 * This file contains Original Code and/or Modifications of Original Code
 * as defined in and that are subject to the Apple Public Source License
 * Version 2.0 (the 'License'). You may not use this file except in
 * compliance with the License. Please obtain a copy of the License at
 * http://www.opensource.apple.com/apsl/ and read it before using this
 * file.
 * 
 * The Original Code and all software distributed under the License are
 * distributed on an 'AS IS' basis, WITHOUT WARRANTY OF ANY KIND, EITHER
 * EXPRESS OR IMPLIED, AND APPLE HEREBY DISCLAIMS ALL SUCH WARRANTIES,
 * INCLUDING WITHOUT LIMITATION, ANY WARRANTIES OF MERCHANTABILITY,
 * FITNESS FOR A PARTICULAR PURPOSE, QUIET ENJOYMENT OR NON-INFRINGEMENT.
 * Please see the License for the specific language governing rights and
 * limitations under the License.
 * 
 * @APPLE_LICENSE_HEADER_END@
 */
/**************************************************************
 LZSS.C -- A Data Compression Program
***************************************************************
    4/6/1989 Haruhiko Okumura
    Use, distribute, and modify this program freely.
    Please send me your improved versions.
        PC-VAN      SCIENCE
        NIFTY-Serve PAF01022
        CompuServe  74050,1022

**************************************************************/
/*
 *  lzss.c - Package for decompressing lzss compressed objects
 *
 *  Copyright (c) 2003 Apple Computer, Inc.
 *
 *  DRI: Josh de Cesare
 */

#include <sl.h>

#define N         4096  /* size of ring buffer - must be power of 2 */
#define F         18    /* upper limit for match_length */
#define THRESHOLD 2     /* encode string into position and length
                           if match_length is greater than this */
#define NIL       N     /* index for root of binary search trees */

int
decompress_lzss(u_int8_t *dst, u_int8_t *src, u_int32_t srclen)
{
    /* ring buffer of size N, with extra F-1 bytes to aid string comparison */
    u_int8_t text_buf[N + F - 1];
    u_int8_t *dststart = dst;
    u_int8_t *srcend = src + srclen;
    int  i, j, k, r, c;
    unsigned int flags;
    
    dst = dststart;
    srcend = src + srclen;
    for (i = 0; i < N - F; i++)
        text_buf[i] = ' ';
    r = N - F;
    flags = 0;
    for ( ; ; ) {
        if (((flags >>= 1) & 0x100) == 0) {
            if (src < srcend) c = *src++; else break;
            flags = c | 0xFF00;  /* uses higher byte cleverly */
        }   /* to count eight */
        if (flags & 1) {
            if (src < srcend) c = *src++; else break;
            *dst++ = c;
            text_buf[r++] = c;
            r &= (N - 1);
        } else {
            if (src < srcend) i = *src++; else break;
            if (src < srcend) j = *src++; else break;
            i |= ((j & 0xF0) << 4);
            j  =  (j & 0x0F) + THRESHOLD;
            for (k = 0; k <= j; k++) {
                c = text_buf[(i + k) & (N - 1)];
                *dst++ = c;
                text_buf[r++] = c;
                r &= (N - 1);
            }
        }
    }
    
    return dst - dststart;
}

```
## Post #16
- Username: lordskylark
- Rank: advanced
- Number of posts: 40
- Joined date: Tue May 26, 2009 8:27 pm
- Post datetime: 2009-06-08T07:32:34+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

I did want to mention before you changed anything with the program...

The long 360 degree images ... those all come out the correct way.

Just the none 360 degree images are flipped/mirrored and upside down.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-08T11:32:07+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

No, I believe those are also not right. I will check tonight.
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-08T21:29:53+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Okay, try this version. I was right, and I should have rotated the bitmap data before creating the bmp file. Now all pictures come out right. Please show the outcome of the previous example you used to point out the misalignment!

SCROLL BELOW FOR THE RIGHT VERSION!
## Post #19
- Username: Balder
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Jul 15, 2007 1:17 am
- Post datetime: 2009-06-08T22:00:38+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Great work (both disassembling and coding the tool). I thank the post cause of being interesting and helpful to lordskylark. Specially now with so many exams upon many of us!

Glad to see that there are no unsolved problems in XeNTaX
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-09T04:35:10+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Oops, there was an error in v0.02, here's the new one:


 untgz.zip
v0.03 (86.79 KiB) Downloaded 125 times
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-12T04:13:42+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Here are most of the converted pictures from the example TGA's that were uploaded:



TE40S11C.JPG (34.95 KiB) Viewed 361 times





TE40S21C.JPG (35.03 KiB) Viewed 361 times





TF7EB91C.JPG (27.64 KiB) Viewed 360 times





TF10S11C.JPG (47.2 KiB) Viewed 359 times





TF10S21C.JPG (47.23 KiB) Viewed 357 times





THMEAL1C.JPG (4.2 KiB) Viewed 355 times





THMEAM1C.JPG (5.32 KiB) Viewed 354 times





THMEAN1C.JPG (1.66 KiB) Viewed 353 times
## Post #22
- Username: mouzafc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2010 6:00 am
- Post datetime: 2010-02-08T20:50:45+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

Hi, I'm trying to use the utility "UNTGZ" but I keep on getting the error message : "Component 'mscomctl.ocx' or one of its dependencies not correctly registered: a file is missing or invalid. I've been trying it on my brand new Windows 7 and on my old Windows XP, but I still get the message on both machines. I reaaly would like to recapture the images from this great game and maybe try to rebuild a little interactivity and some of the panos...

Thanks for your help and go on doing such a great job.

Regards,
## Post #23
- Username: mouzafc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 05, 2010 6:00 am
- Post datetime: 2010-02-08T21:02:43+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

By the way, did you also manage to find out :
- what the raw files are and how to convert them in a usable format
- how the avi files can be converted in a more friendly format (color and sound don't play properly...)

Thanks
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-02-09T05:16:35+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

The error is self-explanatory. You are missing a standard windows file, or it is of a version not supported by the new WIndows 7. Try to see in Windows/system32 if it is there. If not, download it, and save it in the folder of UnTGZ. See if that works.
## Post #25
- Username: bmn
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2010-08-16T20:18:48+00:00
- Post Title: Re: Zork Nemesis/Zork Grand Inquisitor Image (TGA) Format

> Reply from mouzafc
>
> By the way, did you also manage to find out :
- what the raw files are and how to convert them in a usable format
- how the avi files can be converted in a more friendly format (color and sound don't play properly...)

Thanks

I have the same question. Additionally, I try to find out how the WAVE files are compressed.

In my German version of Zork Nemesis I have multiple IFP-files which seem to be soundfiles indeed. Some are compressed, but zwo (translated one) are normal RIFF WAVES. I believe that they are compresses also with LZSS. Later I will upload some samples.

PS:

> Reply from Mr.Mouse
>
> By the way, I'm 99% sure the programmers of Zork have used this code to achieve the decompression

Cannot be. The code is (C) 2000, but Zork Nemesis (I think first Zork which had "TGZ") is released 1996.
