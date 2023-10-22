## Post #1
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-01T12:04:12+00:00
- Post Title: [Wolfenstein] .bimage conversion

Hi, can someone help me to convert this raw image(bimage) to other format and vice versa..? <file removed due forum rules violation>
## Post #2
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-01T13:12:20+00:00
- Post Title: [Wolfenstein] .bimage conversion

It is very simple format, it is RAW with 72bit header  Open with PS
## Post #3
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-06-01T16:43:21+00:00
- Post Title: [Wolfenstein] .bimage conversion

Yes, it's simple format
0x3c - width
0x40 - height 
0x44 - size in bytes
0x48 - raw data
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-06-01T17:02:57+00:00
- Post Title: [Wolfenstein] .bimage conversion

Yeah, Thief is completely right, just 1 small thing

Setup for PS:

```
Bits : 8
Header : 72
```


010 Template :

```
uint width;
uint hegiht;
uint sizeD;
byte DATA[sizeD];
```
## Post #5
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-06-01T19:41:26+00:00
- Post Title: [Wolfenstein] .bimage conversion

> Reply from michalss
>
> Yeah, Thief is completely right, just 1 small thing

Setup for PS:
Code: Select allChannel : 1
Bits : 8
Header : 72

010 Template :
Code: Select allFSeek(60);
uint width;
uint hegiht;
uint sizeD;
byte DATA[sizeD];

Thanks for your replies guys!
## Post #6
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-06T18:11:16+00:00
- Post Title: [Wolfenstein] .bimage conversion

I've found there's actually a bit more to the *.bimage format. The above information is correct with single channel 8 bit textures, but there are more types of textures with varying formats stored in the *.bimage format.

So far I've found they are using *.bimage to store headerless DDS files, of type DXT5 (and some ycocg-DXT5, more on that later).

