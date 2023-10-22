## Post #1
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2020-08-12T02:40:45+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Looks like everything in this game is in a .pac container, looking at the header of the file it seems they are using an updated version of the one they used for Sonic Forces:




header.png (48.92 KiB) Viewed 1025 times



Which has a header that reads "PACx301L" and for which there's an experimental bms script:

[http://aluigi.altervista.org/bms/sfpac.bms](http://aluigi.altervista.org/bms/sfpac.bms)

Anyways, if anyone wants to try and extract stuff from them it doesn't seem to be compressed or encrypted, here are a few example files:

[https://mega.nz/folder/kHh2XAxJ#3x1UJrYQObx-t1Gsu4LOLw](https://mega.nz/folder/kHh2XAxJ#3x1UJrYQObx-t1Gsu4LOLw)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-12T15:48:56+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

You can use Switch Toolbox to unpack the archive properly. Model files are ".model" and seem to be same/similar to previous Hedgehog Engine games. I guess there should be bunch of importers around. If not you can try this for a quick OBJ output : [viewtopic.php?p=157955#p157955](https://forum.xentax.com/viewtopic.php?p=157955#p157955)
## Post #3
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2020-09-09T00:06:52+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

I'm slowly making a blender script for the hedgehog engine. Mesh and UV are easy. I'm still looking into how the normals are stored. I also have enough info for getting weights but just need to work on the skeleton's bone positions.
## Post #4
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2020-09-18T13:49:47+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

We are waiting for your script! Very-very!!!
## Post #5
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2020-10-06T15:07:56+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Yeah actually checking this topic every day ahah
## Post #6
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2021-01-15T19:08:52+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

A bit of a late reply but here is the script i've written so far. Even managed to get animations working for the most part. Code isnt perfect but it's worked well for me so far.

[Github Link](https://github.com/Turk645/Hedgehog-Engine-2-Mesh-Blender-Importer)
## Post #7
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-01-15T22:40:54+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

And what about textures??
## Post #8
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2021-01-16T05:13:10+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

> Reply from Darko ↑Sat Jan 16, 2021 6:40 am at Sat Jan 16, 2021 6:40 am
>
> 
And what about textures??


they are in standard dds format
## Post #9
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-01-16T07:18:58+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Thank you for creating the script! It certainly works with model files.
Like the killercracker script, the character animation doesn't work properly, are there any plans to fix it?
## Post #10
- Username: pox911
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Mar 08, 2018 11:55 am
- Post datetime: 2021-01-16T08:13:09+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

> Reply from einherjar007 ↑Sat Jan 16, 2021 3:18 pm at Sat Jan 16, 2021 3:18 pm
>
> 
Thank you for creating the script! It certainly works with model files.
Like the killercracker script, the character animation doesn't work properly, are there any plans to fix it?

can you give some examples? Admittedly most of my animation testing was using the the mario olympics animations and only a handfull of mech animations. One thing i noticed though is that sometimes the scale value has some weird values despite not being needed for the animation. I've been debating on putting a checkbox to toggle scale use.
## Post #11
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2021-01-21T07:54:09+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Hello, excuse me, are you going to publish the models to download? since I'm interested in the character Hatsuho Shinonome
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-01-21T08:30:19+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Asking for assets is forbidden here.
## Post #13
- Username: TheSuperSpinD
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 23, 2021 3:34 am
- Post datetime: 2021-01-22T20:40:43+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

Is there a way to find the passcode to unpack the initial PKG file everything is stored in?
## Post #14
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-01-30T23:21:06+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

thx for ur script first , but animation doing bad for me , im using a clean installed blender 2.91.2
## Post #15
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-02-08T00:28:33+00:00
- Post Title: Shin Sakura Taisen / Sakura Wars (PS4)

> Reply from TheSuperSpinD ↑Sat Jan 23, 2021 4:40 am at Sat Jan 23, 2021 4:40 am
>
> 
Is there a way to find the passcode to unpack the initial PKG file everything is stored in?

The passcode for any game available for downloading is "00000000000000000000000000000000" with fakepkg.
