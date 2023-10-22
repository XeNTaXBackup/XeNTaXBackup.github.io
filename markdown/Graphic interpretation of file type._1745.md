## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-23T19:19:40+00:00
- Post Title: Graphic interpretation of file type.

For me this is the ultimate and often the only search tool. I comb the file graphic interpretation in search of some signs of visual sense. Most often than not it requires tedious adjustment to bytes per row value. Most often you get the columns at best , but sometimes you can recognise some graphics. 
Few questions: 
* is graphic search a good practice, or rather just some kind of useless noob attempt because simply he does not know better 
* are there any sample pictures of file content or typical patterns, which could be used as a "tell tale" and some kind of indicator of their type?  
* are there any hex editors with graphic representation allowing change byte per row with arrow - fluid and fast search for pattern.
Thanks
## Post #2
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2006-02-24T01:41:53+00:00
- Post Title: Graphic interpretation of file type.

Well, I do know that .BMP and .TGA files can be 'viewed' in Notepad: Open the chosen file, turn off line wrap (if it's on), and change font settings to Courier New, font size 1; you should now see a rough overview of the image. This method can be as useful as the graphic representation in your hex editor.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-02-24T08:35:35+00:00
- Post Title: Graphic interpretation of file type.

> Reply from Xela
>
> For me this is the ultimate and often the only search tool. I comb the file graphic interpretation in search of some signs of visual sense. Most often than not it requires tedious adjustment to bytes per row value. Most often you get the columns at best , but sometimes you can recognise some graphics. 
Few questions: 
* is graphic search a good practice, or rather just some kind of useless noob attempt because simply he does not know better 
* are there any sample pictures of file content or typical patterns, which could be used as a "tell tale" and some kind of indicator of their type?  
* are there any hex editors with graphic representation allowing change byte per row with arrow - fluid and fast search for pattern.
Thanks

The method is only useful in case graphics haven't been compressed. Thus, for old to very old games you could try to tell by eye whether a piece may be graphics. In today's games, a lot of compression is used, so that makes the method almost impossible. 

In case of game archives, it is best if you know how a GRA works (game archive) and where the individual files are. So you can at least know where to look. A lot of the time authors use popular formats, such as BMP, DDS, TGA etc. You can identiy them by tags such as "BM" or "DDS". 

I think it would be interesting to see if a program could identify areas of graphics. Perhaps it is possible.
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-02-27T13:27:28+00:00
- Post Title: Graphic interpretation of file type.

There is a game of which GRA in known to me in fact quite well. That is Strike Fighters: Project 1 large cat (catalog) files containing all is needed to play it. The utility to open it is provided by the developer, so we know what is in each file well and we can and know how to modify them. But it is fascinating while knowing this content,  to see its graphic interpretation in hex and text format next to each other in the original untouched Cat using the hex editor. 

In fact similarities with recently sent TAW file are striking which is giving me some further clues what is what.
## Post #5
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-03T16:37:23+00:00
- Post Title: Graphic interpretation of file type.

It is actually very interesting and amazing how different formats of the files present themselves graphically. Perhaps if only some more time available some tutorials with samples would be good to have here. Yesterday I was looking at the same picture in different formats BMP and PCX. The shape or the outline of the picture in the first format (BMP) was clearly recognizable, but the same thing in PCX was total mish-mash. 

But then again I also realise as to why, the bitmap is "as is" and PCX is run length compressed.
## Post #6
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2006-03-05T15:36:24+00:00
- Post Title: Graphic interpretation of file type.

Try the file below.  It has really helped me a couple of times and is freeware.
[TextureFinder.v20.zip](https://xentaxbackup.github.io/file/629_TextureFinder.v20.zip)
## Post #7
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-05T16:44:29+00:00
- Post Title: Graphic interpretation of file type.

Perfect and thank you very much. This is what I was looking for- that adjustment of byte row width with arrow keys. Very smooth and fast.  
Let me know about other tools like this.
## Post #8
- Username: Meds
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Feb 26, 2006 10:16 am
- Post datetime: 2006-03-07T02:45:50+00:00
- Post Title: Graphic interpretation of file type.

How would one go about converting a raw image into the pixel format of 4444 = 12 + 4 with ImageMagick or anything else for that matter? I've been playing around with it, but it seems to always give me a very small image output and multiple images.
## Post #9
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-07T03:19:43+00:00
- Post Title: Graphic interpretation of file type.

16 bit Extended BMP

This format allows greater colour depth than 8 bit. Instead of 256 colours you could now use the full â€œHiColorâ€
## Post #10
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-03-07T19:35:09+00:00
- Post Title: Graphic interpretation of file type.

thanks Jasmine!!

it remember me a famous gfx grabber on amiga!!
## Post #11
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-09T23:02:05+00:00
- Post Title: Graphic interpretation of file type.

I have lately used quite extensively this Texture Finder brought by Jasmine for which big thanks again. The only gripe I have with the program that viewing window is so large that smaller texture files are very hard to recognize. Also I wonder what exactly "shift" and "skew" operation does to the pixels. Also cannot use palettized menu - why?  

In general this program shows that recognition of the content of file is very risky if relied exclusively on visual examination. Very easy to miss as the different formats of the same picture and even different channel settings withing the program may totaly obscure it.
## Post #12
- Username: bitterbanana
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Feb 09, 2005 9:02 am
- Post datetime: 2007-01-12T04:22:24+00:00
- Post Title: Graphic interpretation of file type.

> Reply from jasmine
>
> Try the file below.  It has really helped me a couple of times and is freeware.
That should be pinned up at the top of this forum.
