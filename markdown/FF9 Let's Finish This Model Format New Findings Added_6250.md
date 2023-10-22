## Post #1
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-20T00:41:07+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-20T13:33:56+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

I posted this in the Noesis thread back in January. We must have similar taste in games  

I'll quote what I posted incase I have something you didn't.

> Reply from ultimaespio
>
> I dunno if your interested in FF9, but I just found some stuff about the model formats.

http://zidane_games.webhost.ru/formats_FFIX.doc

File extractor:
http://zidane_games.webhost.ru/FF9_TOOLS.rar

As well as a battle scene viewer and source:
http://zidane_games.webhost.ru/FF9_TOOLS.rar

http://zidane_games.webhost.ru/FFIX_BattleScene_viewer_final_+_SRC.rar

FF9 needs some love.
## Post #3
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-03-20T14:26:08+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Okay so I got in contact with Chev and got some new information.

To quote what he said, "You can do yourself a huge favor and start with directory 8 (weapons, which mean no need ot understand animation at first), then 7 or 10 (both battle models) and not the trickier field models (directory 4) like I did."

So for now what I know is

Folder/What They Are:

0 - [Status/Menu/Battle/... -Text and random stuff.](http://wiki.qhimm.com/FF9/Dirs/00)
1 - [Misc Images (Logos, Fonts, World 'mini' Map images, etc).](http://wiki.qhimm.com/FF9/Dirs/01)
2 - Dialog Text
3 - Map models (Mini-zidane, airships, save point moogle, tent...) and, IIRC, the map texture.
4 - Field models
5 - Monster Data (Part I, stats, names, etc).
6 - Location Data (Dungeon, Cities, etc).
7 - Monster Data (Part II, 3d models)
8 - Weapon Data (including models)
9 - Samplebanks and Sequencer Data (ie music).
10 - party members Data (including models)
11 - Sound effects
12 - World Map Data.
13 - Special effects (magic, summons...), the file system's different form the other directories so I don't know how to access it.



If you downloaded my renamed files from this thread you can easily copy the following into your bat file and convert the archives of folder 10. Just copy and paste your .bat, db_extract and DB_Extract.exe to folder 10.

Or just use this to make your own bat file easily: [http://textmechanic.com/Generate-List-of-Numbers.html](http://textmechanic.com/Generate-List-of-Numbers.html)

```
DB_Extract.exe 1_10.db
DB_Extract.exe 2_10.db
DB_Extract.exe 3_10.db
DB_Extract.exe 4_10.db
DB_Extract.exe 5_10.db
DB_Extract.exe 6_10.db
DB_Extract.exe 7_10.db
DB_Extract.exe 8_10.db
DB_Extract.exe 9_10.db
DB_Extract.exe 10_10.db
DB_Extract.exe 11_10.db
DB_Extract.exe 12_10.db
DB_Extract.exe 13_10.db
DB_Extract.exe 14_10.db
DB_Extract.exe 15_10.db
DB_Extract.exe 16_10.db
DB_Extract.exe 17_10.db
DB_Extract.exe 18_10.db
DB_Extract.exe 19_10.db
DB_Extract.exe 20_10.db
DB_Extract.exe 21_10.db
DB_Extract.exe 22_10.db
DB_Extract.exe 23_10.db
DB_Extract.exe 24_10.db
DB_Extract.exe 25_10.db
DB_Extract.exe 26_10.db
DB_Extract.exe 27_10.db
DB_Extract.exe 28_10.db
DB_Extract.exe 29_10.db
DB_Extract.exe 30_10.db
DB_Extract.exe 31_10.db
DB_Extract.exe 32_10.db
DB_Extract.exe 33_10.db
DB_Extract.exe 34_10.db
DB_Extract.exe 35_10.db
DB_Extract.exe 36_10.db
DB_Extract.exe 37_10.db
DB_Extract.exe 38_10.db
DB_Extract.exe 39_10.db
DB_Extract.exe 40_10.db
DB_Extract.exe 41_10.db
```


Hopefully this update is of some use. Thanks ultimaespio.

Edit: Updated folder contents based on Chev's info.
## Post #4
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-03-20T16:38:52+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

So, uh, hello guys.

The directory contents are, more or less (based on a post by Zande on the Qhimm forum, and slightly updated with my own sightings):

0 - [Status/Menu/Battle/... -Text and random stuff.](http://wiki.qhimm.com/FF9/Dirs/00)
1 - [Misc Images (Logos, Fonts, World 'mini' Map images, etc).](http://wiki.qhimm.com/FF9/Dirs/01)
2 - Dialog Text
3 - Map models (Mini-zidane, airships, save point moogle, tent...) and, IIRC, the map texture.
4 - Field models
5 - Monster Data (Part I, stats, names, etc).
6 - Location Data (Dungeon, Cities, etc).
7 - Monster Data (Part II, 3d models)
8 - Weapon Data (including models)
9 - Samplebanks and Sequencer Data (ie music).
10 - party members Data (including models)
11 - Sound effects
12 - World Map Data.
13 - Special effects (magic, summons...), the file system's different form the other directories so I don't know how to access it.
14 - ???

DB files are containers, ie directories themselves, used to group data. Just, well, read how they work in the qhimm wiki, since you'll be dealing with them all the time. For the battle and weapon models this means you can find the matching texture somewhere in the same root DB, though a DB can contain DBs, so it can be in another branch. But I never made a tool to visualize the whole directory tree so I never figured out how it works for field and map models, only that it didn't work quite the same way.
## Post #5
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-03-20T17:05:09+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

I've used Timrip on the files in folder 10. 

0 - Vivi
1 - Cinna
2 - Blank
3 - Marcus
4 - Garnet
5 - Zidane
6 - Garnet
7 - Freya
8 - Beatrix
9 - Quina
10 - Garnet (this one's probably her short haired one)
11 - Garnet
12 - Eiko
13 - Zidane
14 - Steiner
15 - Garnet
16 - Garnet
17 - Quina
18 - Freya
19 - Eiko
20 - Beatrix
21 - Eiko
22 - Amarant
23 - Amarant
24 - Trance Zidane
25 - Trance Zidane
26 - Trance Garnet
27 - Trance Garnet
28 - Trance Vivi
29 - Trance Vivi
30 - Trance Garnet
31 - Trance Garnet
32 - Trance Steiner
33 - Trance Steiner
34 - Pluto Knight
35 - Trance Eiko
36 - Trance Eiko
37 - Trance Amarant
38 - Steiner
39 - Zidane
40 - Vivi
41 - Steiner

My guess is that this folder has both field and battle models for playable characters only.
## Post #6
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-03-20T17:06:46+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Yep, that's precisely it. Also, most characters are found twice because field and Battle models are stored separately, even thought they're usually identical (there are exceptions, like Amarant).
## Post #7
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-06-08T06:41:02+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Hi there, my name is Lubdar, I'm new to the board; I didn't see a introductions thread so I just jumped right in. 

I've been perusing the forum trying to absorb some information before I ask incorrectly.  I've managed to extract the DBs for directories 7,8, and 10.  I got as far as you've shown thus far where I find separate folders with a .model file, .animation file, and a couple TIM files.
   I was looking for some clues on the Noesis thread to see how I move from these files to viewing them in Noesis.  I saw MrAdults says that the FF9 plugin is only for the #7 and #10 directories.  If anyone finds the time and wants to help me figure out how to move from where I am to being able to view the models in Noesis , I'd appreciate it.
## Post #8
- Username: Zerox
- Rank: mega-veteran
- Number of posts: 186
- Joined date: Mon Aug 09, 2010 10:50 am
- Post datetime: 2011-06-08T18:59:01+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

> Reply from LUBDAR
>
> Hi there, my name is Lubdar, I'm new to the board; I didn't see a introductions thread so I just jumped right in. 

I've been perusing the forum trying to absorb some information before I ask incorrectly.  I've managed to extract the DBs for directories 7,8, and 10.  I got as far as you've shown thus far where I find separate folders with a .model file, .animation file, and a couple TIM files.
   I was looking for some clues on the Noesis thread to see how I move from these files to viewing them in Noesis.  I saw MrAdults says that the FF9 plugin is only for the #7 and #10 directories.  If anyone finds the time and wants to help me figure out how to move from where I am to being able to view the models in Noesis , I'd appreciate it.
Extract FF9.IMG with Noesis and you'll have the files laid out for you.
## Post #9
- Username: elric03200
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2011 10:11 pm
- Post datetime: 2011-08-16T14:17:48+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Hello EveryBody... 

I's been a few weeks that I try to mod FFIX. I started to try to extract some files from my Official FF IX CD's when I seen you post. 5sorry for my poor english I'm French)

My great question is : 

Once I extracted my .db and mods my .tim for example : HOW to repack files ???

Let me explain, if i extract my 0.db, i'll have à file which contains a lot of elements. when I did what I wanted, I don't know who restore files on a only .db. I search all over the web, even tried to make my own tools with the Db_extractor.exe I don't find any solution...

Thanks to all and again sorry for poor english
## Post #10
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-08-18T15:53:48+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

We simply don't know enough about the format to repack files.
## Post #11
- Username: elric03200
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2011 10:11 pm
- Post datetime: 2011-08-21T03:53:36+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

If I understand good, try to extract files from FF9 is completely useless...
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-08-21T09:01:32+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Not really, not all reasons for extracting files is to edit the game, but rather to examine the files within and such.

Edit: Then again, extracting is the first step in recompilation, so who knows?
## Post #13
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-08-22T20:04:07+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

elric03200> It's not useless at all, we can get better looks at things than in-game, or even things that don't appear in-game at all, or things about the developers. For example, [there's a hidden message written on one of the FF9 monster models](http://forums.selectbutton.net/viewtopic.php?p=869077#869077), and that's something that never could have been learned without being able to extract the models.

It's like analysing a book to understand what makes it a good book, opening a machine to see its circuits, seeing what rules Michaelangelo followed to make his great paintings. It's interesting in itself.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-22T20:21:42+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Wow everyone's so ambitious.
I would just extract it so I can throw them into some animation program
## Post #15
- Username: elric03200
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2011 10:11 pm
- Post datetime: 2011-08-27T17:00:46+00:00
- Post Title: FF9 Let's Finish This Model Format New Findings Added

Hey    ! It's been a lil time =)

I have an idea : Can we try to ask to the tool's creator if there is a way to repack this ??? 
He can make tools to extract, he can maybe even make a repacker no??? 

Even if we have to give him paypal donates right ?
## Post #16
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-27T18:01:49+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from elric03200
>
> Hey    ! It's been a lil time =)

I have an idea : Can we try to ask to the tool's creator if there is a way to repack this ??? 
He can make tools to extract, he can maybe even make a repacker no??? 

Even if we have to give him paypal donates right ?

I guess there is no harm in asking Mr. Adults if he could do that, but I believe he is pretty busy.  I'm sure he'd appreciate donations, but that in no way obligates him to do things for you...
## Post #17
- Username: elric03200
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 16, 2011 10:11 pm
- Post datetime: 2011-09-04T06:52:37+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Hello everybody ?? How goes the searches in these times?
## Post #18
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-13T01:30:36+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Um... Well I hate to tell you that you may have been wasting your time, but Noesis can export FF9 models, textures, animations, and possibly the disc's archives(I've not tried the archive/disc image export since I had the files already) already.

The only thing I recall not being able to export is the field map textures (which have a palette in a separate file I believe) and the world map objects... which are so few I don't think they'd be of much use anyway... but nonetheless.

But in any case, noesis has FF9 support for a majority of things, and the plugin is open source; get it here:
[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #19
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-13T18:18:29+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

So it can extract precisely what we know how to extract   
It is very handy, mind you, but as long as a topic like this exist there's a hope of figuring out the other stuff, like summons. Also, when you say models, does that include the NPCs? Or just battle models?

World map objects do include airships too, there's some nice ones. But just like NPCs the location of their textures is not known (apart from that map models are just like any other).
## Post #20
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-13T22:20:31+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

It extracts precisely what we know how to extract, because it is the culmination of the documentation on the qhimm wiki, which I forwarded to MrAdults and he turned into a plugin for Noesis   

It will extract NPC and etc models from the field map data, which includes sky cabs a few airships, tons of NPCs (I have Mikoto ) and their animation data.

It's important to note that animations are stored as separate files, and multiple Models can use the same animations, however, some animations and models are not compatible (Due to having different numbers of bones)

What it doesn't export readily is the textures for Field model NPCs and etc objects, as they are a different, slightly modified TIM format, and are often packed together in groups, so Mikoto is packed together with about 7 other NPCs and objects, and each field map contains its own set of NPCs and animations. Some maps may have the same models, but there are more or less animations available for them. (Honestly I think they'd have saved space by putting the models in a master archive and calling them from that at the cost of one or two more cycles during map load, rather than storing each map multiple times for each set of NPCs it can have... but whatever)

However, it IS possible to obtain NPC textures through things like PSX-VRAM, however you do need to have a savestate in the proper map to get the textures that way.
You can also use Tile Molester or GGD (If I remember correctly that is) to search through the map file and export the textures and palettes that way.

The textures are 4bpp format, and the palettes are many for each texture as there is a palette for each NPC, but multiple NPCs' textures are stored as a single image, usually 512 x 256 in size...or possibly 1024x512. It's an array of 4 NPC textures by 2 NPC textures in hight.

The UVs for NPC models are set for those dimensions, so you need all 4x2 textures in the image for them to map to the model properly.

Bones fully supported, animations apply properly when exported.

I don't remember whether or not overworld objects are available or not, I haven't tried.

Field models are stored in several hundred files in the 04 folder. The files are unnamed so you'll have to look for the models by eye.

Battle model and player field model animations are interchangeable, as the battle and field models are identical save for the texture mapping, also it seems a few characters' animations can be swapped.

Field map background images are, as I recall, stored in the same DB file as NPC textures for that map, but are 8bpp... as I recall.

If you want to choose a single disc to dump, use disc 4 as it contains nearly all of the previous discs' models.

I hope this answers your question.
## Post #21
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-09-14T02:14:26+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

A few things to note:

1) I recall quite a few things were wrong in the specs I got from...I don't think it was from that wiki (which was down when I tried to look at it), but the docs were probably sourced from there. But in any case, the plugin code with Noesis is probably a better source of info than any docs out there, since it actually works.

2) I didn't see an automatic way to detect the TIM textures that have fixed tiled/paletted data that doesn't correspond with actual TIM specs in them, but those are easy to decode when you know you're looking at them. Those textures are mainly used for world stuff and backdrops. The only reason Noesis doesn't handle them is because I didn't feel like trying to hardcode in paths to figure out what was being looked at in terms of textures. If you wanted to hardcode the plugin to handle them, though, it would be pretty trivial.

3) I recall anim data for the summons was pretty similar to battle/field models (at a glance from the hex), but I never really looked into it. I only spent a day or 2 on that plugin, and figured the source being out there would lead to other people adding support for the other formats if anyone actually cared. You should have enough to work from right there to get all of the models/anims figured out. It's not like FF7/FF8 where the formats and anim storage actually tended to differ in significant ways between field/battle/summon models.

Oh, and 4), since you mentioned location of airship textures and crap aren't known. They are known, I recall coming across texture reference chunks usually paired in the same "DB" file as the models themselves. I recall they contained references in an order that corresponded to texture ID's in the mesh(es) as well. I had them figured out enough to load textures from them, as I recall, but all my notes on them are back on my machine in Arizona. As is all of my FF9 content. So that's about the extent of my usefulness there.
## Post #22
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-09-14T09:58:04+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

If you just want textures to go with the white meshes, just go to the textures resource. Someone managed to rip some there.
## Post #23
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-15T21:46:19+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I already knew where to find the NPCs, just not their textures (going through PSX-vram isn't really what I'm going for, I'd like to create something that can get it all), and not how to match animations to the right NPCs (my viwer really just tries everything and displays the ones that decode correctly, so it will still display animations that aren't meant for a given model).

Regarding 4), well, my bad. Whichever half-assed method I was using to crawl the DBs to find textures missed them for th map models. I guess I'll have another look.

Regarding 3), my main problem would be that I don't get how the special effects directory (the one that contains the summons) is organized, it seemed different from the others, so I never could hook the model viewer on anything since it relied on the directory structure.

