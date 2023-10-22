## Post #1
- Username: Ruggio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 18, 2011 6:54 am
- Post datetime: 2011-01-25T19:02:36+00:00
- Post Title: Extracting .tv files from Korean MMORPG Tenvi

Hi! I recently became interested in a Korean game called Tenvi. It's a 2D sidescrolling platform game. What brought me to this game was the graphics, and I would like to be able to extract them. The game is only open in Korea and China, and even there they're not that popular so it's difficult to find a place with game images. Through my research, I've found a website that makes an extractor, but my knowledge in the Chinese language is nonexistent. The website ix EXRPG and the extractor is called Extractor Suite. It can be found here [http://bbs.exrpg.com/thread-1420-1-1.html](http://bbs.exrpg.com/thread-1420-1-1.html). They have extractors for other games like LaTale, DFO, and Maplestory, and they all require a login. I registered to the site and the only one that doesn't work is the Tenvi one. Disappointment.

So from there I tried learning about extraction methods and found this place. I looked at things people have made for Maplestory, because I thought since they're similar games made by the same people maybe they're set up similarly. But I don't think that's the case, but they probably aren't difficultly encrypted either because the game isn't that popular. I don't know much about extraction, but I'm not sure where to even start and I was wondering if anyone could help me out.

I tried some code from 2006 that worked for Maplestory that would send me in the right direction [viewtopic.php?p=14016#p14016](http://forum.xentax.com/viewtopic.php?p=14016#p14016) and got this:

> offset: 8702
>
> compressed: 2615 uncompressed: 3144
>
> offset: 11390
>
> compressed: 439 uncompressed: 4128
>
> offset: 54032
>
> compressed: 28558 uncompressed: 129083
>
> offset: 94421
>
> compressed: 8 uncompressed: 2
>
> offset: 167113
>
> compressed: 889 uncompressed: 32832
>
> offset: 225717
>
> compressed: 11 uncompressed: 5
>
> offset: 4244283
>
> compressed: 12 uncompressed: 6
>
> offset: 4442636
etc. Not sure what they do.
[http://vana.pastebin.com/f3146d7fe](http://vana.pastebin.com/f3146d7fe) I found this too.

I found this (translated from Chinese):
data10.tv - data14.tv: Map material library
data15.tv: contains references to other .tv files as subdirectories, how the character sprites are displayed and layered
data16.tv: Composite Material Library, NPC, monsters, UI, small maps and so on
data17.tv: xml library
data20.tv - data24.tv: other materials library, a mess, some characters items and equipment, etc.
data25.tv: Model Library (for 3D things i assume)
data26.tv: Sounds
data27.tv: Background Music

These are the game files that hold this data, much like .WZ files of Maplestory. If anyone could help me I would be glad to upload any of them that will be important in extraction. What I'm looking for mainly is the NPC's, monsters, and maybe character stuff.

Thanks.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-26T05:00:11+00:00
- Post Title: Extracting .tv files from Korean MMORPG Tenvi

best way to start is to have the files you're talking about! upload data10.tv (for the graphics) and data17.tv perhaps because of the xml (and for the record - if the uncompressed size is smaller than the compressed size, its generally the wrong script)
## Post #3
- Username: Ruggio
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 18, 2011 6:54 am
- Post datetime: 2011-01-26T17:51:11+00:00
- Post Title: Extracting .tv files from Korean MMORPG Tenvi

haha true that is very important.   

the files go from data10 to data27, but i only uploaded the files to mediafire that might be of use to this folder: [http://www.mediafire.com/?po7k8dpgq0i7w](http://www.mediafire.com/?po7k8dpgq0i7w)

Map material library
[http://www.mediafire.com/?cdlj8aqp23n48a1](http://www.mediafire.com/?cdlj8aqp23n48a1) data10.tv (42.01 MB)
[http://www.mediafire.com/?a835zt9amc1vax5](http://www.mediafire.com/?a835zt9amc1vax5) data11.tv (34.16 MB)
[http://www.mediafire.com/?e9x9nk5n94i43o3](http://www.mediafire.com/?e9x9nk5n94i43o3) data12.tv (25.81 MB)
[http://www.mediafire.com/?7ljdlwx5g9j8ux2](http://www.mediafire.com/?7ljdlwx5g9j8ux2) data13.tv (20.25 MB)
[http://www.mediafire.com/?7ljdlwx5g9j8ux2](http://www.mediafire.com/?7ljdlwx5g9j8ux2) data14.tv (18.56 MB)

Composite Material Library
[http://www.mediafire.com/?7ljdlwx5g9j8ux2](http://www.mediafire.com/?7ljdlwx5g9j8ux2) data16.tv (93.57 MB)

XML Library
[http://www.mediafire.com/?7ljdlwx5g9j8ux2](http://www.mediafire.com/?7ljdlwx5g9j8ux2) data17.tv (6.45 MB)

thanks~
## Post #4
- Username: nasty
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 11, 2009 5:14 pm
- Post datetime: 2011-03-21T11:16:10+00:00
- Post Title: Extracting .tv files from Korean MMORPG Tenvi

Ruggio,
have you success to extract Tenvi files?
Please let me know ..
thanks ..
