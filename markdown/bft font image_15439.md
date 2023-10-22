## Post #1
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-02T16:29:35+00:00
- Post Title: bft font image

It contains font table and graphic data, however I don't have an idea how to get texture. Does any one can look at it?

Samples [https://www.sendspace.com/file/4rsl7e](https://www.sendspace.com/file/4rsl7e)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-04T10:08:05+00:00
- Post Title: bft font image

Here's what I found out about the file format:

```

byte header[12]; // it's the same in both .unpack files

int characterCount;

struct charInfo {
  short keycode;
  byte zero; // always zero
  byte xOffset; // not sure about the offsets
  byte yOffset;
  byte horOffset;
  byte charWidth;
  byte charHeight;
  int unknown; // initial value = 0x55800000, increases by 0x56 each line
};


// @0x1525C

struct charData {
  byte charBitmap[19 * 36];
  int unknown; // alwys zero? padding?
};


// @0x4D160C
// don't know what that section is

int unknownCount;

struct unknown {
  short;
  short;
  int;
};
```
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-04T17:55:30+00:00
- Post Title: bft font image

texturefinder reveals more about main_font.unpack:



main_font-unpack.JPG (134.38 KiB) Viewed 195 times
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-04T19:06:38+00:00
- Post Title: bft font image

The font characters are simple 8-bit grayscale bitmaps with a fixed size of 19x36 pixels per character.
Here's a screenshot of the characters in main_font.unpack, mapped onto a 1024 pixels wide texture atlas:



screenshot.png (119.21 KiB) Viewed 193 times
## Post #5
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-05T00:25:17+00:00
- Post Title: bft font image

> Reply from herbert3000
>
> The font characters are simple 8-bit grayscale bitmaps with a fixed size of 19x36 pixels per character.
Here's a screenshot of the characters in main_font.unpack, mapped onto a 1024 pixels wide texture atlas:
screenshot.png

Oh, did you open it as a raw file from Photoshop? Is there a specific height?
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-05T15:35:25+00:00
- Post Title: bft font image

> Reply from adol365
>
> Oh, did you open it as a raw file from Photoshop? Is there a specific height?Actually I wrote a simple java program that converts the font file into a raw image.


 fontToRaw.zip
(3.32 KiB) Downloaded 113 times
## Post #7
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-06T02:14:12+00:00
- Post Title: bft font image

> Reply from herbert3000
>
> adol365 wrote:Oh, did you open it as a raw file from Photoshop? Is there a specific height?Actually I wrote a simple java program that converts the font file into a raw image.
fontToRaw.zip

Uhm.. unfortunately I had never learned Java.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-06T04:22:54+00:00
- Post Title: bft font image

> Reply from adol365
>
> Uhm.. unfortunately I had never learned Java.
just drop your samples in the folder with the fontToRaw java files
open a command prompt there and type
java fontToRaw
press Enter then it'll ask for a file name like this
Enter filename:
then you can type the name of your sample file and press Enter
and you will get a raw image file of that sample in that folder
that you can open in Photoshop with the dimensions in the file name
## Post #9
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-06T20:34:38+00:00
- Post Title: bft font image

@adol365: Just a quick question. At the current state the program outputs this data:
[https://www.mediafire.com/?7acvohe2y3tcb79](https://www.mediafire.com/?7acvohe2y3tcb79)
Is this sufficient for you to edit the font?  If yes, I could start to write the repacker.
## Post #10
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-07T00:33:13+00:00
- Post Title: bft font image

> Reply from herbert3000
>
> @adol365: Just a quick question. At the current state the program outputs this data:
https://www.mediafire.com/?7acvohe2y3tcb79
Is this sufficient for you to edit the font?  If yes, I could start to write the repacker.

Yes, it is sufficient for me. By the way, is horOffset means xadvance?
## Post #11
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-07T02:34:33+00:00
- Post Title: bft font image

I pretty sure I mixed up the offsets (x/y/hor).
The value that is currently named horOffset is high for characters like "." and "," so I think that's the actual y-offset, is that possible?
## Post #12
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-07T05:30:41+00:00
- Post Title: bft font image

> Reply from herbert3000
>
> I pretty sure I mixed up the offsets (x/y/hor).
The value that is currently named horOffset is high for characters like "." and "," so I think that's the actual y-offset, is that possible?

But isn't you already declare yoffset before horOffset?
I'm not sure exactly what horOffset means but it doesn't quiet matter if one can make a new font.
## Post #13
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-08T23:12:21+00:00
- Post Title: bft font image

> Reply from adol365
>
> But isn't you already declare yoffset before horOffset?
I'm not sure exactly what horOffset means but it doesn't quiet matter if one can make a new font.xOffset, yOffset and horOffset were my first guess for the last 3 values but I guess I was wrong 
If you figure out the true meaning, I can correct that in the program.

But you are right, for making a new font, the names of the keywords are irrelevant.
I should have named them unknown1, unknown2 and unknown3
## Post #14
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-09T02:19:18+00:00
- Post Title: bft font image

> Reply from herbert3000
>
> adol365 wrote:But isn't you already declare yoffset before horOffset?
I'm not sure exactly what horOffset means but it doesn't quiet matter if one can make a new font.xOffset, yOffset and horOffset were my first guess for the last 3 values but I guess I was wrong 
If you figure out the true meaning, I can correct that in the program.

But you are right, for making a new font, the names of the keywords are irrelevant.
I should have named them unknown1, unknown2 and unknown3

In my opinion, the easy way to confirm what is the meaning of UNK1, 2, 3 is that modify fnt table data and take a test in the game.
## Post #15
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-11-14T07:34:20+00:00
- Post Title: bft font image

Here's a converter for the file main_font.unpack:


 FontTools.zip
(197.58 KiB) Downloaded 70 times

Usage: Run the .bat file,
to unpack the file enter: main_font.unpack
to repack the file enter: main_font.unpack.txt

Backup your original files because this tool will overwrite existing files without confirmation.
## Post #16
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2016-11-16T08:56:30+00:00
- Post Title: Re: bft font image

> Reply from herbert3000
>
> Here's a converter for the file main_font.unpack:
FontTools.zipUsage: Run the .bat file,
to unpack the file enter: main_font.unpack
to repack the file enter: main_font.unpack.txt

Backup your original files because this tool will overwrite existing files without confirmation.

Thank you!   When I have time, I will check it.
## Post #17
- Username: adol365
- Rank: advanced
- Number of posts: 70
- Joined date: Fri Nov 21, 2014 7:21 pm
- Post datetime: 2017-01-04T16:42:58+00:00
- Post Title: Re: bft font image

> Reply from herbert3000
>
> Here's a converter for the file main_font.unpack:
FontTools.zipUsage: Run the .bat file,
to unpack the file enter: main_font.unpack
to repack the file enter: main_font.unpack.txt

Backup your original files because this tool will overwrite existing files without confirmation.

Could you update tool for the other files? [https://www.sendspace.com/file/8orrce](https://www.sendspace.com/file/8orrce)
And is it possible export/repack font in png type?