I guess I'll have to brush the dust off and at least get the airships.
## Post #24
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-19T21:38:52+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I might be stupid but I have no clue how to look at/export FF9 models.

First I downloaded a FF9.bin version and that gave me nothing. Then I downloaded your zip file with .db's. I also downloaded a FF9.img version

I used db_Extractor on your files and get .model and .animation. Nothing in newest Noesis opens up and the .img file I cannot do anything with inside 

Some pointers would be nice
## Post #25
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-19T22:21:31+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Are you looking in the FF9.bin file that's stored on the disc, or are you looking at a disc image called FF9.img? 

If what you downloaded is a disc image, mount it with daemon tools or the like, and look inside the image for a file called ff9.img, there should be one as I recall.
## Post #26
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-09-20T13:15:36+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

The contents of this post was deleted because of possible forum rules violation.
## Post #27
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T16:11:48+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Thanks for this long and very useful post. I think I did have the ff9.img in noeses but it just said it could not preview, nothing about trying to export etc.

I am at work now but will look asap. I hope I did just something minor wrong but I did have ff9.img + latest noesis. I wonder why I did not get same prompt like you
## Post #28
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-20T19:25:30+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Regarding the weapons, they don't map correctly because in-game the weapon textures are blitted into a blank spot in the character's texture. For all practical purposes that means you should offset the v coordinate by 14 texels if you're reading from dir08 and everything will look fine, which I guess isn't implemented in the noesis plugin yet.

