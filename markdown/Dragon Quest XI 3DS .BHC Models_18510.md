## Post #1
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-07-28T21:56:25+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

Hello, does anyone can do some some wizardry around those nor Ohana, Spica or EFE could open them gl.
[hero.7z](https://xentaxbackup.github.io/file/14673_hero.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-29T19:54:57+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

Don't know about wizardry  , just using hex2obj, uvs not found so far:



cha01000a_l.jpg (147.31 KiB) Viewed 189 times



H2O file for Lod2:

0x2BF10 3288
Vb1
24 99
0x210FC 606
020300
0x0 255

btw: the extension is .bch, not .bhc
## Post #3
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-07-29T23:09:39+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

Wow... Wizardry indeed   Thanks dude ! Unfortunately I´ve never been able to use Hex2Obj efficiencly or at all to be honest but H2O file worked briliantly, I tried to "reverse engineer" what you did and guessed that the head faces location from the other file (cha01000a_h.bch) would be starting at 476e0 ? But unfortunatelly that´s where my brain started to melt with the tutorial. Please let me know if you uncover UVs and if you have a way to easily guess vertices position and length for other files and thanks again for what´s already been achieved I love those simplistic models.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-30T09:25:45+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

> Reply from Resiliaxia
>
> [...]and guessed that the head faces location from the other file (cha01000a_h.bch) would be starting at 476e0 ?that's correct.   (whatever you're meaning with "head faces"?)

> But unfortunatelly that´s where my brain started to melt with the tutorial. Please let me know if you uncover UVs and if you have a way to easily guess vertices positionThe tutorial is for simple models only. You need to gain experience checking out some dozens of them before you are suspected to be successful with the harder ones.

That's the point most readers don't seem to accept.  

Anyways here (in the _l sample I don't find counts or sizes, 606 -> 5E020000 or 606x28 ->  48420000) you need to search for patterns, as there is FFFFFFFF for example (maybe 4B2A2A2A is another candidate, but not sure).

last FFFFFFFF at 0x1C168, adding  0xD4C (wizardry  ) -> 0x1CEB4, start of vertices for _l sample.
(well I just subtracted 0x1C168 from "the known" 0x1CEB4 to get that 0xD4C, so it's more a jugglery)

For the _h sample it's 0x2D268 + 0xD4C  -> 0x2DFB4, start of vertices.

For the faces, there are many of them, it's required to find out the submesh borders manually so far, imho.



cha01000a_h-bch.jpg (97.04 KiB) Viewed 169 times
## Post #5
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-07-30T12:47:19+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

Woops is there a way to change Topic title I guess not it´s committed unless I contact a moderator, thanks for your efforts but I guess this is out of my reach and there are too many files for one model and I believe _h stands fo high and _l for low curious however for a 3ds game.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-30T15:33:41+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

> Reply from Resiliaxia
>
> , thanks for your efforts but I guess this is out of my reach and there are too many files for one modelwell, it all depends on you.  
These models are not that spectacular, imho, so it's a little bit unlikely that someone will make a script for them.

I was always thinking about the best way to give beginners a startup with coding or scripting, but seems there's one in a thousands, who takes up the chance, if any.
Releasing C- source for the Make_obj project did not really help.

Meanwhile I create Noesis python templates from time to time but in the end it's useless as long as beginners can't perform simple searches for binary patterns.

Uhmm, wait, seems I didn't present such a search for Noesis.  Or I did, and it's lost somewhere in the forum.
([viewtopic.php?f=16&t=14391&p=119019&hil ... ng#p119019](http://forum.xentax.com/viewtopic.php?f=16&t=14391&p=119019&hilit=+string#p119019))
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-07-31T11:04:19+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

off: for me h2o always something like "every time from scratch" because when I want to use it I always start from tutorial for it to then proceed with the format I want. its ui is confussing shit out off me. I always thought that it can be simplier but then 'Model researcher' came up. I don't claim that "MR" is a super-tool but it is a lot more organized in terms of interface, and you don't have to learn tool — you just need to understand the format you want. So if you want bring the begginers through your tool to their desired models you may consider to re-touch h2o's ui
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-31T11:46:01+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

I've posted my answer here:
[viewtopic.php?f=29&t=10894&p=142667#p142667](http://forum.xentax.com/viewtopic.php?f=29&t=10894&p=142667#p142667)
so that we don't get too much off topic here.
## Post #9
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-08-01T10:37:52+00:00
- Post Title: Dragon Quest XI 3DS .BHC Models

On my part it´s not about Hex2Obj UI since it does pretty much the same if not better than Model Researcher but more about the learning curve that is hard as stated by shakotay2 that is problematic I am not quite a lazy ass (I always try first and search a lot) but I have my limit and I am really not a programmer at all, this territory is always confusing me a lot (I even fail at building GitHub files to be more specific...) So I do rely on people who are able & willing to take time to make tools since I believe they might learn from it and since it´s the purpose of this website I am hopefull when I ask for help but I understand that sometimes it is not an easy task.
