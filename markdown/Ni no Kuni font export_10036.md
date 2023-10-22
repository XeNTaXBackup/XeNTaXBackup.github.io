## Post #1
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-13T15:33:12+00:00
- Post Title: Ni no Kuni font export

I want to translate this game on my language. I unpacked the sdat, adat, zarc, could change text and pack back. But the game does not support cyrillic. I found a font but I can not understand in what format they are.

i upload font from demo version game

```
http://www.mediafire.com/?8le5fdq86gjs67d
```
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-13T22:37:10+00:00
- Post Title: Ni no Kuni font export

chrrox posted an image to dds converter script here: [viewtopic.php?f=10&t=5037](http://forum.xentax.com/viewtopic.php?f=10&t=5037)
I tried it but the output still looks not right.
## Post #3
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-14T04:50:06+00:00
- Post Title: Ni no Kuni font export

I got a dds file using a script. But it looks like this. I can not understand what is wrong. too little experience I have.

[](http://imageshack.us/photo/my-images/132/ftsyshummb36p.png/)
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-15T12:21:05+00:00
- Post Title: Ni no Kuni font export

> Reply from dodther
>
> I got a dds file using a script. But it looks like this. I can not understand what is wrong. too little experience I have.
That's what I meant with "looks not right". But there is a pattern at least. I'll have a second look into this later on.

I don't have much clue about the DDS imageformat so the only thing I could do was trying to find some variables. The width and height of the image are stored at 0xB8 and 0xBA in two bytes and the size of the image is stored at 0xC2 in the p3img file. That is what I get by feeding the p3igg into tileggd with the right dimensions:
[http://imageshack.us/photo/my-images/62 ... p3igg.png/](http://imageshack.us/photo/my-images/62/ftsyshummb36pp3igg.png/)
## Post #5
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-16T05:32:53+00:00
- Post Title: Ni no Kuni font export

wrong script.
me talk that need use 8.8 AL 16bpp | alpha/luminance 2048 x 512
[http://www.mediafire.com/?e73i1jku5yd1e78](http://www.mediafire.com/?e73i1jku5yd1e78)

[](http://imageshack.us/photo/my-images/338/ftsyshummb36p.png/)

but Photoshop see only RGB + alpha. but there is one more layer
## Post #6
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-16T09:25:27+00:00
- Post Title: Ni no Kuni font export

Good you know some details. I'm curious how you found out.
I would try to create a dds with the properties you specified and copy the header. Try to add the imagedata of your fontfile after the header and look whats coming out.
## Post #7
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-18T02:23:09+00:00
- Post Title: Ni no Kuni font export

i did it!

[](http://imageshack.us/photo/my-images/688/rusk.jpg/)

need use 8.8 AL 16bpp | alpha/luminance 2048 x 1024

and font contain cyrillic character
## Post #8
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-18T08:36:27+00:00
- Post Title: Ni no Kuni font export

Yeah, n1. Would you mind explaining how you did it in detail?
Used Photoshop plugin to save a 8.8 AL 16bpp with the right size and pasted the igg into it? What about the font that was still visible even after turning the channels off?
## Post #9
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-18T15:55:22+00:00
- Post Title: Ni no Kuni font export

i create in photoshop bank image 2048х1024
save as 8.8 AL 16bpp
open with HxD and replase header
## Post #10
- Username: xujozer
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 07, 2011 1:36 pm
- Post datetime: 2013-01-27T02:35:02+00:00
- Post Title: Ni no Kuni font export

Hi, can you tell me what was the tool used to extract the texts? I also would like to translate the game into my language.
