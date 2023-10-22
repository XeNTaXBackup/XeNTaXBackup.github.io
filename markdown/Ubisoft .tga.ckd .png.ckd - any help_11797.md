## Post #1
- Username: aptyp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 15, 2014 1:09 am
- Post datetime: 2014-08-17T04:48:39+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Yet another problem with Rayman Legends, Just Dance 2014, etc, image files. I tried all posted scripts, tools, none of which handle swizzled DDS DXT format.

that .bms also didn't work for this situation

```
get SIZE asize
math SIZE -= 0x34
string NAME += ".dds"
log NAME 0x34 SIZE
```

[tga-png-x360-ckd.zip](https://xentaxbackup.github.io/file/7668_tga-png-x360-ckd.zip)
## Post #2
- Username: aptyp
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-21T14:38:25+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Edit: Ok, I have gotten the files to load. Could you tell me which game this is, platform and provide some more samples?
## Post #3
- Username: aptyp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 15, 2014 1:09 am
- Post datetime: 2014-08-22T04:24:33+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Gh0stBlade tga's from Just Dance 5 2014 XBOX360
[jd5-tga-ckd.zip](https://xentaxbackup.github.io/file/7693_jd5-tga-ckd.zip)
## Post #4
- Username: aptyp
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-22T19:41:13+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Sorry, still not enough samples. It's DDS there are multiple types so I want to support them all. Furthermore, I'm concerned about how to correctly read the data located before/after the DDS type info. As a result, I will need lots of samples so I can see the relation between the counts/size of that data otherwise It will not be compatible with other files.

Edit: You can drop me more in a PM if it's easier.

Cheers.
## Post #5
- Username: aptyp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 15, 2014 1:09 am
- Post datetime: 2014-08-23T10:58:03+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Gh0stBlade I send files to you
## Post #6
- Username: aptyp
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-23T15:58:16+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

I have got the files to load in Noesis... Well most of them....
There are probably some other unsupported types but from the ones I tried they were all working.
You will need to place the python script in Noesis/plugins/python then you'll be able to open them and export to other formats.

Hope it helps!
[fmt_JustDance5_ckd.zip](https://xentaxbackup.github.io/file/7706_fmt_JustDance5_ckd.zip)
## Post #7
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-10T16:50:55+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

So i used the Python script in Noesis, but whenever i try to load a file most of the time it gets cut off is there a way to fix this?
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-16T23:31:13+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

> Reply from planedec50
>
> So i used the Python script in Noesis, but whenever i try to load a file most of the time it gets cut off is there a way to fix this?
Is it for the same game?
## Post #9
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-24T13:30:12+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

> Reply from Gh0stBlade
>
> planedec50 wrote:So i used the Python script in Noesis, but whenever i try to load a file most of the time it gets cut off is there a way to fix this?
Is it for the same game?

It's for the Just Dance games. Some pictures (the pictos) are 256x256 but exceed the max size. It looks like the picture below
[pic.png](https://xentaxbackup.github.io/file/9335_pic.png)
## Post #10
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-24T23:18:32+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

> Reply from planedec50
>
> Gh0stBlade wrote:planedec50 wrote:So i used the Python script in Noesis, but whenever i try to load a file most of the time it gets cut off is there a way to fix this?
Is it for the same game?

It's for the Just Dance games. Some pictures (the pictos) are 256x256 but exceed the max size. It looks like the picture below
Upload the sample if you can.
## Post #11
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-24T23:42:55+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

Heres the sample i used.
[http://www.mediafire.com/download/3e5gm ... 000e76.dat](http://www.mediafire.com/download/3e5gm7ciu10e30b/00000e76.dat)

Its the same as Just Dance 2014 .tga.ckd format but renamed with the .dat ending
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-26T19:49:55+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

> Reply from planedec50
>
> Heres the sample i used.
http://www.mediafire.com/download/3e5gm ... 000e76.dat

Its the same as Just Dance 2014 .tga.ckd format but renamed with the .dat ending
There is nothing wrong with the texture, it's correct.

Regards.
## Post #13
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-26T20:03:03+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

The texture and colors is correct but picture size isnt. It seems to be cropped
[Capture.PNG](https://xentaxbackup.github.io/file/9345_Capture.PNG)
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-26T20:27:38+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

What you see in-game is probably the same texture just flipped and placed together to make it look like one person. OR the other half is stored in another texture file. From my memory, there are several textures which look like this and usually they're ones which obviously can be mirrored. The fact this works fine on several other textures of the same type flag means it's most likely correct. Increasing the width/height is not possible as the pixel data for it simply isn't there.
## Post #15
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-06-26T20:42:06+00:00
- Post Title: Ubisoft *.tga.ckd *.png.ckd - any help

But how is that possible when i have searched all files. This game stores in a folder with the name and a number which refers to the main part. And how can it be flipped if there are supposed to be legs on this picture.
## Post #16
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-08-29T13:40:16+00:00
- Post Title: Re: Ubisoft *.tga.ckd *.png.ckd - any help

Hi! I'm just wondering again if you could add these types of dds formats to the python script, to noesis they have a bad array size.
[https://www.mediafire.com/folder/5t47f9 ... t_Textures](https://www.mediafire.com/folder/5t47f9bg7xefj/Ubisoft_Textures)
