## Post #1
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-09T23:04:23+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

The meshes and Textures appear to be inside .bnd files. Armored Core Formula Front for the PSP and Chromehounds, by the same developer appear to use the same format but the BMS scripts I've found for those games don't seem to work on these.

Running offzip with these parameters: "c:\offzip\offzip.exe -a c:\file.bin c:\extract 0x0" produces several .smd, .dat, .flv, (not flash video) and .xpr files.

running unbundler.exe from the XSDK extracts the .tga textures from these .xpr files.

Another game I'm looking to extract models from, project sylpheed, as well as some dead or alive and soul calibur games use .xpr files for models and textures so I'm assuming it's the same here.

Sample Archive Data: sub_head.bnd
Sample XPR Data: 001a6090.xpr

[https://skydrive.live.com/#cid=E74D852E ... DF762F!108](https://skydrive.live.com/#cid=E74D852ED8DF762F&id=E74D852ED8DF762F!108)
## Post #2
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-13T05:31:42+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

flv[FLVER] is the model.
same as PS3 Another Century's Episode R
## Post #3
- Username: TallgeeseIV
- Rank: beginner
- Number of posts: 39
- Joined date: Mon Nov 15, 2010 10:32 am
- Post datetime: 2011-12-13T17:18:01+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

Ohhh, you're right, i remember seeing that topic where it was pointed out too. thanks a bunch. I'll add a sample .flv file soon.
## Post #4
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2011-12-17T01:37:55+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

i am guessing the flv file is the same as in dark souls. There is a blender script here for flver files but it doesnt really work, maybe modifiable. Interested in your progress!
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-12-17T10:28:04+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

Dark Souls and Armored Core For Answer are of different flv format.
## Post #6
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2011-12-17T14:54:44+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

yeah sadly you are right. Theres an flver importer here for blender but it breaks while importing the dark souls flv.
## Post #7
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T18:01:18+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

hmm the header seems similar though

46 4C 56 45 52 00 42
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T19:50:40+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

There doesn't seem to be any flv samples.
## Post #9
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T20:40:15+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

Here are some Armored core FLVs
[http://xis9.com/armorecore.zip](http://xis9.com/armorecore.zip)
Here are Dark Souls FLVs that were found inside a main archive
[http://xis9.com/ds1.zip](http://xis9.com/ds1.zip)
Here are FLVER files found inside files that were further unpacked
[http://xis9.com/ds2.zip](http://xis9.com/ds2.zip)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T21:44:38+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

Now all we need is the flver importer that was written but removed from MF lol

I can see the vertices and indices, along with the texNames and stuff, but if it's already been done hopefully someone still has it.
## Post #11
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T21:54:33+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

the blender importer?
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T22:35:39+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

Ya I think that's what it was.
## Post #13
- Username: hatyn
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Dec 17, 2011 3:30 am
- Post datetime: 2012-01-08T22:40:26+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

its still available in the FLVER thread [viewtopic.php?f=16&t=6955](http://forum.xentax.com/viewtopic.php?f=16&t=6955) but it doesnt work with this file type. I was hoping someone posts the FLVER files from that cute psp game so we can see what the difference is.

here it is [http://xis9.com/import-flver.blend](http://xis9.com/import-flver.blend)
## Post #14
- Username: unkownac
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 18, 2014 2:15 pm
- Post datetime: 2014-08-18T08:05:38+00:00
- Post Title: [Request] Armored Core For Answer Models/Textures

> Reply from TallgeeseIV
>
> The meshes and Textures appear to be inside .bnd files. Armored Core Formula Front for the PSP and Chromehounds, by the same developer appear to use the same format but the BMS scripts I've found for those games don't seem to work on these.

Running offzip with these parameters: "c:\offzip\offzip.exe -a c:\file.bin c:\extract 0x0" produces several .smd, .dat, .flv, (not flash video) and .xpr files.

running unbundler.exe from the XSDK extracts the .tga textures from these .xpr files.

Another game I'm looking to extract models from, project sylpheed, as well as some dead or alive and soul calibur games use .xpr files for models and textures so I'm assuming it's the same here.

Sample Archive Data: sub_head.bnd
Sample XPR Data: 001a6090.xpr

https://skydrive.live.com/#cid=E74D852E ... DF762F!108

I don't understand why i only get .dat format file
