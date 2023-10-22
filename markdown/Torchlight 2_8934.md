## Post #1
- Username: JohnMullins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 09, 2007 10:28 pm
- Post datetime: 2012-05-12T16:31:37+00:00
- Post Title: Torchlight 2

I am in the beta and it uses some pak format which cannot be easily extracted and repacked like in the original.
If anybody is interested in looking into that, please drop me a PM.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-12T17:27:18+00:00
- Post Title: Torchlight 2

```
DATA.PAK.MAN - FileTable for Archive
```
## Post #3
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-19T13:01:42+00:00
- Post Title: Torchlight 2

Also in the beta, also interested in this.
## Post #4
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2012-05-20T02:45:18+00:00
- Post Title: Torchlight 2

imho TL2 file format corresponds with simple tutorial from quake. Pak is data file, man has pointers to offsets and legths. its 5 AM, im sleepy, but maybe somebody will make script for bms
## Post #5
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-20T10:38:50+00:00
- Post Title: Torchlight 2

PAK is unfortunately a --VERY-- common extension and this format has nothing to do with Quake's.
## Post #6
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-20T10:45:01+00:00
- Post Title: Torchlight 2

This PAK has easy structure

```

then repeat until end of file
4B Unpacked size
4B Packed size
[Packed size]B ZLib data

```


MAN file is little complicated. I'm working on it, but have not much time to finish reversin. But I'll try.
## Post #7
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2012-05-20T12:11:25+00:00
- Post Title: Torchlight 2

> Reply from Delacroix
>
> PAK is unfortunately a --VERY-- common extension and this format has nothing to do with Quake's.
true, maybe that wasnt Quake, but im 100% sure i saw this method somewhere
## Post #8
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-21T17:36:11+00:00
- Post Title: Torchlight 2

So here it is. 
First version for actual beta game. Repack is not available now. It will be added later 



