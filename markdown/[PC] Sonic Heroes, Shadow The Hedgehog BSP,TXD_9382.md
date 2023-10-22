## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-01T05:25:36+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Request: I'd request a script or import plugin to support Sonic Heroes' BSP format that would import into 3DS Max 2011 or later. 
Format: BSP Version 11, TXD. I believe the GC and PS2 version uses the same format type of BSP, DFF, and ONE.
Game(s) Used In: Sonic Heroes, Shadow the Hedgehog, Tony Hawk's Pro Skater 3 and others. [Link](http://en.wikipedia.org/wiki/BSP_%28file_format%29)
Demo/Where to buy: 
[[Buy@Amazon US](http://www.amazon.com/Sonic-Heroes-Pc/dp/B0006O4VNM)]
[[Buy@Amazon EUR](http://www.amazon.co.uk/Mastertronic-Ltd-Sonic-Heroes-PC/dp/B0016OVRW4)]
[[Demo/Trial](http://www.gamefront.com/files/3667073/Sonic-Heroes-Demo)].

Inside the ONE files you find either a BSP or DFF. However, they will be in PRS format. You'll need to decompress them and rename the extension (it will come out as a bin file). The TXD for the stages seems to differ from the ones used in the DFF files. The stage models files can be found under the filename stgxx.one or sxx.one. "xx" is the stage's number. The textures are in the TXD folder. When you decompress them, you'll see a filename like:

STG05_AFN_05.BSP.PRS
Decompress that with PRS Decompressor and you'll get:
STG05_AFN_05.BIN


Simply rename the BIN extension to whatever the extension was in before the ".PRS".
"STG05_AFN_05.BSP"

You can down the Utilities to unpack the files [here](http://www.hacking-cult.org/?utils). You're looking for the PRS Decompressor, ONE Unpacker, and Sonic Heroes TXD Unpacker.

[GameExtractor/](http://www.watto.org/extract/) is used for Shadow The Hegdehog's .ONE file. When you extract the file ONE file, you'll get a filename with a BSP format, but it just a PRS file with the BSP, DFF, or TXD extension. Simply rename the extension to PRS, decompress then rename it back to the original file extension.

If you need more information, just ask.
## Post #2
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-02T07:29:30+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

I tried a program I found for Tony's Hawk Pro Shaker 3 that convert BSP to OBJ. THPS3 uses BSP version 11 as well as Sonic Heroes and Shadow. However, they don't work. 

[http://devilclanthps3.weebly.com/tools.html](http://devilclanthps3.weebly.com/tools.html)
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-03T09:37:20+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Aren't they Renderware files?
## Post #4
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-03T14:13:34+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Yes, they are, but they're a different format than what Source Engine uses (BSP version 20-23) or other games that uses BSP. The DFF I have no problem with. Using RW Analyze, i can convert Sonic Heroes DFF (v3.5) to GTA3-SA's DFF format (v3.4) and then use Kam's scripts to import them into max. The only I really want is the stage geometry so I can try to port to Sonic Generations, same for some of Shadow The Hedgehog's level.
## Post #5
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-08-04T15:30:54+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

> Reply from ShinKun
>
> Yes, they are, but they're a different format than what Source Engine uses (BSP version 20-23) or other games that uses BSP. The DFF I have no problem with. Using RW Analyze, i can convert Sonic Heroes DFF (v3.5) to GTA3-SA's DFF format (v3.4) and then use Kam's scripts to import them into max. The only I really want is the stage geometry so I can try to port to Sonic Generations, same for some of Shadow The Hedgehog's level.

The only problem there is that you don't get any weight data, or any bone names.
## Post #6
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-04T16:08:25+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Well, you do get the bones (as dummies) and vertex data, but no animation data or something like that. However, I'm more interested with importing the BSP, which contains the stage geometry. If I wanted the character models then, I can get them from Model Resource. Also, I got the TXD to read, I just opening the wrong file.
## Post #7
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-08-05T13:27:14+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

I think there might be something different with the BSP implementation in Renderware compared to Source (or any other id Tech derivative for that matter). Dunno if the RW SDK came with an importer of some sort for BSP data, but since the toolkit's an internal tool I won't be delving too much with that for legal reasons.
## Post #8
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-05T17:59:55+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

I've talked with someone who has it, they said it has an exporter, but not importer, and it's for Max4-5. They have a worldviewer when you can open the BSP files and use  3DXRipper, but you won't get the textures or vertex color. At least, I don't think so. I heard this really easy format, but no one has bothered with. Might be due to the Sonic heroes hate, I dunno.
## Post #9
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-07T12:53:29+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

renderware bsp is easy format based on chunks. the problem is that any developer could add own chunks there, so default RW tools do not work with these files. same story with exporter. default bsps will doubtly work in games because of lack of specific chunks.

1st of all try to combine 'have normals' and 'have extrauv' checkboxes before you're sure my tool fails. if it does, i might try to modify it to work with sonic, i already tried dave mirra freestyle bmx and italian job which uses same bsp format and it involved some minor code fixes. i'd give it a shot, if you'd provide me an example of sonic bsp file.

edit: txd most probably can be read with one of gta tools.
## Post #10
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-07T13:22:58+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

> Reply from DCxDemo
>
> renderware bsp is easy format based on chunks. the problem is that any developer could add own chunks there, so default RW tools do not work with these files. same story with exporter. default bsps will doubtly work in games because of lack of specific chunks.

1st of all try to combine 'have normals' and 'have extrauv' checkboxes before you're sure my tool fails. if it does, i might try to modify it to work with sonic, i already tried dave mirra freestyle bmx and italian job which uses same bsp format and it involved some minor code fixes. i'd give it a shot, if you'd provide me an example of sonic bsp file.

edit: txd most probably can be read with one of gta tools.

Download the trial in the first link.  I PM'd. 

It worked, but not all files worked. It seems bigger file size will crash, or any other BSP files will crash it.
## Post #11
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-07T14:53:32+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

the problem was that the tool used fixed buffer size, so it didn't work when it exceeded. *thps3 bsp file contains lots of small objects, while sonic's bsp contain a single huge object* though there is problem with files too. FFFF0014 should be the last dword in each file. though there are few extra bytes, that makes my tool think that there are more chunks in the file. you'll have to remove those extra bytes manually. also textures are as .tga in mtl file. if you use different format, you'll have to change this as well.

*beta tool was here*

but the result is annoying if you ask me, other games have whole mesh in a single bsp.
## Post #12
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-07T15:07:39+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Have to remove them manually? So, would the extra bytes be after FFFF0014? I see "FF FF 00 14 All through out the file.
## Post #13
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-07T15:18:43+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

remove 'em only after the last one you can find. 2-4 bytes usually.
## Post #14
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-07T15:24:34+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Ah.



So, after this bit? I blank it out with 00s or just out right delete the section?
Both gave methods gave me that end of file error.=/
## Post #15
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-07T19:33:13+00:00
- Post Title: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

yes, delete selected.
## Post #16
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-07T20:35:50+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Tried yours and still get the read error. The smaller sized BSP worked fine with anything unchecked though The bigger filesize crashed with this error. 

If I check any other options, I still get the read file error.

Edit: it working again. Weird. The one I downloaded form your site works now.

However, it doesn't import right.



It not suppose to have missing faces...

I appreciate you trying to help. I really do.
## Post #17
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-08T09:59:23+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

ok, i see now, the problem is in material split. i ignored it and i have full mesh, but it's untextured.
it must be using different face storing method, but... it worked for both trilist and tristrip. i've also added extra bytes check, so you don't need to bother deleting 'em.

edit: i think i fixed it.
remember that this should be used with default checkboxes states to work.

edit2: 1 more fix - now you can choose extension that will be written in mtl file.


 bsp2objv021sonic.rar
(178.25 KiB) Downloaded 71 times



and it still works with thps3 files. i think i should write a general bsp tool.
## Post #18
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-08T10:39:52+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Have you looked at the Shadow The Hedgehog ones? It's the same BSP version, but they don't have the FFF014.
Also, thanks for the tool. By the way, do you mind if I upload this and post this one Sonic Retro?
## Post #19
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-08T14:45:12+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

> Reply from ShinKun
>
> Have you looked at the Shadow The Hedgehog ones? It's the same BSP version, but they don't have the FFF014.
another game? tell me if it doesn't work. file version doesn't matter until something changed there in file structure.

> Reply from ShinKun
>
> Also, thanks for the tool. By the way, do you mind if I upload this and post this one Sonic Retro?
this tool is free to use. post some textured screens if you can.
## Post #20
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-08T15:22:00+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Yea, I sent to the Shadow The Hedgehog ones, dunno if you looked at them. Your tool will load them them just fine, but when imported into max, they are blank.
## Post #21
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-08T16:09:05+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

i never played a single sonic game and those sites are kinda mystery to me. there's no way i could find it if you posted it somewhere.

if smth doesn't work, show me the files, i'll check what i can do.
## Post #22
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-08T17:06:21+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

It's in the same pack i PM'd you. I'll Pm you again though.
## Post #23
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-08T20:36:13+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

these are collision models, they dont have textures applied, uv coords are always zero. looks like these are used in physics calculation, not rendering. the model itself should be somewhere around with similiar filename, but without COLI.
## Post #24
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-08T20:49:21+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Those are the only BSP files in the .one archive. I think I found out where the geometry is found, but no actual way to rip the file.
## Post #25
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2012-08-09T10:16:32+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

then you'll need someone who will write unpacker first. and you didn't show me screens yet, i'd like to see textured environments. maybe a link where you published it?
## Post #26
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2012-08-09T10:21:58+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Sorry forgot.
## Post #27
- Username: SimulatorSam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 17, 2021 6:29 pm
- Post datetime: 2021-03-17T14:12:56+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

> Reply from DCxDemo ↑Tue Aug 07, 2012 8:53 pm at Tue Aug 07, 2012 8:53 pm
>
> 1st of all try to combine 'have normals' and 'have extrauv' checkboxes before you're sure my tool fails. if it does, i might try to modify it to work with sonic, i already tried dave mirra freestyle bmx and italian job which uses same bsp format and it involved some minor code fixes. i'd give it a shot, if you'd provide me an example of sonic bsp file.Sorry to bump an old thread. I'm trying to use the bsp2objv021sonic tool linked earlier in The Italian Job. Would you happen to still have a version of the tool that works for The Italain Job BSPs?

```
levela: empty mesh					- london
levelb: some verts					- turin
levelc: "I/0 error 131." crashes, some verts		- car testing track
leveld: takes awhile, only some verts			- getaway turin
levele: "I/0 error 131." crashes, 0 byte obj		- turin at night
levelf: "I/0 error 131." crashes, 0 byte obj		- alps
levelg: some verts					- red white and blue motorway
levelh: some verts					- birds-eye camera london
levelj: "Read beyond end of file." some verts		- car testing track again
levelk: some verts					- snow map

Options used:

Split by materials
BSP have normals data
BSP have extraUV data
.mtl texture type .bmp
```
Here's what the resulting .obj's usually look like. Just a very small portion of the map made of just vertices. The .mtl files look filled out though.
## Post #28
- Username: DCxDemo
- Rank: advanced
- Number of posts: 43
- Joined date: Sat May 14, 2011 5:02 pm
- Post datetime: 2021-03-20T03:19:54+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

> Reply from SimulatorSam ↑Wed Mar 17, 2021 10:12 pm at Wed Mar 17, 2021 10:12 pm
>
> 
Sorry to bump an old thread. I'm trying to use the bsp2objv021sonic tool linked earlier in The Italian Job. Would you happen to still have a version of the tool that works for The Italain Job BSPs?
I barely remember delphi to fix the old tool, but here's a newer one. check readme.


[bsp2obj_italian.zip](https://xentaxbackup.github.io/file/19759_bsp2obj_italian.zip)
## Post #29
- Username: SimulatorSam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 17, 2021 6:29 pm
- Post datetime: 2021-03-20T06:55:37+00:00
- Post Title: Re: [PC] Sonic Heroes, Shadow The Hedgehog BSP,TXD

Brilliant, thank you very much. :)