For regular DXT5 images, you can remove the 72 byte *.bimage header (saving the Width, Height, and Size variables, then tack on a 128 byte DDS header from a DXT5 image, and replace those saved variables here:

0x0C - height 
0x10 - width
0x14 - size in bytes
(more on DDS header here: [http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb943982%28v=vs.85%29.aspx) )

Should open normally in any program capable of reading DDS.

Now, for ycocg-DXT5, this is a special flavor of DDS using a custom color-space which was invented jointly by ID and Nvidia (whitepaper: [http://www.nvidia.com/object/real-time- ... ssion.html](http://www.nvidia.com/object/real-time-ycocg-dxt-compression.html)) 

The format is completely identical to DXT5, but you need a program that can read the special colorspace. So far I have only found one:

[http://www.gimp.org/](http://www.gimp.org/)  Using the custom DDS plugin found here:  [https://code.google.com/p/gimp-dds/](https://code.google.com/p/gimp-dds/)

The modification procedure is the same as outlined above, with one extra step at the end. In order for Gimp to know this DDS is using Ycocg colorspace, an additional flag has to be put into the header, in the "Reserved" space of the DDS header.


There are two flavors of Ycocg, the normal which is designated YCG1 and a "Scaled" version that is designated YCG2.  With that special header in place, GIMP will recognize the DDS as using one or the other, and decode it properly.

Now that I've nailed down the *Bimage format completely, hopefully i can get to work on those Megatextures nobody has still cracked.
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-08T05:42:33+00:00
- Post Title: [Wolfenstein] .bimage conversion

> Reply from volfin
>
> I've found there's actually a bit more to the *.bimage format. The above information is correct with single channel 8 bit textures, but there are more types of textures with varying formats stored in the *.bimage format.

So far I've found they are using *.bimage to store headerless DDS files, of type DXT5 (and some ycocg-DXT5, more on that later).

For regular DXT5 images, you can remove the 72 byte *.bimage header (saving the Width, Height, and Size variables, then tack on a 128 byte DDS header from a DXT5 image, and replace those saved variables here:

0x0C - height 
0x10 - width
0x14 - size in bytes
(more on DDS header here: http://msdn.microsoft.com/en-us/library ... s.85).aspx )

Should open normally in any program capable of reading DDS.

Now, for ycocg-DXT5, this is a special flavor of DDS using a custom color-space which was invented jointly by ID and Nvidia (whitepaper: http://www.nvidia.com/object/real-time- ... ssion.html) 

The format is completely identical to DXT5, but you need a program that can read the special colorspace. So far I have only found one:

http://www.gimp.org/  Using the custom DDS plugin found here:  https://code.google.com/p/gimp-dds/

The modification procedure is the same as outlined above, with one extra step at the end. In order for Gimp to know this DDS is using Ycocg colorspace, an additional flag has to be put into the header, in the "Reserved" space of the DDS header.


There are two flavors of Ycocg, the normal which is designated YCG1 and a "Scaled" version that is designated YCG2.  With that special header in place, GIMP will recognize the DDS as using one or the other, and decode it properly.

Now that I've nailed down the *Bimage format completely, hopefully i can get to work on those Megatextures nobody has still cracked.

I have try this method and nope was not able to make it work, on the other hand this is RAW bitmap image without doubs. No need to do some extra steps, PS and my template do all work. At least for fonts, rest textures you could be right, never check this.
## Post #8
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2014-07-08T17:45:54+00:00
- Post Title: [Wolfenstein] .bimage conversion

> Reply from michalss
>
> volfin wrote:I've found there's actually a bit more to the *.bimage format. The above information is correct with single channel 8 bit textures, but there are more types of textures with varying formats stored in the *.bimage format.

So far I've found they are using *.bimage to store headerless DDS files, of type DXT5 (and some ycocg-DXT5, more on that later).

For regular DXT5 images, you can remove the 72 byte *.bimage header (saving the Width, Height, and Size variables, then tack on a 128 byte DDS header from a DXT5 image, and replace those saved variables here:

0x0C - height 
0x10 - width
0x14 - size in bytes
(more on DDS header here: http://msdn.microsoft.com/en-us/library ... s.85).aspx )

Should open normally in any program capable of reading DDS.

Now, for ycocg-DXT5, this is a special flavor of DDS using a custom color-space which was invented jointly by ID and Nvidia (whitepaper: http://www.nvidia.com/object/real-time- ... ssion.html) 

The format is completely identical to DXT5, but you need a program that can read the special colorspace. So far I have only found one:

http://www.gimp.org/  Using the custom DDS plugin found here:  https://code.google.com/p/gimp-dds/

The modification procedure is the same as outlined above, with one extra step at the end. In order for Gimp to know this DDS is using Ycocg colorspace, an additional flag has to be put into the header, in the "Reserved" space of the DDS header.


There are two flavors of Ycocg, the normal which is designated YCG1 and a "Scaled" version that is designated YCG2.  With that special header in place, GIMP will recognize the DDS as using one or the other, and decode it properly.

Now that I've nailed down the *Bimage format completely, hopefully i can get to work on those Megatextures nobody has still cracked. 

I have try this method and nope was not able to make it work, on the other hand this is RAW bitmap image without doubs. No need to do some extra steps, PS and my template do all work. At least for fonts, rest textures you could be right, never check this.

yes, for a single-plane grescale image, you can just use RAW import, as I mentioned. But not all *.bimages are in that format. This is for full color 24 bit images. For example the sky used in levels [http://i.imgur.com/FkkG0D6.jpg](http://i.imgur.com/FkkG0D6.jpg) 

This was extracted from 'chunk1.resources', stored in 'generated\textures\linear_ycocgdxt5_models\mapobjects\skies\c01p1_sky.bimage' It was 4096x2048 24 bit color, Ycocg DXT5 compressed. (it was in fact the folder name 'linear_ycocgdxt5_models' that first gave me a clue what format they were using) If you try to load that file using RAW, it will fail.
## Post #9
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2014-07-11T09:27:56+00:00
- Post Title: [Wolfenstein] .bimage conversion

The font textures are also in .bimage files. Michalss' 010 template should be applied to those and after that it can be edited with PS?
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-07-11T19:08:57+00:00
- Post Title: [Wolfenstein] .bimage conversion

> Reply from lostprophet
>
> The font textures are also in .bimage files. Michalss' 010 template should be applied to those and after that it can be edited with PS?

Yes that template works for Fonts never tested it for anything else!
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-07-18T11:00:58+00:00
- Post Title: [Wolfenstein] .bimage conversion

[out]
## Post #12
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-08-04T16:56:24+00:00
- Post Title: [Wolfenstein] .bimage conversion

[out]
## Post #13
- Username: Eugeny
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 03, 2015 11:55 pm
- Post datetime: 2015-07-04T06:00:33+00:00
- Post Title: [Wolfenstein] .bimage conversion

BIMAGE to DDS converter by MerlinSVK

```
# BIMAGE to DDS converter (PC/PS3)
# by MerlinSVK    Oct 2014
# version 1.1
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x59\x43\x47\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get NAME basename
string HNAME = NAME
string HNAME += ".head"
string NAME += ".dds"

get ASIZE asize
get ID long

if ID == "0x644FD853"      # PC
     goto 0x10
     endian big
     get WIDTH long
     get HEIGHT long
    endian little
     goto 0x42
     savepos START
    xmath DATASIZE "ASIZE - START"
    log HNAME 0 START   # save header for backward conversion
else
     goto 0xC
     endian big
     get WIDTH long
     get HEIGHT long
    endian little
     goto 0x3E
     savepos START
    xmath DATASIZE "ASIZE - START"
    log HNAME 0 START   # save header for backward conversion
endif

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 DATASIZE long

append
log MEMORY_FILE START DATASIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE
```
