## Post #1
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-02-26T22:29:42+00:00
- Post Title: BTEX in FF15 PC

I have extracted btex file from fntbin file, loaded into Noesis and I got exported attached graphic. So, I started wondering how to edit it. Checking Noesis plugin, it seems that this exact font graphic uses BC4 compression. Does anybody know how to edit this BTEX graphic with BC4 compression?
[fnt2out.png](https://xentaxbackup.github.io/file/13963_fnt2out.png)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-27T00:43:16+00:00
- Post Title: BTEX in FF15 PC

partially complete extractor there >>> [viewtopic.php?f=16&t=17659](http://forum.xentax.com/viewtopic.php?f=16&t=17659)

if you need more formats you can add more of those stylie

```
		texData = rapi.imageDecodeDXT(texData, width, height, noesis.FOURCC_BC4)
		texfmt = noesis.NOESISTEX_RGBA32

```


lines for the formats you need decoded. in the benchmark the format fmt byte is at 0xA6. there you can find the hex for the fmt.

edit: sure missed the reimport question. done.
## Post #3
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-02-27T20:25:54+00:00
- Post Title: BTEX in FF15 PC

Yeah, I have checked this python script. But the problem is how to edit it and insert back to the game in the same format - BC4. I don't see any import functions in Noesis.
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-28T14:19:02+00:00
- Post Title: BTEX in FF15 PC

has anybody tryna mod this any technical knowledge of binary and howto code things to get this done? you know reimporting doesn't stop at the btex files. you gotta get the earc back together too. who's gonna do that? i'm not complaining about dummy questions. /sarcasm

so... yeh. let me dl the benchmark again. gotta try bewbs or pants off? i hope the format didn't change in the demo version. i won't download it. i don't need it. it doesn't run on my potatoe. no point modding it.
## Post #5
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-02-28T18:42:19+00:00
- Post Title: BTEX in FF15 PC

I know how to put btex to fntbin and I know how to make zlib chunks to put the file again into earc - I see all needed pointers in earc. I did similar things with text already, so this part is not a problem.
I have found few programming codes and file format description, but I was wondering if there is a tool to edit BC4 format already, just to not waste time and discover America once again.

Format didn't change in demo version. Demo contains all needed things to translate the whole game, with all text for royal edition (~400 000 words in EN). Even benchmark has this text already, but EN/JA only.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-28T20:01:08+00:00
- Post Title: BTEX in FF15 PC

okay. raw stuff. did the extraction in bms. it outputs dx10 ddses. was easier to deal with bc3+ files. works with batch folder and reimport, but ofc you need a dx10 dds, the same format and sizes. you need the full texture data chunk with mipmaps. in that case they are needed - like most models will need them - you gotta generate them when saving the modified texture.

update: fixed the dxt5 fmt flag. lil bummer counting binary 
[ffvx_btex2dds_v2.rar](https://xentaxbackup.github.io/file/14287_ffvx_btex2dds_v2.rar)
## Post #7
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-01T23:24:21+00:00
- Post Title: BTEX in FF15 PC

Thanks a lot for this  After change French "ç" into Polish "ę", my font was compressed into bigger chunks than the original, so offzip and bms didn't work. But I have made new zlib chunks, inserted and moved all needed pointers manually today, and it works 

------
Edit: I have made a tool to extract and rebuild EARC archives, with no restriction in compressed filesize. I will publish it in few days.
[kup.PNG](https://xentaxbackup.github.io/file/13980_kup.PNG)
## Post #8
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-07T22:58:14+00:00
- Post Title: BTEX in FF15 PC

Archiver done: [viewtopic.php?f=10&t=17795](http://forum.xentax.com/viewtopic.php?f=10&t=17795)
## Post #9
- Username: RlySkiz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 08, 2018 7:52 am
- Post datetime: 2018-03-15T07:00:06+00:00
- Post Title: BTEX in FF15 PC

> Reply from episoder
>
> okay. raw stuff. did the extraction in bms. it outputs dx10 ddses. was easier to deal with bc3+ files. works with batch folder and reimport, but ofc you need a dx10 dds, the same format and sizes. you need the full texture data chunk with mipmaps. in that case they are needed - like most models will need them - you gotta generate them when saving the modified texture.

now... i'm still waiting for the test here. dunno if the de-archiver can reimport this correct now.

edit: probably luck the compressed chunk fit in there, but we got a skintone bra.

When i open the file you uploaded it immediately closes itself. Also does it need to be in a specific folder like the ff15/datas folder or can it be wherever? I can't quite follow in general.. I have a bunch of .btex files extracted from the game with Hammerhead and Noesis but have no way of converting these into actual materials/textures
## Post #10
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-03-15T08:26:21+00:00
- Post Title: BTEX in FF15 PC

> Reply from RlySkiz
>
> When i open the file you uploaded it immediately closes itself. Also does it need to be in a specific folder like the ff15/datas folder or can it be wherever? I can't quite follow in general.. I have a bunch of .btex files extracted from the game with Hammerhead and Noesis but have no way of converting these into actual materials/textures

hello newb. ofc it won't work without the tool. the script is for [quickbms](http://aluigi.altervista.org/quickbms.htm). note that the download comes with a reimport bat in the box, but you need the dotmode bat for this script's reimport to work.

(i sholda called it .hack bat. that's where this very requested feature started )
## Post #11
- Username: RlySkiz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 08, 2018 7:52 am
- Post datetime: 2018-03-15T09:16:14+00:00
- Post Title: BTEX in FF15 PC

> hello newb. ofc it won't work without the tool. the script is for quickbms. note that the download comes with a reimport bat in the box, but you need the dotmode bat for this script's reimport to work.
>
> 
>
> (i sholda called it .hack bat. that's where this very requested feature started )

I have the dotmode.bat but am i missing something here? I am, i know.. but.. Why export it and import it again... i want to be able to open the materials/textures the .btex files to be able to use them in blender for example since i'm already able to export the models into .fbx files via Neosis but the textures are missing. Thats what i try to do. Why should i reimport them again after exporting. I don't want to change anything on them to make mods for the game, i try to get the character models basically to be able to use them in blender. Same with .lsd or .sab sound files...

Or does the dotmode.bat change every .btex into useable .png or something?
## Post #12
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-03-15T09:49:08+00:00
- Post Title: BTEX in FF15 PC

if you wanna extract, just use the script in quickbms as it is. it is an extractor. it is dx10 and is based on reimport specs tho. meant to mod.

if you just wanna preview and extract, you could try to use the noesis plugin >> [here](http://forum.xentax.com/viewtopic.php?p=137657#p137657). it's only partially complete. it should open and export most textures correct tho.
## Post #13
- Username: RlySkiz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 08, 2018 7:52 am
- Post datetime: 2018-03-15T10:35:27+00:00
- Post Title: BTEX in FF15 PC

Posted in this topic already but somehow missed that single link.. thx.



got it working now.. lets see if i can find Shiva ( ͡° ͜ʖ ͡°)
## Post #14
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2018-03-15T22:13:50+00:00
- Post Title: BTEX in FF15 PC

Shiva = sm03 ( ͡° ͜ʖ ͡°)
## Post #15
- Username: RlySkiz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 08, 2018 7:52 am
- Post datetime: 2018-03-16T08:48:48+00:00
- Post Title: BTEX in FF15 PC

Yep already got her, even with textures and all... i also found her giant version that you can see in the snowy train area.

Basically got every game asset now, this is insane.. Every prop, food, street signs, chairs, building parts, weapons, npc, mobs, bosses, summons, whole mountain ranges... finally.

The only problem i have really is that every character has very weird hair since its prepared for nvidia hairworks i guess, everything looks like they have tagliatelle hair.
## Post #16
- Username: rathren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 18, 2018 4:29 am
- Post datetime: 2018-03-17T23:50:49+00:00
- Post Title: Re: BTEX in FF15 PC

> Reply from episoder
>
> okay. raw stuff. did the extraction in bms. it outputs dx10 ddses. was easier to deal with bc3+ files. works with batch folder and reimport, but ofc you need a dx10 dds, the same format and sizes. you need the full texture data chunk with mipmaps. in that case they are needed - like most models will need them - you gotta generate them when saving the modified texture.

now... i'm still waiting for the test here. dunno if the de-archiver can reimport this correct now.

edit: probably luck the compressed chunk fit in there, but we got a skintone bra.

Hey, nice work!

I am trying to do the same you did and came pretty far but I fail at using the right settings for saving my .dds because the textures look broken when put in game. I am using Photoshop with the Intel .dds plugin. But it does not have the bc3+ compression you are talking about as a option. Could you tell me what program you used to edited your .dds? Thanks!
## Post #17
- Username: Mark森
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 26, 2018 3:58 pm
- Post datetime: 2018-03-26T09:38:14+00:00
- Post Title: Re: BTEX in FF15 PC

> Reply from episoder
>
> okay. raw stuff. did the extraction in bms. it outputs dx10 ddses. was easier to deal with bc3+ files. works with batch folder and reimport, but ofc you need a dx10 dds, the same format and sizes. you need the full texture data chunk with mipmaps. in that case they are needed - like most models will need them - you gotta generate them when saving the modified texture.

now... i'm still waiting for the test here. dunno if the de-archiver can reimport this correct now.

edit: probably luck the compressed chunk fit in there, but we got a skintone bra.

Excuse me, how to convert from dds to btex
## Post #18
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-26T16:50:27+00:00
- Post Title: Re: BTEX in FF15 PC

Just copy pure pixels from one file to another, without headers etc.



dds.JPG (81.09 KiB) Viewed 444 times


If modified file has the same format as the original one, then pixels will fit without any problems.

...or use QuickBMS.
## Post #19
- Username: xMGMx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 19, 2018 12:43 am
- Post datetime: 2018-04-18T17:27:43+00:00
- Post Title: Re: BTEX in FF15 PC

> Reply from Robin
>
> I have extracted btex file from fntbin file
How you extract it? I want to replace russian font with something since it's awful.
## Post #20
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-04-19T20:12:46+00:00
- Post Title: Re: BTEX in FF15 PC

Open fntbin in hexeditor and search "SEDBbtex" - this is start of the btex file. Except one file, where are stored two BTEX files (I don't remember which one), BTEX content is till the end of fntbin file.

But you have to set correct kerning etc. This info is stored in fntbin, starting from 20205h (font_event.dx11.fntbin) and there are 9 bytes for every character:
1) offset from left of the whole texture, 2 bytes
2) offset from top, 2 bytes
3) texture start, from left, 1 byte (can be negative: 255 means -1) - kerning on the left side of character
4) texture start, from top, 1 byte (vertical placement of character)
5) texture width, 1 byte (how many pixels game have to read starting from 1))
6) texture height, 1 byte
7) whole block of character width (kerning on the right side of character), 1 byte. Example: If you have character with start 2 pixels after beginning of the block - 3) is set to "2", then 7) should be 2 (kerning from left) + texture width + 2 (kerning from right).