Torchlight 2 PAK Files Extractor
[http://raptor.cestiny.cz/download/torch ... actor.html](http://raptor.cestiny.cz/download/torchlight-2-pak-files-extractor.html)

Enjoy it
## Post #9
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-21T18:30:08+00:00
- Post Title: Torchlight 2

Thanks. I owe you one.

When you add repack function, THEN there will be time to seriously rumble
## Post #10
- Username: sosoyaya
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 22, 2012 2:29 pm
- Post datetime: 2012-05-22T06:34:14+00:00
- Post Title: Torchlight 2

> Reply from XRaptor
>
> So here it is. 
First version for actual beta game. Repack is not available now. It will be added later 



Torchlight 2 PAK Files Extractor
http://raptor.cestiny.cz/download/torch ... actor.html

Enjoy it
it's awesome ....thank you so much ,wait repack will be available
## Post #11
- Username: JohnMullins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 09, 2007 10:28 pm
- Post datetime: 2012-05-22T16:12:29+00:00
- Post Title: Torchlight 2

Is it possible to extract paks that dont have a .man file like the locale pak?
## Post #12
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-22T16:37:33+00:00
- Post Title: Torchlight 2

It is different file with the same extension. So no.
## Post #13
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2012-05-24T17:02:40+00:00
- Post Title: Torchlight 2

cool that you have come a bit on the way of modding torchlight 2 ;D repack feature is gonna be sweeet, thanks for the hard work dude
## Post #14
- Username: JohnMullins
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 09, 2007 10:28 pm
- Post datetime: 2012-05-24T18:05:44+00:00
- Post Title: Torchlight 2

> Reply from XRaptor
>
> It is different file with the same extension. So no.
And this is impossible to extract therefore? Cant believe...
## Post #15
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-24T19:02:28+00:00
- Post Title: Torchlight 2

Not with this program at least. But let us not distract XRaptor from focusing on Data.pak/Data.pak.man first. More things will surely come later if only we ask nicely
## Post #16
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-28T12:36:53+00:00
- Post Title: Re: Torchlight 2

Ok, repack implemented. Time to test it 

Torchlight 2 PAK Files Extractor
[http://raptor.cestiny.cz/download/torch ... actor.html](http://raptor.cestiny.cz/download/torchlight-2-pak-files-extractor.html)

Enjoy
## Post #17
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-05-28T19:56:05+00:00
- Post Title: Re: Torchlight 2

I love you for this, man.
## Post #18
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-29T00:02:21+00:00
- Post Title: Re: Torchlight 2

Did somebody manage to find the texts in the beta?
## Post #19
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-29T07:50:22+00:00
- Post Title: Re: Torchlight 2

> Reply from lostprophet
>
> Did somebody manage to find the texts in the beta?
Everywhere in .layout and .dat files  There is no single file with localized texts. But it can change in final product.
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-06-02T21:55:02+00:00
- Post Title: Re: Torchlight 2

Mmm, interesting, since the first Torchlight was based on Ogre3D, this is also using the same file extensions

Material, Mesh, skeleton, dds, png

where material describes which texture is applied to what mesh, and the skeleton contains the animations, I'm going to try the OgreMeshViewer which can be found here : [http://www.ogremax.com/downloads](http://www.ogremax.com/downloads)

I haven't tried it yet, but I will asap

T.
## Post #21
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-06-02T22:01:17+00:00
- Post Title: Re: Torchlight 2

Yep it works,

extract everything, download the OgreMaxViewer ( use the windowed viewer )
open the .material file and change the .png extension to .dds

and here it is:



Many Thanks for the extractor !!!

T.
## Post #22
- Username: maynem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 15, 2010 3:47 pm
- Post datetime: 2012-09-20T20:16:30+00:00
- Post Title: Re: Torchlight 2

I do not speak english, sorry.
## Post #23
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-09-21T01:43:08+00:00
- Post Title: Re: Torchlight 2

I got an error too when I used the extractor for full released version. Game seems support for modding, it loads extracted files automatiacally.
## Post #24
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-09-21T05:03:24+00:00
- Post Title: Re: Torchlight 2

Yeah, I found this yesterday too. I'll check it. It is only file throwing error.
## Post #25
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-09-21T17:36:10+00:00
- Post Title: Re: Torchlight 2

Ok, fixed tool is ready. Seems that it is only file with zero size. There were no one like this in beta. It should work now.

Torchlight 2 PAK Files Extractor
[http://raptor.cestiny.cz/download/torch ... actor.html](http://raptor.cestiny.cz/download/torchlight-2-pak-files-extractor.html)
## Post #26
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-09-22T08:24:41+00:00
- Post Title: Re: Torchlight 2

thanks XRaptor, i gonna make some translation with this game
## Post #27
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-23T21:42:46+00:00
- Post Title: Re: Torchlight 2

Thank you Raptor.
## Post #28
- Username: maynem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 15, 2010 3:47 pm
- Post datetime: 2012-09-24T12:06:56+00:00
- Post Title: Re: Torchlight 2

Unpacker works, thanks. There is a problem - unpacked game does not work. I deleted DATA.PAK.MAN and DATA.PAK.
## Post #29
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2012-09-25T03:56:39+00:00
- Post Title: Re: Torchlight 2

I have that problem too, you have to open it with notepad and save as unicode encoding.
## Post #30
- Username: maynem
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 15, 2010 3:47 pm
- Post datetime: 2012-09-25T09:17:37+00:00
- Post Title: Re: Torchlight 2

> I have that problem too, you have to open it with notepad and save as unicode encoding.

I know. But need to process a lot of files*.dat .It takes a lot of time. Problem.
In general, it does not matter. I had the usual interest.
## Post #31
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2013-11-13T19:18:31+00:00
- Post Title: Re: Torchlight 2

Updated version 1.3. No more "Out of Memory" (I hope) 

Torchlight 2 PAK Files Extractor
[http://raptor.cestiny.cz/download/torch ... actor.html](http://raptor.cestiny.cz/download/torchlight-2-pak-files-extractor.html)
## Post #32
- Username: Martell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 30, 2013 2:37 am
- Post datetime: 2014-08-25T23:09:41+00:00
- Post Title: Re: Torchlight 2

Hi guys,

I'm new to the forums,
I hope it's okay to post this to this thread as it involves torchlight 2.

I am quite new to python plugin development for blender but i had had a little success in adding animation support to the 
torchlight-to-blender project.

I was wondering if someone with a lot more expertise in this area would help me finish off this feature.

Here is a link to my latest work on this.
[https://github.com/martell/torchlight-t ... d3ceacea5a](https://github.com/martell/torchlight-to-blender/commit/6647d949a60d16ee538a6a8fd94635d3ceacea5a)

I'd love to discuss more with one of the importer experts here on xentax
