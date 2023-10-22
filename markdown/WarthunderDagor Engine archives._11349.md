## Post #1
- Username: WatchDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 17, 2014 8:48 pm
- Post datetime: 2014-03-23T10:42:13+00:00
- Post Title: Warthunder/Dagor Engine archives.

So I have been spending the last few days trying to decipher the archive files in the free to play game "WarThunder".
Developed by Gaijin entertainment, it uses their in house "Dagor" engine.
According to [its wikipedia page](http://ru.wikipedia.org/wiki/Dagor_Engine)(Russian) there are at least 19 games using the engine.
However, I am only interested in WarThunder.

This topic has already been somewhat discussed for a different game(Blades of Time) here: [viewtopic.php?f=10&t=8794&hilit=vromfs](http://forum.xentax.com/viewtopic.php?f=10&t=8794&hilit=vromfs)

The WarThunder game files contain a few different types of archive files.
I have had varying levels of success trying to decipher them.

The main archive types within the game are:

vromfs.bin
dxp.bin
grp
blk
vromfs.bin
Header Bytes: 56 52 46 73 00 00 50 43(VRFs  PC)
Description:
VROMFS archives are fairly basic.
They consist of 6 parts. All lengths and addresses are Little Endian.
A 16 byte header with the file type and the location of the footer and optionally the length of the decompressed data.
A 32 byte subheader with the location of the file name locations, the file locations and the number of files.
A section describing the location of the file names(Length=8 x filecount).
A section containing the file names. File names are null terminated.
A section describing the locations and lengths of the files(Length=8 x filecount, First 4 bytes is location, next 4 is length).
A section containing the file data.
A 110 byte footer of unknown content(probably some sort of checksum or signature)

vromfs files may optionally be zlib deflated.
If compressed the compression will start at 0x10, also the decompressed file length will be in the header.
I wrote a basic tool to extract files from these archives.
[You can download it from github.](https://github.com/magJ/dagor-archive/releases)(Requires Java 1.7)

dxp.bin
Header Bytes: 44 78 50 32 02 00 00 00 (DxP2)
Description:
These archives appear to contain textures is DDS format.
These files appear similar in layout to the vromfs files, however they seem to contain an extra section for DDS headers.
I could probably extract these and if I knew anything about DDS files/headers I might be able to do something useful with them.
At the moment they aren't my top priority.

grp
Header Bytes: 47 52 50 32 (GRP2)
Description:
I dont really know what these files contain. Probably 3d models. Based on the names.
Its fairly simple to get a file listing, but I haven't been able to get much further than that.
I am hesitant to put much effort into these as I don't know if there is any useful data inside.

blk
Header Bytes:00 42 42 46 02 00 00 00 (BBF)
Description:
These are the files I am most interested in the the moment.
These files appear to be compiled markup.
The vromfs archives are full of these.
There is one example of a user editable uncompiled blk file in the root directory of the game (config.blk).
The uncompiled file is JSON like, it has nested key values with explicit types.
I would like to be able to convert the compiled blk's back to the plaintext version.

Here is a shortened example of the plaintext version:

```
cloudsQuality:t="high"
doShowDriversOutdated:b=yes
graphicsQuality:t="user"
renderer2:t="auto"

video{
  mode:t="fullscreen"
  postfx_antialiasing:t="high_fxaa"
  vsync:b=no
  resolution:t="2560 x 1440"
}

graphics{
  shadowQuality:t="medium"
  texquality:t="high"
  anisotropy:i=8
  numCloudLayers:i=80
  fxTexScale:r=0.25
  lastClipSize:i=8192
  fxDensityMul:r=0.9
}

render{
  selfReflection:b=yes
  motionBlur:b=no
  ssaoQuality:i=0
}
```

Compared to a hex dump of a compiled version(different data):


So there are a few thing I would like some help with:
First of all, if anyone knows of any tools that work with these files, or knows where I can get dagor engine dev kits, then that would be appreciated.

Otherwise, I would like some help decompiling the blk files. Maybe someone can help decipher them for me.
Some hints on what to do with the DDS files would be helpful too.

If anyone needs sample files let me know, otherwise WarThunder is free to play and it can be downloaded quite easily.
You can then use my above tool to extract the vromfs files.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-23T20:49:23+00:00
- Post Title: Warthunder/Dagor Engine archives.

Very nice. Tested on Blades of Time ?
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-03-23T21:05:51+00:00
- Post Title: Warthunder/Dagor Engine archives.

Yeah I have been working on these games.
The problem is I can not find the compressed size for model files.
I have no idea where its stored.
## Post #4
- Username: WatchDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 17, 2014 8:48 pm
- Post datetime: 2014-03-24T07:16:56+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from Ekey
>
> Very nice. Tested on Blades of Time ?
No, I haven't tried it on any other games.
## Post #5
- Username: WatchDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 17, 2014 8:48 pm
- Post datetime: 2014-04-19T13:17:21+00:00
- Post Title: Warthunder/Dagor Engine archives.

So I just found out that there are official tools available for this game: [http://warthunder.com/en/news/541-The-W ... der-CDK-en](http://warthunder.com/en/news/541-The-War-Thunder-CDK-en)
## Post #6
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-10-29T07:53:29+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from WatchDog
>
> So I just found out that there are official tools available for this game: http://warthunder.com/en/news/541-The-W ... der-CDK-en
This tool cannot export model for browsing
## Post #7
- Username: InnerCircle
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 01, 2014 12:29 am
- Post datetime: 2014-11-16T22:33:32+00:00
- Post Title: Warthunder/Dagor Engine archives.

someone has created a tool to at least extract  .vromfs.bin and dxp.bin archives

[http://forum.warthunder.com/index.php?/ ... extractor/](http://forum.warthunder.com/index.php?/topic/155747-vromfsbin-resource-viewerextractor/)
## Post #8
- Username: kol93
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 20, 2014 5:59 pm
- Post datetime: 2014-11-20T10:05:29+00:00
- Post Title: Warthunder/Dagor Engine archives.

Are you still interrested in compiling/decompiling BBF (BLK) files?
I know, that this format is used to build requests/responses of your actions in (at least) hangar (War Thunder). And I have to give you some requests/responses and describe you them. Also I can intercept more requests/responses from client.
## Post #9
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-23T11:22:46+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from InnerCircle
>
> someone has created a tool to at least extract  .vromfs.bin and dxp.bin archives

http://forum.warthunder.com/index.php?/ ... extractor/Thank you, this is very good news, this model has done a very fine game, I really like, I hope everyone can participate in the game, this is the download address tool : [http://www.nexusmods.com/warthunder/mods/617/](http://www.nexusmods.com/warthunder/mods/617/)?
## Post #10
- Username: WatchDog
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Mar 17, 2014 8:48 pm
- Post datetime: 2015-05-01T00:56:19+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from kol93
>
> Are you still interrested in compiling/decompiling BBF (BLK) files?
I know, that this format is used to build requests/responses of your actions in (at least) hangar (War Thunder). And I have to give you some requests/responses and describe you them. Also I can intercept more requests/responses from client.
I am still interested, i haven't done any work on this for quite a while, but I would like to have another crack at it.
## Post #11
- Username: PlanesFan1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 27, 2015 1:12 am
- Post datetime: 2015-06-26T17:15:32+00:00
- Post Title: Warthunder/Dagor Engine archives.

Any recent progress on this? I would like to extract the model files.
## Post #12
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-03T06:07:09+00:00
- Post Title: Warthunder/Dagor Engine archives.

Working tools here: [https://github.com/klensy/wt-tools](https://github.com/klensy/wt-tools)
But nothing for grp unpack/convert
## Post #13
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2015-12-03T06:53:25+00:00
- Post Title: Warthunder/Dagor Engine archives.

Blender 2.49b .grp import script. 

[viewtopic.php?p=73250#p73250](http://forum.xentax.com/viewtopic.php?p=73250#p73250)

Tested on Blades of Time, it works. Gives geometry and uv
## Post #14
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-04T08:40:18+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from DXFan619
>
> Blender 2.49b .grp import script.
Not working, I'll try to ask author for update it for WT.

I track how game loads model, by logging file reads at the moment I switched to Leopard 1 tank preview:

```
Q:\Games\WarThunder\res\germ_gm.grp
Q:\Games\WarThunder\res\collision_pack.grp
Q:\Games\WarThunder\res\gm_logic.grp
Q:\Games\WarThunder\res\germ_gm.grp
Q:\Games\WarThunder\res\gm.dxp.bin
Q:\Games\WarThunder\res\lowquality_gm.dxp.bin
Q:\Games\WarThunder\content\pkg_main\res\pkg_main_gm.dxp.bin
Q:\Games\WarThunder\content\pkg_main\res\pkg_main_tanks\germ_leopard_1.dxp.bin
Q:\Games\WarThunder\ui\tex.vromfs.bin
Q:\Games\WarThunder\content\pkg_main\res\pkg_main_tanks\germ_leopard_1.dxp.bin
Q:\Games\WarThunder\content\hq_tex\res\hq_tex_lowquality_gm.dxp.bin
```

Looks like all german tanks groupped into one big file (125 Mb) germ_gm.grp
Script not loads anything if I try to import this GRP, but log looks promising (attached).
I try also small plane file from res\aircrafts\a5m.grp - log looks similar:

```


(232, 232, 329636, 128, 3, 0, 0, 140, 3)
0 a5m4_cockpit_skeleton
1 a5m4_cockpit
2 a5m4_cockpit_anim
0 (109, 27, 248, 86) (256, 0, 0, 0, 55748, 46263)
1 (224, 58, 0, 0) (1, 0, 34553, 16581, 38224, 4)
2 (2, 0, 0, 0) (55748, 46263, 1, 1, 0, 0)
SECTION
```


Samples of GRP's is uploaded [here](https://yadi.sk/d/flWM522HkxduP) (114 Mb).
[WT_germ_gm_log.zip](https://xentaxbackup.github.io/file/10102_WT_germ_gm_log.zip)
## Post #15
- Username: divmass
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 03, 2016 1:19 pm
- Post datetime: 2016-06-03T05:55:55+00:00
- Post Title: Warthunder/Dagor Engine archives.

> Reply from Andrakann
>
> Working tools here: https://github.com/klensy/wt-tools
But nothing for grp unpack/convert

I have a server responses to client requests  from hangar. They have blk format (Header Bytes:00 42 42 46 02 00 00 00). But this utility are not completely unpacked server responses.
Anyone can help me?
[resp.ZIP](https://xentaxbackup.github.io/file/11002_resp.ZIP)
## Post #16
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-03-03T17:00:49+00:00
- Post Title: Re: Warthunder/Dagor Engine archives.

Any news  ?
## Post #17
- Username: NatoriousB
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 14, 2020 6:48 pm
- Post datetime: 2021-02-09T06:37:08+00:00
- Post Title: Re: Warthunder/Dagor Engine archives.

I'm interested in this as well. I just found the game and the vehicles are amazing. The CDK doesn't support the latest version of Blender and it would be nice to have the models in a format that can be imported into Blender.
