## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-14T04:12:46+00:00
- Post Title: MikuMikuDance Models

here's a maxscript I've been working on to handle the PMD format in max. I have to figure out how to import animations still. anyway GUI'd the script, just drag and drop the *.ms script into max and a float box will popup.. and obviously select import to get a PMD into max.

> SCRIPT RELEASE - FEB 13 2011
>
> 
>
> 
>
> DOWNLOAD:  http://www.mediafire.com/?pbm83mqyq5a495a
>
> http://www.youtube.com/watch?v=seusFW_I53I
>
> 
>
> Script Supports Import and Export of the PMD format.
>
> Some features are missing, although basic import and export should be possible
>
> there are some limitation, that I will address later which can cause problems with export.
>
> However I will continue to work on the script to better script functionality.
>
> 
>
> Feel free to drop feed back or questions.

PS> if you don't know what mikumikudance (MMD) is, its a free animation creator made by some japanese guy. awesome enough, these guys created some pretty sweet models! and now they can be accessed through max.

enjoy!

-mariokart64n
## Post #2
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-02-14T08:15:17+00:00
- Post Title: MikuMikuDance Models

nice work man  keep it up, i'm sorry i can't do anything though, my programming skills is close to zero.  anyway, great work
## Post #3
- Username: SoftIce
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Jan 23, 2011 12:31 pm
- Post datetime: 2011-02-17T20:52:31+00:00
- Post Title: MikuMikuDance Models

Sweet. Thanks Mario! I've wondered about the MMD model skeletons, and if they all have the same base bones or something, since I often see different models doing the same dance.
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2011-02-22T05:10:27+00:00
- Post Title: MikuMikuDance Models

[out]
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-02-22T05:20:57+00:00
- Post Title: MikuMikuDance Models

guess your right, since theres an xbox360 port.. but I can't find the PC source anywhere  :\

It certainly would have helped
## Post #6
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-02-22T09:44:33+00:00
- Post Title: MikuMikuDance Models

thanks
## Post #7
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2011-03-20T14:38:10+00:00
- Post Title: MikuMikuDance Models

Nice script. Works great.
## Post #8
- Username: Goshujin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 18, 2011 10:54 pm
- Post datetime: 2011-03-21T05:11:54+00:00
- Post Title: MikuMikuDance Models

Hiya,

great script, are you trying to tackle the animation files too?
It would be great if we could import MMD animation scripts into max or something.

kind regards
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-21T20:06:07+00:00
- Post Title: MikuMikuDance Models

i tried doing that, and you can find partial support in the last script. which I released on the miku forums
[http://mmdc.proboards.com/index.cgi?boa ... 286&page=2](http://mmdc.proboards.com/index.cgi?board=edits&action=display&thread=286&page=2)


though I'm having alot of problems with getting it to work.. if i follow the positions and rotations from the animation file, my bones get torn apart O_o.. 
I just don't have any experience with importing animations, I've been tying to find other maxscripters to help.. but so far no luck
## Post #10
- Username: Goshujin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Mar 18, 2011 10:54 pm
- Post datetime: 2011-03-22T01:43:37+00:00
- Post Title: MikuMikuDance Models

I believe there is something that allows VMD importing to Blender

[https://sites.google.com/a/render.jp/vmdimporter/](https://sites.google.com/a/render.jp/vmdimporter/)

Here is a link to the version

[https://sites.google.com/a/render.jp/vm ... ects=0&d=1](https://sites.google.com/a/render.jp/vmdimporter/Home/hontai-to-tsukaikata/Blender249VMD.zip?attredirects=0&d=1)

So from there maybe it's possible to output to a format that Max likes?

I am having trouble locating the MMD starter pack characters and the windows 100% characters so I may have to buy the magazine and starter pack off of amazon.
I live in Japan so I wont get stung on shipping
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-22T02:33:44+00:00
- Post Title: MikuMikuDance Models

figuring out how to read the data from the file isnt the problem.. its interpreting it in max.. I just don't know how to properly script it.

also I got a few of those windows models from another guy. I can send you what I have if you want. won't be the official starter pack, but atleast its a start.

if you have msn, add me
## Post #12
- Username: FallenAngelRiku
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Nov 30, 2011 1:28 pm
- Post datetime: 2011-11-30T06:16:58+00:00
- Post Title: MikuMikuDance Models

thanks for writing this script!
MMD works with VMD Files, wich are basically animation files, they hold positions of certain bones, as example:
"LeftArm" x=6 y=3 z=8 first frame
Rigging models on MMD allows you to name them the same, and save VMD motion datas to load them on different models, the only requirement is that the second model must have a bone with the same name as the first, this makes things easier.
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-12-01T01:58:59+00:00
- Post Title: MikuMikuDance Models

great work really man, I like this game, is really good, and models how say too are cool, the japanese make good staff ^^
