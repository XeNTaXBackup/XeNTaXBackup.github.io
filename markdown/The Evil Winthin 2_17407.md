## Post #1
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2017-12-16T13:55:59+00:00
- Post Title: The Evil Winthin 2

Hi!
I've unpacked the game's language files with this script: [http://aluigi.altervista.org/bms/the_evil_within_2.bms](http://aluigi.altervista.org/bms/the_evil_within_2.bms) (quick bms)
I've the autoi script to the lanb file
I want to translate the game, but I can not repack the file 
Can someone help you in it?
## Post #2
- Username: halfway
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Aug 24, 2017 1:50 pm
- Post datetime: 2017-12-24T19:08:32+00:00
- Post Title: The Evil Winthin 2

> Reply from Zotya0330
>
> Hi!
I've unpacked the game's language files with this script: http://aluigi.altervista.org/bms/the_evil_within_2.bms (quick bms)
I've the autoi script to the lanb file
I want to translate the game, but I can not repack the file 
Can someone help you in it?
wath?!  edit text files? can you give me that script?
## Post #3
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-04-07T09:21:14+00:00
- Post Title: The Evil Winthin 2

I send a message
## Post #4
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-04-07T09:21:45+00:00
- Post Title: The Evil Winthin 2

UP.
## Post #5
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-12T06:33:27+00:00
- Post Title: The Evil Winthin 2

Is there no solution for backpacking?
## Post #6
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-05-12T16:12:13+00:00
- Post Title: The Evil Winthin 2

> Reply from Zotya0330
>
> Is there no solution for backpacking?

quickbms can import files... you know that, right?
did you know about repack with QuickBMS?
Did you try It? (Sorry if i was ask a wrong question)
## Post #7
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-12T17:03:05+00:00
- Post Title: The Evil Winthin 2

Yeah I know
I tried
## Post #8
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-05-16T05:39:23+00:00
- Post Title: The Evil Winthin 2

Good news, finally... I found a way to do that(for font and text and voice)
I wil share this information soon... Just wait for a while
## Post #9
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-19T07:20:48+00:00
- Post Title: The Evil Winthin 2

Cool! I can't wait!
## Post #10
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-25T15:59:28+00:00
- Post Title: The Evil Winthin 2

Any progress with repack?
## Post #11
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2018-06-01T14:36:52+00:00
- Post Title: The Evil Winthin 2

*.PTR

```
UINT32 - version
UINT32 - splited to 4 parts and XORed first 32768 bytes (32 KB) PKR MD5
UINT32 - splited to 4 parts and XORed decompressed PTR MD5

```


You should compress PTR file. It's work fine with C# DeflateStream. And you don't need compress PKR data.
## Post #12
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2018-06-02T03:10:20+00:00
- Post Title: The Evil Winthin 2

> Reply from ripper
>
> Code: Select allUINT32 - splited to 4 parts and XORed first 32768 bytes (32 KB) PKR MD5
UINT32 - splited to 4 parts and XORed decompressed PTR MD5Great research! Can you explain more about this two fields?
## Post #13
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2018-06-02T15:18:53+00:00
- Post Title: The Evil Winthin 2

> Reply from delutto
>
> ripper wrote:Code: Select allUINT32 - splited to 4 parts and XORed first 32768 bytes (32 KB) PKR MD5
UINT32 - splited to 4 parts and XORed decompressed PTR MD5
Great research! Can you explain more about this two fields?
common.ptr and common.pkr as example.
On the first image we skip header (0x10 bytes), select next 0x8000 bytes and calculate MD5 and get AAA643D74BB3433E09F662006A05EDB8

[](https://img.hurtom.com/i/2018/06/img1.png)

Then (img2) we split this hash to 4 parts and XOR it. 

```

```

[](https://img.hurtom.com/i/2018/06/img2.png)

As i promise Zotya0330. I'll share tool source when return to home, monday-tuesday.
## Post #14
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2018-06-03T19:35:05+00:00
- Post Title: The Evil Winthin 2

> Reply from ripper
>
> *.PTR
Code: Select allUINT32 - XORed by 0xFADC4688 decompressed PTR size
UINT32 - version
UINT32 - splited to 4 parts and XORed first 32768 bytes (32 KB) PKR MD5
UINT32 - splited to 4 parts and XORed decompressed PTR MD5


You should compress PTR file. It's work fine with C# DeflateStream. And you don't need compress PKR data.

Thank you a lot ripper! Finally I was able to add Import Mode to my tool. [Download link](http://zenhax.com/viewtopic.php?f=9&t=5088&p=35555#p35555)
I could not make it's work with compressed data, only works with uncompressed data.
## Post #15
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2018-06-05T17:38:06+00:00
- Post Title: The Evil Winthin 2

As i promised, here is my [sources](https://github.com/ripper1692/STEMUtil). Compiled binary in bin/Debug folder.

Usage for extract data:
1. Click PTR File "..." button and choose ptr file (note: pkr file must be placed on the same level with ptr, or 1 level above, like in game directory);
2. If needed click Extract directory "..." button and choose preferred directory.

Usage for import data:
1. Click Data directory "..." button and choose directory with extracted data (note: this program import only self-extracted files);
2. If needed click PKR/PTR File "..." button and choose preferred directory and filename.

This tool convert lanb files to txt (same as bms script format) and 48.dat font map files to xml like format.

Fonts in bimage files. If you see in xml data x coordinate more than image width it means that you need select image alpha channel.
In game little bit more than 58 763 words.
## Post #16
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-06-06T16:34:01+00:00
- Post Title: Re: The Evil Winthin 2

Problem!
In .xml files; bearingX is advanceX! Not a bX to bring offset to right! Actully you set wrong name

Replace AdvanceX to bearinX, you set worng name...

And also; you must change your source to creat a new 48.dat with added characters, not inject or insert value's...
## Post #17
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-06-09T14:53:18+00:00
- Post Title: Re: The Evil Winthin 2

And how to edit font files?
## Post #18
- Username: ripper
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Nov 20, 2014 4:52 am
- Post datetime: 2018-07-31T18:01:08+00:00
- Post Title: Re: The Evil Winthin 2

As i need recreate fonts (because english letters slight bolder than cyrillic) and You guys have some trouble with that, here detailed example.
There is big topic about Id tech textures, if you are interested - [here link](http://forum.xentax.com/viewtopic.php?f=18&t=16112).

Before we start, you'll need some hex editor, we will put in and out image data from .bimage files.

Let's go:

1. After extracting pkr data, go to <extracted directory>\generated\textures\fonts and you'll see following folders
[](https://img.hurtom.com/image/it6)

If your writting system alphabetical, as mine, you need change next fonts
[](https://img.hurtom.com/image/it3)

If not, you might choose other fonts.


2. Go to first directory, fot_newrodinpro_db, and open 48.bimage in hex editor. You will see something like this
[](https://img.hurtom.com/image/itO)

2.1. Find Goto function (in some editors Ctrl+G) set offset to 12 (dec) or 0C (hex) and press enter (or "Go" button)
[](https://img.hurtom.com/image/itR)

2.2. Here is our image width - 1000 px
[](https://img.hurtom.com/image/itd)

2.3. Now find goto function once again and set offset to 16 (dec) or 10 (hex) and press enter (or "Go" button)
[](https://img.hurtom.com/image/itZ)

2.4. Here is our image height  - 2032 px
[](https://img.hurtom.com/image/itj)

2.5. Now goto find goto function once again and set offset to 62 (dec) or 3E (hex) and press enter (or "Go" button)
[](https://img.hurtom.com/image/it1)

2.6. Press Ctrl+Shift+End and copy (Ctrl+C) selected data (if nothing happened, click on the underscored symbol and press again)
2.7. Create new file (Ctrl+N),  paste (Ctrl+V) data and save file (Ctrl+S). I named this file fot_newrodinpro_db.raw
2.8. Now you need create blank dds image, for these purposes I use GIMP. So open GIMP, create a new file with our image size and click OK
[](https://img.hurtom.com/image/itD)

2.9. Now click File -> Export as (Ctrl+Shift+E) choose DDS image from dropdown list
2.10. Select compression BC3/DXT5, no mipmaps, no additional options and save file
[](https://img.hurtom.com/image/itF)

2.11. Open created dds image in hex editor and goto 128 (dec) or 80 (hex) offset.
[](https://img.hurtom.com/image/itS)

2.12. Press Ctrl+Shift+Home and copy selected data (if nothing happened check 2.6)
2.13. Paste this data at the beginning of fot_newrodinpro_db.raw 
[](https://img.hurtom.com/image/its)

2.14. Save file as fot_newrodinpro_db.dds

Note: same thing with other files. Here sizes, start at 2.5 step for copy other data
fot_newrodinpro_db - 1000x2032
fot_udkakugo_large_pr6_m - 1112x2264
tng_font_cn - 860x2872
tng_font_ko - 840x1600
tng_font_lang - 368x656
tng_font_zh - 1076x2296
tng_gothic_m - 260x752


3. Now is time for edit image, i'll use Adobe Photoshop with NVIDIA Texture Tools because i'm still don't learned how to use others (GIMP, Paint .NET, Krita). You need any image editor with ability work with image channels.
Little about image. Image splitted by 2 parts, left part placed in red channel, right part - alpha channel. So real width of images are multiplited by 2, remember that, when you'll setting coordinates in xml-like font map file. Real image looks something like this
[](https://img.hurtom.com/image/itc)

When you finish save image as DXT5
[](https://img.hurtom.com/image/itL)


4. So, when you`ll finish with images, time add them to font map. Open xml-like file <extracted directory>\fonts\fot_newrodinpro_db\48.dat.xml
4.1. First thing what you need to do - update chars count, if you need add 1, 2, 5, 10 etc. chars, add to chars number. In current version fot_newrodinpro_db has 1920 chars, i need add only 8, so for me chars count is 1928.
[](https://img.hurtom.com/image/it0)

4.2. Now going to [UTF-8 encoding table and Unicode characters](https://www.utf8-chartable.de/unicode-utf8-table.pl?utf8=-&unicodeinhtml=dec) resource and choose your range, for me is U+0400 ... U+04FF: Cyrillic. Set "numerical HTML encoding of the Unicode character" param to decimal
4.3. When i added characters to DOOM (2016) weird thing happened. If i added char at the end of list, game don't recognized it, so i recommend add chars by id order. In my case first letter with id 1028
[](https://img.hurtom.com/image/itY)

4.4. Copy closest row, paste after and set id
[](https://img.hurtom.com/image/itG)

4.5. Now go to our image and get coordinates. In my case letter on the red channel so his X=528, Y=240, width=29, height=35 (if you add chars to alpha channel add to coordinate image width). Keep in mind, in program bearing is advance and advance is bearing. I missnamed params when develop tool. If bearing(advance) value > 127 substract 256, just wrong variable type.
[](https://img.hurtom.com/image/itn)
[](https://img.hurtom.com/image/itV)


5. Now you need only put in image data to bimage file and import back to pkr.
5.1. Open dds image and goto offset 128
5.2. Press Ctrl+Shift+End and copy selected data (if nothing happened check 2.6)
5.3. Open .bimage file and goto offset 62
5.4. Press Ctrl+Shift+End, paste previously copied data (if nothing happened check 2.6) and save file.

That's all, do same with other fonts, import data to pkr and enjoy your fonts.

Note: on version 1.0 fonts changed only, if you import map and image to p1_loc_01.pkr/ptr file. So if you try import to the other file and nothing change, try import to p1_loc_01.

Sorry for this long text. I would like hide all this in spoiler, but spoiler tag doesn't work.
Oh, and sorry for my english.