Try change something and check how it looks in game. It only looks difficult
## Post #21
- Username: xMGMx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 19, 2018 12:43 am
- Post datetime: 2018-04-19T23:51:40+00:00
- Post Title: Re: BTEX in FF15 PC

I hope i can avoid kerning edits. Will try to make same sized letters just align and smooth them out.
Look at that. I think the person who made it was dead drunk or was a bear.
[rus.JPG](https://xentaxbackup.github.io/file/14245_rus.JPG)
## Post #22
- Username: xMGMx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 19, 2018 12:43 am
- Post datetime: 2018-04-21T00:36:20+00:00
- Post Title: Re: BTEX in FF15 PC

So I made it, but with all the ajustments needed to make letters fit old placements it doesen't look any better.
[123.jpg](https://xentaxbackup.github.io/file/14250_123.jpg)
## Post #23
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-04-21T18:46:51+00:00
- Post Title: Re: BTEX in FF15 PC

What is wrong with these letters? I see problems with kerning in "т", "с" and "у", but don't know cyrillic alphabet too much to see another issues. Also, game is scaling these fonts, on my computer it would be looking even worst
## Post #24
- Username: xMGMx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Apr 19, 2018 12:43 am
- Post datetime: 2018-04-21T19:58:47+00:00
- Post Title: Re: BTEX in FF15 PC

Inconsistent kerning, some letters looks smaller than others like "д" in одному, asymmetric letters like "т" has longer stroke on the right etc.
I noticed that bytes in XY are reversed for some reason. For example 265 written as 09 01 instead 01 09. Took me an hour to determine where 10th byte coming from.   
Here I photoshoped calibri over original. I want it to be like this.
[http://www.framecompare.com/screenshotc ... n/J2C1NNNU](http://www.framecompare.com/screenshotcomparison/J2C1NNNU)
## Post #25
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-04-22T19:34:38+00:00
- Post Title: Re: BTEX in FF15 PC

Yeah, so kerning has to be modified. SE probably used Pro versions of some CJK fonts and just copied kerning to the game.

As for bytes, they are always reversed, as they are arranged in little-endian format.