From my old viewer:

[](http://imageshack.us/photo/my-images/204/capturelzj.png/)

I got the dir03 textures too now, except they're kinda weird, they're declared as 16bpp in the TIM file but they look like 4bpp.

EDIT: oh, I get it, it's like the NPCs in room files, 4bpp and they declare them as 16bpp so it won't load palette data since the palette is already contained elsewhere.

[](http://imageshack.us/photo/my-images/90/tent.png/) [](http://imageshack.us/photo/my-images/638/pagese.png/)

So now I need to figure out how to get the CLUT and page informations (the tent's nifty because it's aligned on the right page but it's the only model that's that well-behaved).
## Post #29
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-09-20T21:08:20+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from pixellegolas
>
> Thanks for this long and very useful post. I think I did have the ff9.img in noeses but it just said it could not preview, nothing about trying to export etc.

I am at work now but will look asap. I hope I did just something minor wrong but I did have ff9.img + latest noesis. I wonder why I did not get same prompt like you
I think you need to re-name the FF9.img when it's ripped from the ISO, it doesn't have the .img in the title, so noesis can't pick it up. Just make sure the file is called " FF9.img "

> Reply from Chev
>
> Regarding the weapons, they don't map correctly because in-game the weapon textures are blitted into a blank spot in the character's texture. For all practical purposes that means you should offset the v coordinate by 14 texels if you're reading from dir08 and everything will look fine, which I guess isn't implemented in the noesis plugin yet.

From my old viewer:



I got the dir03 textures too now, except they're kinda weird, they're declared as 16bpp in the TIM file but they look like 4bpp.

For Chev, How or where did you offset the v coordinate, is that in the Data Viewer? Makes sense, but not sure where to adjust the v-axis. Is there a setting in an older version of Noesis? Oh and the Dir3 textures may be 8bpp I think, cause you can view them in PsxVram with that setting.
                                            - Thanks.
## Post #30
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-20T21:17:46+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from Kujo99
>
> For Chev, How or where did you offset the v coordinate, is that in the Data Viewer? Makes sense, but not sure where to adjust the v-axis. Is there a setting in an older version of Noesis?
Well, I'm using a custom FF9-only model viewer I made long ago, not noesis, so I have different options (and a crappier UI). Maybe look in the texture settings

Glad you got your colors for NPCs. For the map models 4bpp really is the only way to decode the indices though.
## Post #31
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-09-20T21:37:49+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Haha, sometimes custom UIs are the best way's to get results... I'm only limited with what I got. Good job with those textures in Dir 3 and 8.

Were you able to View the NPC files with the textures as well? The only ones that work in Noesis for me are animations of the characters from Dir3 with the .ff9mdl's and.tim's from Dir10.
## Post #32
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T22:42:50+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Managed to get it working thanks to you Kujo!

[](http://www.imagebanana.com/view/e4pkvho9/ff9render.jpg)

I put the animated char inside Unity too with some effects and here is how it looks like
## Post #33
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-20T23:12:55+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Very nice Pixellegolas. I did something similar with Freya a while back.... Come to think of it I should do some more work on that project.
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-20T23:37:46+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

It was way better when I turned off texture interpolation and keeping in pixly instead. Looks really bad when engine smudges the textures
## Post #35
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-21T00:13:53+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Of course it does. I wrote a completely new shader just for that reason.

In any case, is there anything else in FF9 we still don't have a way to get at? Seems like all the edges are covered... Textures, battle scenes, battle models and enemies, field maps and models...

Are we missing anything?
## Post #36
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-09-21T00:37:14+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

@Kujo99: thanks for sharing TileMap_0.6 and the BattleScene Viewer!!!
@ Mr Adults: As always, a continuous "Thank you" for Noesis
@ Satoh and everyone else: this has been a huge help exploring the cds.

I was 
> Reply from Satoh
>
> Of course it does. I wrote a completely new shader just for that reason.

In any case, is there anything else in FF9 we still don't have a way to get at? Seems like all the edges are covered... Textures, battle scenes, battle models and enemies, field maps and models...

Are we missing anything?
Has anyone explored Dir13?  I was curious about the summons data but haven't seen any models for them.
## Post #37
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-09-21T01:44:34+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I'm a bit interested in Dir9 to see if there are any MIDI files that can be read.

And I think it would be cool to Find out how to read the files in Dir11, you know, to get the sound effects.
## Post #38
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-21T01:52:08+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

There's a number of tools for PSX sound file playback and conversion at a place called zophar's domain. There's even a winamp plugin for PSX midi music (called PSF, PS Sound Font as I recall...)

You may be able to find some files that are playable as is... 

I forgot all about summons actually; I'd quite like to get my hands on Fenrir.
## Post #39
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-21T05:31:22+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from Satoh
>
> Of course it does. I wrote a completely new shader just for that reason.

In any case, is there anything else in FF9 we still don't have a way to get at? Seems like all the edges are covered... Textures, battle scenes, battle models and enemies, field maps and models...

Are we missing anything?
For example how to get the texture anims (like all the eye animations, which are based on blitting parts of the textures). And yeah, the summon dir.
## Post #40
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-09-21T09:33:15+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I was gonna say music and sounds but you covered it
## Post #41
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-22T04:42:59+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I don't mean to sound dense or rude, but could you tell me why you would need to know how the textures are blitted for blinking?

Would it be for modding the game itself? I can't think of how a scripted function like that would be useful outside of the parent engine...

I can already tell you the where to/from of the blit if that's what you need... all facial textures have a secondary eye-open and eye-shut somewhere in the image. I'd assume it's blitted into the original face portion of the face for a split second, and then the backup eye-open is blitted back into place.

I don't think the coords for the transfer is stored in the textures or models... Though I suppose being able to access/read/change scripts -would- be a valuable modding asset...

But I'm curious as to what made you mention the blitting specifically...


**BLIT for those unaware, is BLock Image Transfer (or possible variations of this acronym), or in other words, copying a rectangular portion of an image, and pasting it into and existing image.
## Post #42
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-22T18:35:33+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from Satoh
>
> I don't mean to sound dense or rude, but could you tell me why you would need to know how the textures are blitted for blinking?
For visualization, duh. Sure, you can guess by looking at the texture, but an automated program can't, plus you sure can't tell me when the blinks happen unless you go over everything frame by frame in an emulator and hope you'll be able to find every mode of every model close enough to the viewpoint. It's like asking why I included animations or textures in a viewer when I could all reanimate and retexture by hand myself (and thus miss the unused content like extra anims or messages on textures). Viewers are for seeing content that's there, saying you could guess is completely missing the point making forums like this one exist in the first place. 

Plus as mentioned before in the thread there can be pleasure in understanding how things work.
## Post #43
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-09-22T20:18:19+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I love that fact! I've noticed so many things already that I could have never seen without checking out the model data... 

Like... 

The escalator outside the guestroom, in Lindblum. (Well, not motel data, lol)

The Inside of the Air Cab in Lindblum!!!

Amazing renders of all the characters!!!

I just can't wait until we get to the point where all the models and textures with the animations can be read.

I was thinking it would be cool to use the 3d battle backgrounds and model data to make a sort of 3d version of FF9, well, of course not the whole game, but maybe a movie like trailer about the game. It will be like FFIX like you've never seen it before!!!
## Post #44
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-09-22T21:34:50+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from Kujo99
>
> I love that fact! I've noticed so many things already that I could have never seen without checking out the model data... 

Like... 

The escalator outside the guestroom, in Lindblum. (Well, not motel data, lol)

The Inside of the Air Cab in Lindblum!!!

Amazing renders of all the characters!!!

I just can't wait until we get to the point where all the models and textures with the animations can be read.

I couldn't agree with you more!!!
## Post #45
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-09-25T20:08:58+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

The contents of this post was deleted because of possible forum rules violation.
## Post #46
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-10-13T20:30:31+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

YAY NEWS! . . . 

Turns out if I use PSXVRAM and gather a texture file, if I save it as a .bmp and drag it onto the Noesis model, in Noesis, I get this... a correctly mapped character, for the most part... The model data reads the first textue, but for it to read the others, like the hands, i'll need to create a proper sized texture with both the mattes in them.

Also, I believe it only works if there is one texture "block" so to speak, I used photoshop to crop the one texture i wanted, then saved as .bmp...
## Post #47
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-10-14T03:02:47+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

That is great news!! what do you mean by texture block, I'll have to look into PSXVRAM....
## Post #48
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-10-14T08:38:42+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

In PSXVRAM you open a save state from the scene you are in, saved while playing the game on epsxe, (I already have all the backgrounds from Dir4 all 4 disks, took forever...   So it makes it easy to figure out which DB folder in Dir4 has which scene, model, ) anyway, the save state in PSXVRAM shows you the textures in the 8bit setting and you can select the color pallet for those textures by right clicking the pallet, then selecting the CLUT for that texture. once you have that texture you can save it, crop it, (i used .bmp) and drag it onto the model in noesis.

After some more experimenting i just might get the textures to work, but it'll be the long way around . . . which I'm cool with.

Oh, yeah... the texture block i was referring to was the area in which a specific characters texture is, opposed to others in the same file, like this one that Chev pulled up... [http://img851.imageshack.us/img851/6609/unled3rk.png](http://img851.imageshack.us/img851/6609/unled3rk.png) 

It's strange, cause I've been reading Chev's research, and if you open a .tim in noesis, you will see a colorful, scrambled image like you would see in PSXVRAM but in 16bit as if that's the .tim's properties, one .tim file contains all other NCP textures... so you would think the .mdl data would only read a file that large with all the textures in them. However, it read one small texture, and mapped it to the model correctly, even though it's a separate file. 

Now the trick is how to get noesis to read two or three files... 

And I think I have an Idea . . . I'll get back to yall'.  


Oh, yeah, and I have already began sorting out all of the animation data to their proper .mdl files.   * ORGANIZING *   

This is how it goes... 



Here's a fun fact... PSXVRAM can also view battle scene backgrounds, and give us their matte textures so we can use them to make some    "crafty stage paper models"
## Post #49
- Username: Kujo99
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 19, 2011 5:05 pm
- Post datetime: 2011-10-14T10:39:39+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Well, for the most part is just short of perfect, but not all models map properly...
## Post #50
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-12-15T01:54:17+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

If posting after 2 months of inactivity is necroposting, let me know

Anyway, how can I view the models of FF9 with animations and textures? What program do I use, and what are the steps of doing it. Sorry if I didn't read the whole thing, I guess I am lazy and out of time today.

Can someone send me the files used to extract the "db" files? I'm having trouble over here creating a way to do so...
## Post #51
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-12-15T05:24:15+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Noesis is the tool you want: [http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

Use it to extract and decode models and textures.
## Post #52
- Username: dragicorn
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Sep 18, 2011 3:21 am
- Post datetime: 2011-12-15T18:37:22+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Another Update? Cool!
## Post #53
- Username: itoikenza
- Rank: advanced
- Number of posts: 52
- Joined date: Sat Jan 07, 2012 9:24 am
- Post datetime: 2012-04-17T18:06:38+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

> Reply from Kujo99
>
> Well, for the most part is just short of perfect, but not all models map properly...
is that girl with the blue hair viewable in the latest noesis? can you tell me her file name?
## Post #54
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2012-04-19T09:40:36+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Has anyone managed to view the world map at all?
I've managed it with another view by Zidan on the quimm forums, but this was just a viewer for the .raw files, I'm unable to even see these 2 files with Noesis for some reason.
## Post #55
- Username: Avalanche
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 12, 2012 5:57 am
- Post datetime: 2012-07-11T22:00:02+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Hi Guys,

Have you seen any possibility in FF9 to extract the dialog and then make a translation?
## Post #56
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2012-07-14T17:16:38+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

sure, all the dialogue is in directory 02, which only contains text files, though I guess everything fight-related might be in the monster directory?. Anyway, character table can be found [there](http://wiki.qhimm.com/FF9/CharTables#Character_Table_for_EU_.26_US_version), but no one's made an editor AFAIK
## Post #57
- Username: Avalanche
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 12, 2012 5:57 am
- Post datetime: 2012-07-15T10:29:37+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

I extracted the FF9_IMG file with zidane's FF9_img_extractor.exe and with the Noesis, too. But i can't open any file from the 02 directory. Can you help me, how can i reach the dialog texts? How can i open them?
## Post #58
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2014-08-06T12:44:04+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Please anyone can tell me where i can download Noesis software on the net, i try to find but i dont get it?

Please any help.
## Post #59
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-08-06T14:47:02+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Either refer to the Noesis thread in general game tools, or go to his website.
## Post #60
- Username: Splasher9
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Nov 04, 2013 10:57 pm
- Post datetime: 2014-08-10T19:33:19+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

Hi everyone.  

Can someone tell in which directory the game stores Bahamut model ? Just could not find it in Field models folder.
## Post #61
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-08-10T23:51:53+00:00
- Post Title: Re: FF9 Let's Finish This Model Format New Findings Added

At present I don't think anybody knows the whereabouts of the summon models. Someone was able to rip the texture for Bahamut, but I'm not sure of there method.
