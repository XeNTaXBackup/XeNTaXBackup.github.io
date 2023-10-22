## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-02-05T12:53:19+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Topic was created, because game archives has .DAT archive format, but use different method for archiving\compression files. All these formats unsupported to all current tools, because they works for PC versions, not PS1-2, Xbox. (Note: dont work with DEMO(not all), STAGE, VOX and other small archives - CODEC, BRF)

Metal Gear Solid [PS1]
Music files are stored in STAGE.DIR, which has compression or something. Possibly uses Huffman-like or pseudo-code or compression flag on music files(VAG\VB\VH).
DEMO.DAT and VOX.DAT possibly has music audio, but not sure about it.

Metal Gear Solid 2: Sons of Liberty [PS2]
MIDI-style|PS1 VAG-style music audio. Stores in SDX containers, which in STAGE.DAT.
MGS HD Collection possible doesn't have differences, because use SDX format too.

Metal Gear Solid 2: Substance [Xbox, PS2]
One or two big .DAT archives cuted to separate 400MB parts. Music audio format is the same as PS2 original or use separate .DAT for music as PC version.
Dont check PS2 version yet.

MGS3 not included, because music archived in separate BGM.DAT and two tools can unpack files from it - Konami DAT Unpacker and demux_dat by hcs.

Files for research and testing can be accessed through PM.
## Post #2
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2014-02-11T14:59:03+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Ps1 stage.dir is known. I'll look into it when I'm at my computer.
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2014-02-16T14:08:35+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

There is [this](http://forum.xentax.com/viewtopic.php?f=10&t=5485&start=0) information. There is also [this](http://snailrush.online.fr/) tool for PS1 sound listening. Open a DAT file and scan it. Seems like DEMO and STAGE have all the stuff in them.

(EDIT)
I just whipped this up. [MGSDIRTool](https://github.com/neko68k/MGSDIRTool)

Looking at the "DIR"s in the STAGE.DIR file, it seems like it uses hardcoded PSX memory addresses. Obviously, this is problematic...

[](http://imgur.com/d7Txdiy)
## Post #4
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-02-18T14:12:51+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Unpacked data from STAGE.DIR looks like BSP, BSP-like structure(for example, Quake, HL, Unreal), because many sounds, which scans PSound 2.0, is the same, specially in sXX files.

I found music samples in:
Demo (JP)
init
titlep

Retail (JP)
d16e
init
s07a
s07b
s16d
title

Also, I have two unlicensed versions of the MGS1 for PS1 with translated text and voices - I think its possible use for understands used archive/compression methods.
P.S.: MGSDIRTool works with all STAGE.DIR for all versions(russians too).
## Post #5
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2014-03-14T21:26:17+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

I'm going to say no, no bsp. There is no bsp-like data in the models themselves. They are straight quads and indices as can be seen [here](https://github.com/neko68k/mgsview/blob/master/mgsview/KMD.cpp)
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-03-17T01:02:12+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

> Reply from ameneko
>
> I'm going to say no, no bsp. There is no bsp-like data in the models themselves. They are straight quads and indices as can be seen here
I think he wasnt talking about the model data but how all data is stored in a directory/ tree. bsp might not have been the best word for him to use, but it relates to the "tree" concept. How each level stores the specific sounds they need. and how the sounds aren't stored in one big file like most games do?
## Post #7
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2014-03-25T23:27:58+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Makes sense. I can elaborate a little on that. Each 'Sxxy' directory contains all the assets for a given 'stage' in the game. Generally this is an entire section of map, one floor of a building and all the rooms that connect to it. All the textures for this map, all the models in it, the collision models and radar/collision map, animations and sound effects are stored for each stage. 

There is a generic assets container also, I dont remember the name off hand. It contains common objects, textures, etc. Snakes model and skins, explosion and gun models and things like that.

The VRAM is laid out so that the frame buffer is in the top left corner and is double buffered. To the right of that are the generic textures mentioned in the paragraph above. Below that are all the stage related textures pre-sorted, roughly, by width then height ignoring the bpp. This vram texture x,y and texture pallete x,y data is stored either in TIMs or similar on the PSX or PCX extra data in the unused section of the header on the PC version. On the far bottom right seems to be a scratch area for codec pop up message and other stuff.

My recollection is that codec text and speech is stored in its own directory.

In the stage directories the files are something like this for the PC version. HZM for map collision and radar map. KMD for all models, heierachically sorted and linked. Not sure about animations right now.. I have more info, some of this is implemented or somewhat documented in the source repo in above posts.
## Post #8
- Username: DXBigBoss
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 28, 2011 1:46 pm
- Post datetime: 2015-03-20T22:00:59+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Wanted to also confirm MGSDirTool works with Metal Gear Solid: VR Missions as well (obviously)
But I don't understand what to do with the files, or rather, how to use them. Play them, edit them. Anyone have any idea?
## Post #9
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2015-08-12T01:11:02+00:00
- Post Title: MGS series [.DAT][.DIR](PS1, PS2, Xbox)

Could someone pass me the compiled MGSDIRTool?
