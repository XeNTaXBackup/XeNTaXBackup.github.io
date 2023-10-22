## Post #1
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-29T06:47:18+00:00
- Post Title: Phantasy Star Complete Collection [PS2] (*BMP)

Sega Ages 2500 Vol. 32 - Phantasy Star Complete Collection (J) 

I just found out that this collection features a gallery of concept art & illustrations for PS I-IV. The good news is that all of pictures are in .BMP format, the bad news is that most of them are not viewable in any standard picture software. 
So I'm guessing the files have some kind of modified header or something. 

I tried NovaSoftwareExtractor to scan and extract the actual picture (sometimes this simple method works in other cases), but it found nothing. Also these encrypted BMPs don't load into any image editing software (Photoshop, GIMP, etc), it says the file is incorrect or damaged.

Maybe someone can give me an advice on what to do to view these pics?

Here's a sample of BMP that doesn't work: [http://www.mediafire.com/?1e354jg8si4d1ts](http://www.mediafire.com/?1e354jg8si4d1ts)

And another one that works: [http://www.mediafire.com/?s447szzv3cfivru](http://www.mediafire.com/?s447szzv3cfivru)
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2012-12-30T20:33:21+00:00
- Post Title: Phantasy Star Complete Collection [PS2] (*BMP)

Had a look at the header of the file, searched for it on google, landed here ([http://forums.sonicretro.org/index.php? ... 7591&st=15](http://forums.sonicretro.org/index.php?s=5b98f0eede26568c958db8884ccc3d9a&showtopic=27591&st=15)), compiled the code and tested it with your file. Profit!
This was simple. You should at least do a googlesearch before you ask for help next time.
I attached the compiled converter written by Treeki ([http://andlabs.lostsig.com/lzs2decomp.c](http://andlabs.lostsig.com/lzs2decomp.c)).

[http://img14.imageshack.us/img14/1368/00ps4front.jpg](http://img14.imageshack.us/img14/1368/00ps4front.jpg)
[lzs2decomp by Treeki.zip](https://xentaxbackup.github.io/file/6107_lzs2decomp by Treeki.zip)
## Post #3
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-12-31T14:41:16+00:00
- Post Title: Phantasy Star Complete Collection [PS2] (*BMP)

Amazing! You made my day sir. I really appreciate this. 

And sorry if I'm being noobish about it. I didn't even know that searching header's info on Google was a way to start. Looking at stuff in hex editor tells me nothing, it's kinda over my head. 
I might be proficient with other tools for 3D rendering or photoshop but this hexing/code compiling stuff is not for everyone. 
There's just no time to learn everything. That's why sometimes you gotta ask for help of others. Please understand. 

Thanks a lot again.
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-01-01T11:50:07+00:00
- Post Title: Phantasy Star Complete Collection [PS2] (*BMP)

> Reply from MiLØ
>
> Amazing! You made my day sir. I really appreciate this. 

And sorry if I'm being noobish about it. I didn't even know that searching header's info on Google was a way to start. Looking at stuff in hex editor tells me nothing, it's kinda over my head. 
I might be proficient with other tools for 3D rendering or photoshop but this hexing/code compiling stuff is not for everyone. 
There's just no time to learn everything. That's why sometimes you gotta ask for help of others. Please understand. 

Thanks a lot again.
Ah, I see. I'm glad I could help then.
