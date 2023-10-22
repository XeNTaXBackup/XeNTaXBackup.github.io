## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-08T09:47:59+00:00
- Post Title: Legend of Grimlock [.dat file]

Since the whole .dat file is too big (over 300 MB), I've uploaded the start and the end of the file, using Mr. Mouse's FileCutter tool.
Could somebody take a look at it, please?
Thanks.

Had to remove link, because of the new rules.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-04-08T14:20:23+00:00
- Post Title: Legend of Grimlock [.dat file]

```
idstring GRAR
get NR_OF_FILES long
for i = 0 < NR_OF_FILES
  get FILE_ID long
  string namehex p= "%08x" FILE_ID
  get START_POS long
  get PACKED_SIZE long
  get ORIGINAL_SIZE long

  if PACKED_SIZE == 0
    log namehex START_POS ORIGINAL_SIZE
  else
    set THE_POS long 4
    math THE_POS += START_POS
    set THE_SIZE long -4
    math THE_SIZE += START_POS
    clog namehex THE_POS THE_SIZE ORIGINAL_SIZE
  endif
next i
```
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-08T16:12:48+00:00
- Post Title: Legend of Grimlock [.dat file]

Thanks bacter! Sadly the files in them seem weird, without any extensions, but I'll wait the final version of the game, maybe it'll differ from them.
## Post #4
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2012-04-12T20:13:38+00:00
- Post Title: Legend of Grimlock [.dat file]

Minor update, extract with extension ...

```
idstring GRAR
get NR_OF_FILES long
for i = 0 < NR_OF_FILES
  get FILE_ID long
  string namehex p= "%08x" FILE_ID
  get START_POS long
  get PACKED_SIZE long
  get ORIGINAL_SIZE long

  if PACKED_SIZE == 0
    log namehex START_POS ORIGINAL_SIZE
  else
    set THE_POS long 4
    math THE_POS += START_POS
    set THE_SIZE long -4
    math THE_SIZE += START_POS
    clog namehex THE_POS THE_SIZE ORIGINAL_SIZE
  endif
  
  Open . namehex 1
  Get TYPE long 1
  
  string name p= "%08x.unk" FILE_ID
  
  if TYPE == 0x014A4C1B
	string name p= "%08x.script" FILE_ID
  endif
  if TYPE == 0x46464952
	string name p= "%08x.wav" FILE_ID
  endif
  if TYPE == 0x4853454d
	string name p= "%08x.mesh" FILE_ID
  endif
  if TYPE == 0x314c444d
	string name p= "%08x.mdl" FILE_ID
  endif
  if TYPE == 0x20534444
	string name p= "%08x.dds" FILE_ID
  endif
  if TYPE == 0x4d494e41
	string name p= "%08x.anim" FILE_ID
  endif
  if TYPE == 0x00000100
	string name p= "%08x.ttf" FILE_ID
  endif
  if TYPE == 0x4d495247
	string name p= "%08x.grim" FILE_ID
  endif
  if TYPE == 0x5367674f
	string name p= "%08x.ogg" FILE_ID
  endif
  if TYPE == 0x000A0000
	string name p= "%08x.tga" FILE_ID
  endif

  log name 0 ORIGINAL_SIZE 1
  
next i

```


P.S. Anyone know how delete file in .bms ?
## Post #5
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-12T20:27:20+00:00
- Post Title: Legend of Grimlock [.dat file]

There is no "TYPE", it is filename hash  I have working extractor with almost 1/3 filenames. But it takes some time to get all filenames. Hash count is easy.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:40:25+00:00
- Post Title: Legend of Grimlock [.dat file]

Please review the new forum rules. 
[viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
## Post #7
- Username: eferdi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 13, 2012 8:33 am
- Post datetime: 2012-04-13T00:36:50+00:00
- Post Title: Legend of Grimlock [.dat file]

where can i get the grimrock file extractor?
soon we can start do mod this awesome game
## Post #8
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T08:33:22+00:00
- Post Title: Legend of Grimlock [.dat file]

I will release it later today.
## Post #9
- Username: eferdi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 13, 2012 8:33 am
- Post datetime: 2012-04-13T09:37:24+00:00
- Post Title: Legend of Grimlock [.dat file]

awesome would be a rebuild function so we can put new or modified content into the game
## Post #10
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T10:48:15+00:00
- Post Title: Legend of Grimlock [.dat file]

I think engine is able to load files outside of archive with higher priority. But I have to check it. Otherwise repack is not problem. I'm still gathering filenames to create full list. Just wait
## Post #11
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-13T11:20:46+00:00
- Post Title: Legend of Grimlock [.dat file]

Just wow, every time I want to translate something XRaptor appears with his super-duper extractor/repacker   Thank you!
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2012-04-13T11:39:44+00:00
- Post Title: Legend of Grimlock [.dat file]

If i'm not mistaken the game uses the 32 bit FNV-1a algorithm for the hash calculation.
## Post #13
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T12:21:13+00:00
- Post Title: Legend of Grimlock [.dat file]

> Reply from bacter
>
> If i'm not mistaken the game uses the 32 bit FNV-1a algorithm for the hash calculation.
yes, you are right
## Post #14
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T15:57:56+00:00
- Post Title: Legend of Grimlock [.dat file]

Ok, so here it is:

Legend of Grimrock DAT File Extractor
[http://raptor.cestiny.cz/download/legen ... actor.html](http://raptor.cestiny.cz/download/legend-of-grimrock-dat-file-extractor.html)

Quick info:
Because of hashed filenames, I had to create hashtable.txt file and include it to extractor. So don't delete it  Now still missing 299 filenames, so only hashes are extracted. But it is not problem, everyone can help to finish it 

HashCounter tool is included. So you can simply check hashes for any file. If you will find any new file, simply add it to input.txt file, use HashCounter application and let it generate new hashtable.txt. Then use extractor again. 

In hashtable are many files never used in game, but just ignore those items (like dll files etc.). They left from automatic scanning. Game itself uses in-game extension conversion. So for example if it looks for file model.fsb, it means than engine is looking for model.mesh and model.model files or model.animation file. The same it is for *.tga - it looks for *.d3d9_texture etc. But it is not important for you.

About repack - just check if game takes extracted files first. I'm now little lazy to test it (I want to play this game now). There is no problem to implement repack later.

So enjoy it.
## Post #15
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-13T16:16:19+00:00
- Post Title: Legend of Grimlock [.dat file]

> Reply from XRaptor
>
> Ok, so here it is:

Legend of Grimrock DAT File Extractor
http://raptor.cestiny.cz/download/legen ... actor.html

Quick info:
Because of hashed filenames, I had to create hashtable.txt file and include it to extractor. So don't delete it  Now still missing 299 filenames, so only hashes are extracted. But it is not problem, everyone can help to finish it 

HashCounter tool is included. So you can simply check hashes for any file. If you will find any new file, simply add it to input.txt file, use HashCounter application and let it generate new hashtable.txt. Then use extractor again. 

In hashtable are many files never used in game, but just ignore those items (like dll files etc.). They left from automatic scanning. Game itself uses in-game extension conversion. So for example if it looks for file model.fsb, it means than engine is looking for model.mesh and model.model files or model.animation file. The same it is for *.tga - it looks for *.d3d9_texture etc. But it is not important for you.

About repack - just check if game takes extracted files first. I'm now little lazy to test it (I want to play this game now). There is no problem to implement repack later.

So enjoy it.
Great work!   As you suspected, the game CAN read from external files, but as I've seen, the gametexts are in .lua files. If I edit them directly, with Notepad++, I get an error. Are there any specific editors for these kind of files?
## Post #16
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2012-04-13T16:19:15+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

lostprophet, how u made game work with external files?
## Post #17
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T16:21:07+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Lua is compiled script, so there is no editor. I think that from version 5+ there is no way how to decompile them. So all you can do is hexedit it and you have to use the same length as original string.
## Post #18
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-13T16:21:50+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from XRaptor
>
> Lua is compiled script, so there is no editor. I think that from version 5+ there is no way how to decompile them. So all you can do is hexedit it and you have to use the same length as original string.
Ouch.
## Post #19
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-04-13T16:57:22+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

How do you get the game to recognize external files?

I've tried extracting the whole .dat and placing the contents in the games folder, placing the contents in a folder called grimrock & grimrock.dat and nothing worked
## Post #20
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T17:04:01+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

And why you are trying to put all extracted files to game?  As I wrote, game engine is looking for other files then they are named, so it 100% works with lua files. There is no naming conversion for lua files.
## Post #21
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-13T17:32:11+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Itze
>
> How do you get the game to recognize external files?

I've tried extracting the whole .dat and placing the contents in the games folder, placing the contents in a folder called grimrock & grimrock.dat and nothing worked
I've tried it with MainMenu.lua. I opened it up in Notepad++, changed some "Cancel" texts to "Mégsem" (only the ones starting with capital C's), and put it in the game's main directory.
## Post #22
- Username: semi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2012 1:34 am
- Post datetime: 2012-04-13T17:36:32+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

LoG uses [LuaJIT](http://luajit.org/) compiled bytecode. IIRC there is no decompiler, but you can print out bytecode nicely by doing:

$ luajit -bl MyFile.lua

Hope that helps
## Post #23
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T18:24:06+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I never used lua script or binaries, but what are this bytecode exports for? Is there any way how to modify them and recompile back to lua?
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-13T21:16:46+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

New Filenames.

```
assets/data/animation_events.lua
shaders/d3d9/base.hlsl
shaders/d3d9/Fxaa3_8.h
```
## Post #25
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T21:22:18+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

$wallset is variable like 'dungeon', 'prison', 'temple'. So if you will find more dungeon types, it will be ok
## Post #26
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-13T21:23:43+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Okay 

Have strange problem with file - assets/shaders/crystal.hlsl

PS: it's modified executable for debugging new filenames  



Hash for this file : 55995FE5. But after unpacking the archive I not found this hash like : UNKNOWN_HASH\55995FE5.
Any ideas  ?
## Post #27
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-13T21:36:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I don't know. Maybe this error dialog modifies file path? Hash counting is case sensitive, so it should be crystal.hlsl or Crystal.hlsl and hashes are different. BTW this file is included in hashtable.txt, but file doesn't exists. But more lua scripts points to it.

EDIT:
Updated tables. You points me to get some more model and meshes files  Simply put them to extractor folder.


 tables.rar
(37.35 KiB) Downloaded 39 times
## Post #28
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-04-13T23:58:24+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

[http://luadec51.luaforge.net/](http://luadec51.luaforge.net/)

Just found this. Untested. But MAYBE it'll work?
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-14T00:09:17+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

```
assets/samples/characters/damage_male_03.wav
assets/samples/characters/damage_male_04.wav
assets/samples/characters/damage_lizardman_02.wav
assets/samples/characters/damage_lizardman_03.wav
assets/samples/characters/damage_minotaur_03.wav
assets/samples/characters/party_move_03.wav
assets/samples/characters/party_move_04.wav
assets/samples/characters/party_move_05.wav
assets/samples/monsters/ogre_attack_02.wav
assets/samples/monsters/ogre_hit_01.wav
assets/samples/monsters/snail_attack_02.wav
assets/samples/monsters/spider_attack_02.wav
assets/samples/weapons/hit_flesh_02.wav
assets/models/items/sword01.mesh
assets/models/items/sword01.model
assets/models/items/torch_lit.mesh
assets/models/items/torch_lit.model
assets/models/props/temple_floor_corpse.mesh
assets/models/props/temple_floor_corpse.model
assets/models/props/props_rock_medium01.mesh
assets/models/props/props_rock_medium01.model
assets/models/props/temple_wall_dirt_01.mesh
assets/models/props/temple_wall_dirt_01.model
assets/models/props/temple_wall_dirt_02.mesh
assets/models/props/temple_wall_dirt_02.model
assets/models/props/temple_wall_moss_01.mesh
assets/models/props/temple_wall_moss_01.model
assets/models/props/temple_wall_moss_02.mesh
assets/models/props/temple_wall_moss_02.model
assets/models/wall_sets/dungeon/goromorg_statue_02.mesh
assets/models/wall_sets/dungeon/goromorg_statue_02.model
assets/models/wall_sets/dungeon/goromorg_statue_03.mesh
assets/models/wall_sets/dungeon/goromorg_statue_03.model
assets/models/wall_sets/dungeon/goromorg_statue_04.mesh
assets/models/wall_sets/dungeon/goromorg_statue_04.model
assets/models/wall_sets/temple/goromorg_statue_02.mesh
assets/models/wall_sets/temple/goromorg_statue_02.model
assets/models/wall_sets/temple/goromorg_statue_03.mesh
assets/models/wall_sets/temple/goromorg_statue_03.model
assets/models/wall_sets/temple/goromorg_statue_04.mesh
assets/models/wall_sets/temple/goromorg_statue_04.model
```
## Post #30
- Username: ymgve
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 14, 2012 6:26 am
- Post datetime: 2012-04-14T01:41:53+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

After combining and cleaning all the previous lists and adding a few files of my own, these are the currently known file names: [http://pastebin.com/nnKM34iB](http://pastebin.com/nnKM34iB)

It appears the files are mostly sorted alphabetically inside the dat file, so one might be able to guess what the other filenames are. I've made a more detailed list here: [http://pastebin.com/U5Bqtq44](http://pastebin.com/U5Bqtq44)
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-15T12:09:28+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Here new updated.
[tables_2.rar](https://xentaxbackup.github.io/file/5306_tables_2.rar)
## Post #32
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-15T14:45:16+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Thnx for helping with filenames. So here is last merged version with all knows filenames without nonexists crap (dll, fsb, ...). Still 151 is missing.


 tables.rar
(26.99 KiB) Downloaded 36 times
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-15T16:29:17+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

New 

```
assets/animations/wall_sets/prison/lever_up.animation
assets/animations/wall_sets/prison/wall_secret_button_tiny_press.animation
assets/animations/wall_sets/prison/wall_secret_button_large_press.animation
```

Upd. - my decompiled lua's for translators to other languages 

[dreams.lua](http://pastebin.com/DuJfKqPb)
[intro.lua](http://pastebin.com/b2ywfNf6)
[end_cinematic.lua](http://pastebin.com/kxd8HyP5)
## Post #34
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-15T21:49:28+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> New 
Code: Select allassets/animations/wall_sets/prison/lever_down.animation
assets/animations/wall_sets/prison/lever_up.animation
assets/animations/wall_sets/prison/wall_secret_button_tiny_press.animation
assets/animations/wall_sets/prison/wall_secret_button_large_press.animation
Upd. - my decompiled lua's for translators to other languages 

dreams.lua
intro.lua
Wow, just 2 questions:
-Can the other .lua files be decompiled too?
-Do they work with the game?
## Post #35
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-15T22:37:31+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Sure. It is necessary to lay all loaders the Lua where main executable. Example.
For file -> assets/data/intro.lua need loader GameMode.lua. If the loader will not be there where the main executable is into.lua will not work.

Here screens 

[http://img7.imageshack.us/img7/8663/gri ... 231141.png](http://img7.imageshack.us/img7/8663/grimrock201204160231141.png)
[http://img193.imageshack.us/img193/2844 ... 231214.png](http://img193.imageshack.us/img193/2844/grimrock201204160231214.png)
[http://img827.imageshack.us/img827/7046 ... 231266.png](http://img827.imageshack.us/img827/7046/grimrock201204160231266.png)
## Post #36
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-15T22:49:48+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> Sure. It is necessary to lay all loaders the Lua where main executable. Example.
For file -> assets/data/intro.lua need loader GameMode.lua. If the loader will not be there where the main executable is into.lua will not work.

Here screens 

http://img7.imageshack.us/img7/8663/gri ... 231141.png
http://img193.imageshack.us/img193/2844 ... 231214.png
http://img827.imageshack.us/img827/7046 ... 231266.png
Great job finding this out! I've downloaded the files from pastebin above, but they have txt extensions. Do I have to rename them to lua? I've extracted Grimrock.dat and put the GameMode.lua and the modified intro.lua to the installation folder, but nothing changed ingame.
## Post #37
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-15T23:27:48+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Yep txt extension need to change to lua.

Example :

Installed game to : D:\Games\Legend of Grimrock
GameMode.lua - need copy to D:\Games\Legend of Grimrock
intro.lua - need copy to D:\Games\Legend of Grimrock\assets\data\
## Post #38
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-15T23:35:01+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> Yep txt extension need to change to lua.

Example :

Installed game to : D:\Games\Legend of Grimrock
GameMode.lua - need copy to D:\Games\Legend of Grimrock
intro.lua - need copy to D:\Games\Legend of Grimrock\assets\data\
Hmmm..

Changed line in intro.lua "Mount Grimrock" to "Grimrock hegység".

Installed game to: D:\Steam\steamapps\common\Legend of Grimrock
Copied GameMode.lua to: D:\Steam\steamapps\common\Legend of Grimrock
Copied intro.lua to: D:\Steam\steamapps\common\Legend of Grimrock\assets\data

When I start a new game, "Mount Grimrock" appears in the intro, not "Grimrock hegység". I don't really know, what I'm doing wrong.
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T00:08:57+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I make small video ([here](http://www.mediafire.com/?uu52c6hcosb4i62)). Try this method
## Post #40
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-16T00:37:57+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> I make small video (here). Try this method
Method works great, cheers! Will you decompile the other .lua files too?:)
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T00:47:54+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Maybe
## Post #42
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-16T08:10:44+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Because game engine ignores some extracted files, I made a new version of extractor with repack feature. I will release it later with updated hashtable.txt list.
## Post #43
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-16T09:37:44+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I've tried to edit the font files, which are in assets/fonts, but somehow the game doesn't read them. AFAIK, the loader for the fonts is Gui.lua, which I put in the installation directory and I've put the modified font files to assets/fonts.
## Post #44
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-04-16T09:40:08+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> Maybe

Couldn't you share the howto to actually decompile those files?
## Post #45
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-16T09:49:43+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

As I said before, here is updated version with repack feature.

Legend of Grimrock DAT File Extractor
[http://raptor.cestiny.cz/download/legen ... actor.html](http://raptor.cestiny.cz/download/legend-of-grimrock-dat-file-extractor.html)
## Post #46
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T11:51:46+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from XRaptor
>
> As I said before, here is updated version with repack feature.

Legend of Grimrock DAT File Extractor
http://raptor.cestiny.cz/download/legen ... actor.html
Good job X  

> Reply from Vash
>
> 
Couldn't you share the howto to actually decompile those files?
This game used compiled LUA with LuaJit.

Example use: luajit -bl skills.lua skills.out

Output file - bytecode listing like (skills.lua) this :

```
0001    GGET     0   0      ; "defineSkill"
0002    TDUP     1   1
0003    TNEW     2  17
0004    GGET     3   2      ; "stat"
0005    KSHORT   4   2
0006    KSTR     5   3      ; "strength"
0007    KSHORT   6   1
0008    CALL     3   2   4
0009    TSETB    3   2   1
0010    GGET     3   2      ; "stat"
0011    KSHORT   4   5
0012    KSTR     5   4      ; "vitality"
0013    KSHORT   6   2
0014    CALL     3   2   4
0015    TSETB    3   2   2
0016    GGET     3   2      ; "stat"
0017    KSHORT   4   8
0018    KSTR     5   5      ; "health"
0019    KSHORT   6  10
0020    CALL     3   2   4
0021    TSETB    3   2   3
0022    GGET     3   6      ; "talent"
0023    KSHORT   4  10
0024    KSTR     5   7      ; "endurance"
```

[here](http://lua-users.org/wiki/LuaJit) Bytecode Instructions. Maybe later I will make video how decompile
## Post #47
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-04-16T12:13:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

oh so you basically translate asm->lua by hand?
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T12:21:14+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Yep
## Post #49
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-04-16T12:29:14+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

lol that's harsh, thanks anyway, I'll give it a try if I find some time
## Post #50
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T16:39:53+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

[Here](http://www.mediafire.com/?3qu281a9fa579oo) video decompiling assets\dungeons\menu\level01.lua with minimal descriptions.
## Post #51
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-16T17:00:14+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

nice video, thnx
## Post #52
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-16T17:17:33+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Is there a compiled JuaJit binary somewhere?
## Post #53
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-16T17:29:52+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from lostprophet
>
> Is there a compiled JuaJit binary somewhere?
beta 8 for example 
[http://sourceforge.net/p/safelua/wiki/L ... 0binaries/](http://sourceforge.net/p/safelua/wiki/LuaJIT%20binaries/)
## Post #54
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-16T18:17:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from XRaptor
>
> lostprophet wrote:Is there a compiled JuaJit binary somewhere?
beta 8 for example 
http://sourceforge.net/p/safelua/wiki/L ... 0binaries/
It says: "unknown LuaJit command or jit.* modules not installed."
I do everything to the letter, that was shown in the video above.
UPDATE: Beta 9 works
## Post #55
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T18:17:45+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

LuaJIT-2.0.0-beta 9 attached

The only one problem is that LuaJIT refuses to work with large strings and const 

```
dungeon.lua
items.lua
monsters.lua
skills.lua
```

[LuaJIT-2.0.0-beta9.rar](https://xentaxbackup.github.io/file/5310_LuaJIT-2.0.0-beta9.rar)
## Post #56
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-16T18:22:06+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> LuaJIT-2.0.0-beta 9 attached

The only one problem is that LuaJIT refuses to work with large strings and const 
Code: Select allanimation_events.lua
dungeon.lua
items.lua
monsters.lua
skills.lua
Yeah, it's true:

```
0062    KSTR     5  30      ; "- Left click on an item to pick it up fr"~
0063    KSTR     6  31      ; "- You can change the marching order by d"~
```

The end of each line is missing
## Post #57
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-16T18:35:06+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from lostprophet
>
> 
Yeah, it's true:
Code: Select all0061    KSTR     4  29      ; "- The item slots are used for attacking "~
0062    KSTR     5  30      ; "- Left click on an item to pick it up fr"~
0063    KSTR     6  31      ; "- You can change the marching order by d"~
The end of each line is missing

There is not the problem. This reduction in the line. Totally can be extracted from the original.
Example with talents.lua

```
0001    GGET     0   0      ; "defineTalent"
0002    TDUP     1   1
0003    CALL     0   1   2
0004    GGET     0   0      ; "defineTalent"
0005    TDUP     1   2
0006    CALL     0   1   2
0007    GGET     0   0      ; "defineTalent"
0008    TDUP     1   3
0009    CALL     0   1   2
0010    GGET     0   0      ; "defineTalent"
0011    TDUP     1   4
0012    CALL     0   1   2
0013    GGET     0   0      ; "defineTalent"
0014    TDUP     1   5
0015    CALL     0   1   2
0016    GGET     0   0      ; "defineTalent"
0017    TDUP     1   6
0018    CALL     0   1   2
0019    GGET     0   0      ; "defineTalent"
0020    TDUP     1   7
0021    CALL     0   1   2
0022    GGET     0   0      ; "defineTalent"
```


I don's see here KSTR instructions. Because in the original they are.

```
Thunderstruck
name
lightning_speed
description You are fast, very fast.
```
## Post #58
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-16T18:40:40+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

You can disable lines truncate, it is defined in jit\bc.lua
Simply change

```
kc = format(#kc > 40 and '"%.40s"~' or '"%s"', gsub(kc, "%c", ctlsub))
```

to

```
kc = format('"%s"', gsub(kc, "%c", ctlsub))
```
## Post #59
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-04-17T07:19:50+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Upload please all decompiled lua-files.
For translation game
## Post #60
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-17T08:25:09+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I think that manual "decompiling" actual lua scripts is waste of time because of upcoming patch. They can change files and you have to start again.
## Post #61
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-04-17T13:16:46+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Ekey just watched your tutorial... damn good work
## Post #62
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-17T14:38:27+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

It is a pity that all LUA not be able to decompile. LUAJit bugged and not all records ByteCode instructions
## Post #63
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-04-17T16:56:35+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

i guess they'll release the mod tools soon... people in the official forum are begging for them and especially translations
## Post #64
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-17T18:56:28+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

They planning release only LUA API and MapTool nothing more.
## Post #65
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-18T09:35:42+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> They planning release only LUA API and MapTool nothing more.
Does the LUA API mean we will be able to decompile the .lua files properly?
## Post #66
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-04-18T09:42:21+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

no, it means that you could write your own modules using the LUA functions they write (and compile) probably..
## Post #67
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-18T12:09:22+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Vash
>
> no, it means that you could write your own modules using the LUA functions they write (and compile) probably..
Exactly
## Post #68
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2012-04-18T12:21:17+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

in theory they actually COULD write some translate functions...the question is "will they?"
## Post #69
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-18T12:25:33+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

There is no need to do "translate functions". They should simply give uncompilled scripts with texts and that's all. But they are against modding and distributing of original game files.
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-18T12:32:25+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Removed
## Post #71
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T06:51:24+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Well, just to let you know, I just made silent update of version 1.1 on my website. No version change. Just redownload archive. I just added some more filenames to list and added error handler to application for checking 'hashtable.txt'. Some users have problem that application doesn't load that file. So now there is error message if file not found with location where exe is looking for that file. I hope it will help.
## Post #72
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2012-04-19T09:10:14+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

```
assets/models/props/prison_floor_corpse.model
assets/models/swipes/swipe_combo_cross.mesh
assets/models/swipes/swipe_combo_cross.model
assets/models/wall_sets/dungeon/wall_rune.mesh
assets/models/wall_sets/dungeon/wall_rune.model

```
## Post #73
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T12:52:08+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

```
assets/models/props/props_rubble_low01.model
assets/models/props/props_wood_barrel01.mesh
assets/models/props/props_wood_barrel01.model
assets/models/props/props_torch01.mesh
assets/models/props/props_torch01.model
assets/models/wall_sets/temple/wall_moss.mesh
assets/models/wall_sets/temple/wall_moss.model
```
## Post #74
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T13:29:50+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Ok, here is actual hashlist.txt file. Helper file included.

115 file names is missing.
## Post #75
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T15:49:47+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Thanks X for update. I extract full archive with new hashtable and total missing files = 128 not 115
## Post #76
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T15:57:09+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Strange, try to redownload attachment. There are 2218 filenames in hashtable.txt + 115 missing it is 2333 total.
## Post #77
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T16:04:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Ops my bad. I thought that it was necessary to put the hashtable in the game folder
## Post #78
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T16:19:05+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

No, it is simply external dictionary for extractor. List is not embeded in exe because it is not complete.
## Post #79
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T16:33:07+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

New

```
assets/models/props/prison_ivy_01.model
assets/models/props/prison_ivy_02.mesh
assets/models/props/prison_ivy_02.model
assets/models/props/prison_wall_dirt_01.mesh
assets/models/props/prison_wall_dirt_01.model
assets/models/props/prison_wall_dirt_02.mesh
assets/models/props/prison_wall_dirt_02.model
assets/models/props/prison_ceiling_roots_01.mesh
assets/models/props/prison_ceiling_roots_01.model
assets/models/props/prison_ceiling_roots_02.mesh
assets/models/props/prison_ceiling_roots_02.model
assets/models/props/prison_ceiling_roots_03.mesh
assets/models/props/prison_ceiling_roots_03.model
assets/models/props/temple_ceiling_moss_01.mesh
assets/models/props/temple_ceiling_moss_01.model
assets/models/props/temple_ceiling_moss_02.mesh
assets/models/props/temple_ceiling_moss_02.model
```
## Post #80
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T16:56:00+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

It is hard to guess filenames based on previous files  Tried many combinations. made simple tool for autocheck filenames based on hash, but it is usable only for filename parts less then 8 chars. Otherwise it takes ages to check all combinations.
## Post #81
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T17:16:16+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Model files (mesh and model) extension in begin and end of file contains names
## Post #82
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T17:36:01+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

yes, but now it is not so easy, because strings in model file is not the same like filename
## Post #83
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-19T17:52:11+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Exactly, but some of the filenames I so found 

Example:

```
assets/models/props/temple_floor_corpse.mesh
UNKNOWN_HASH/D56D8182
UNKNOWN_HASH/B98569E4
assets/models/props/temple_glass_wall_01.model
assets/models/props/temple_glass_wall_01.mesh
```

D56D8182 and B98569E4 - 100% filename begin assets/models/props/temple_%s

Edit: By the way, some filenames may be from Demo version (worth checking out)
## Post #84
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-19T18:18:07+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

yes, you are right. Trying and trying, but it takes time now.

93 to go
## Post #85
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-20T01:42:26+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Okay will soon end up decompiling items.lua
## Post #86
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2012-04-20T02:25:39+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

```
assets/models/wall_sets/prison/door_ornament_locked.mesh
assets/models/wall_sets/temple/door_ornament_locked.model
assets/models/wall_sets/temple/door_ornament_locked.mesh
lib/mesh/lwo_loader.lua
lib/mesh/obj_loader.lua
lib/render_context/d3d9.lua
lib/render_context/ogl.lua
lib/shaders/lambert.hlsl
lib/shaders/texture.hlsl

```
## Post #87
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-20T05:42:52+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I'm finally finish decompiling items.lua and they ready to translate and modifiy.

Translatable instructions:

```
description
```


Meet : Just killer 

[http://img221.imageshack.us/img221/2008 ... 931135.png](http://img221.imageshack.us/img221/2008/grimrock201204200931135.png)
[http://img807.imageshack.us/img807/5807 ... 931317.png](http://img807.imageshack.us/img807/5807/grimrock201204200931317.png)

If you found bug let me know. Have fun 
[items_decompiled.rar](https://xentaxbackup.github.io/file/5334_items_decompiled.rar)
## Post #88
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-20T09:17:37+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Decompiled skills. 

Translatable instructions: See the previous post.
[skills_decompiled.rar](https://xentaxbackup.github.io/file/5335_skills_decompiled.rar)
## Post #89
- Username: XR3
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 07, 2011 1:17 pm
- Post datetime: 2012-04-20T09:34:03+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

@Ekey

You are the Best !   
Thx for new Lua.
## Post #90
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-20T09:42:57+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Talents out 
[talents_decompiled.rar](https://xentaxbackup.github.io/file/5336_talents_decompiled.rar)
## Post #91
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2012-04-20T10:20:38+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

```
assets/animations/monsters/guardian/guardian_attack_left.animation
assets/animations/monsters/herder/herder_small_top_attack.animation
assets/animations/monsters/tunnel_ogre/tunnel_ogre_get_hit.animation
assets/particles/cube_hit_wall.psys

```
## Post #92
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-21T07:04:02+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Great work   I've been working the last three days and I come home for this
## Post #93
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-22T23:32:09+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So how many lua files are left for decompiling?
## Post #94
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T00:12:10+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I decompiled last 2 lua's : animation_events.lua and samples.lua it's not for translate, just for modify or adding new animations and sounds.
For translate puzzle descriptions need decompile all levels. In decompiling many people are not interested.
I do not want just do it alone  . Anyway I do not know very well the Lua language.
## Post #95
- Username: dogkarl
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Sep 10, 2010 2:56 pm
- Post datetime: 2012-04-23T03:05:47+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> I decompiled last 2 lua's : animation_events.lua and samples.lua it's not for translate, just for modify or adding new animations and sounds.
For translate puzzle descriptions need decompile all levels. In decompiling many people are not interested.
I do not want just do it alone  . Anyway I do not know very well the Lua language.

Well, I am interested in translation. I have a lot of experience of C++ and reverse engineering, but I have no knowledge of lua before I encounter this game. Downloaded your video, now trying to decompile mainmenu.lua. If success, will share the decompiled files. Maybe we can work together?
## Post #96
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-23T11:07:03+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Added files from last patch + some found filenames. 
75 to go.
## Post #97
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T12:47:42+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

X you forgot adding 1 filename

```
assets/particles/cube_hit_wall.psys
```
## Post #98
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-23T12:55:46+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

ups, yeah, you are right. Added for future publish. 
I just added all reported files, but somehow this one is missing now in list, sorry
## Post #99
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T13:01:50+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Here last decompiled lua's
[animation_events_&_samples.rar](https://xentaxbackup.github.io/file/5352_animation_events_&_samples.rar)
## Post #100
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-23T15:27:20+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Hello guys,
i am interested in decompiling too, but i dont understand the lua language well.
When i tried to decompile the tutorial.lua and the first lines are
0001    KNUM     0   0      ; 0.1
0002    GGET     1   0      ; "enableUserInput"
0003    KPRI     2   2
0004    CALL     1   1   2

and i dont know how to write the first function....
kind of disapointing... i only came up with this
[0.1]=(enableUserInput(true))
but i know thats not going to work

i am from germany so i need a better tutorial for this lua-language.
Only the bytecode description doesnt help at all. Maybe someone know a good tutorial-site?

sry for my bad english, but i realy want to help and translate this into german
## Post #101
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T16:03:16+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Like this 

```
x=enableUserInput(true)
```
## Post #102
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-23T16:10:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> Like this 
Code: Select alllocal x = 0.1
x=enableUserInput(true)

thx a lot works like this
---
---
---
local x = 0.1
enableUserInput(true)
showImage("assets/textures/cinematic/intro/page01.tga")
drawElements()
## Post #103
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T16:39:40+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Nope my fail. after

0004    CALL     1   2   2 is
0005    MOV      0   1

```
0002    GGET     1   0      ; "enableUserInput"
0003    KPRI     2   2
0004    CALL     1   2   2
0005    MOV      0   1
0006    GGET     1   1      ; "showImage"
```


original

```
0002    GGET     1   0      ; "enableUserInput"
0003    KPRI     2   2
0004    CALL     1   1   2
0005    GGET     1   1      ; "showImage"
```


here valid 

```
enableUserInput(true)
```


drawElements it's table and begin like

```
some table 1,
some table 2,
some table 3,
})
```
## Post #104
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-23T16:52:05+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> Nope my fail. after...
Code: Select alldrawElements({
some table 1,
some table 2,
some table 3,
})

hehe u scare me xD
that would became my next question because i tried this
drawElements(lj_tab_new{x,0,0})
but it always put out a GGET instead of TNEW

```
0003    KPRI     2   2
0004    CALL     1   1
0005    GGET     1   1
0006    KSTR     2   2
0007    CALL     1   1
0008    GGET     1   3
[b][u]0009    GGET     2   4[/u][/b]
0010    TDUP     3   5
0011    TSETB    0   3
0012    CALL     2   0
0013    CALLM    1   1
0014    RET0     0   1
```


this isnt going to work too
drawElements({lj_tab_new(x,0,0)})
## Post #105
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-23T17:11:38+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

By the way for all other decompiler here is a batch-file to convert the lua to dec(can be opened with all txteditors like notepad++)
by drop the lua file on to it

and a batch to see the bytecode by dropping the dec on the batch - very helpful because u dont have to rename the files like in the tutorial
Cheers!
[luabatch.7z](https://xentaxbackup.github.io/file/5353_luabatch.7z)
## Post #106
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T17:24:10+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

TNEW it's {

```
{some code},
{some code},
{some code},
})
```


I'm stuck here

Original

```
0033    GGET     1  17      ; "fadeIn"
0034    MOV      2   0
0035    CALL     1   1   2
0036    GGET     1  18      ; "click"
0037    CALL     1   1   1
0038    GGET     1  19      ; "fadeOut"
0039    MOV      2   0
0040    CALL     1   1   2
```


My

```
0033    GGET     1  17      ; "fadeIn"
0034    MOV      2   1
0035    CALL     2   1   1
0036    GGET     2  18      ; "click"
0037    CALL     2   1   1
0038    GGET     2  19      ; "fadeOut"
0039    MOV      3   2
0040    CALL     3   1   1
```


dunno why i get

MOV      2   1
CALL     2   1   1

instead of

MOV      2   0
CALL     1   1   2
## Post #107
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-23T18:46:42+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

my idea:
Looks like a functions needs to be closed.
because the first number is higher than the original.
some of your luacode could help. But u know i am a total beginner as well.
## Post #108
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-23T19:38:59+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

can not understand how the code should look like. Get this error

```
stack traceback:
	[string "CinematicMode.lua"]: in function 'fadeIn'
	[string "CinematicMode.lua"]: in main chunk
	[string "CinematicMode.lua"]: in function 'update'
	[string "Grimrock.lua"]: in function 'display'
	[string "Grimrock.lua"]: in main chunk
```


Here unfinished. Maybe someone will do it to finish.
[tutorial.rar](https://xentaxbackup.github.io/file/5358_tutorial.rar)
## Post #109
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-24T13:13:23+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> can not understand how the code should look like. Get this error
Code: Select all[string "CinematicMode.lua"]:0: attempt to compare number with nil
stack traceback:
	[string "CinematicMode.lua"]: in function 'fadeIn'
	[string "CinematicMode.lua"]: in main chunk
	[string "CinematicMode.lua"]: in function 'update'
	[string "Grimrock.lua"]: in function 'display'
	[string "Grimrock.lua"]: in main chunk

Here unfinished. Maybe someone will do it to finish.

Hey dude!
i finished it! nice work of u by the way ^^

cant upload say always the file is empty... so here is the code
[http://www.peoplesliberationfront.net/a ... 4yruHwBMk=](http://www.peoplesliberationfront.net/anonpaste/index.php?30b024e65756719a#z+ZT5/YOqbvv3v+YMZJDt4ZaRZYn2/Eiq+4yruHwBMk=)
## Post #110
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-24T14:24:35+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Thank you for your hard work too! I took the liberty and uploaded it to pastebin.com too, since you can't copy or download from AnonPaste without losing the formatting.
[http://pastebin.com/019t4ysK](http://pastebin.com/019t4ysK)
## Post #111
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-24T15:40:36+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So nice 
[tutorial_decompiled.rar](https://xentaxbackup.github.io/file/5361_tutorial_decompiled.rar)
## Post #112
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-04-24T16:07:31+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

How i can open *.mesh or *.model file format?Game have really interesting content,so i want take it in my collection
## Post #113
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-24T16:34:20+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> So nice
What are the next lua files to edit?
level01.lua to level13.lua
mainmenu.lua
gui_pc.lua
and
settings.lua
could be important

whats your plan ekey?
## Post #114
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-24T16:54:48+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I currently busy my work and no have plans for decompiling other lua's. You can try decompile it alone
## Post #115
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-26T14:21:26+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I would gladly help, but after I watched the tutorial video, it's still not clear for me.
## Post #116
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-26T15:14:52+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

You must be familiar with LUA language
## Post #117
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-04-26T15:31:13+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> You must be familiar with LUA language
Yeah, that's the problem :/
## Post #118
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-26T16:10:23+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So there is no point decompile now. After every patch you need be decompile it again with new code.
For beginners - [http://lua.gts-stolberg.de/en/index.php](http://lua.gts-stolberg.de/en/index.php)
and [http://lua-users.org/wiki/TutorialDirectory](http://lua-users.org/wiki/TutorialDirectory)
## Post #119
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-04-26T16:37:53+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Still don't understand why the hell they hardcoded all texts to game data. Pretty lame.
## Post #120
- Username: sch0t3
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Apr 22, 2012 12:04 am
- Post datetime: 2012-04-26T16:41:24+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Maybe they didnt fought it would be a success?!   
I think they just wanted to finish it nothing more... I do this too when I have to hurry with my webdesign
## Post #121
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-26T16:45:33+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from XRaptor
>
> Still don't understand why the hell they hardcoded all texts to game data. Pretty lame.
Yep you right. Could make one single file with all texts. Maybe they will do so.

btw: SaveGame.lua very interesting script. Respon for loading and saving game data 
btw2: [http://www.grimrock.net/2011/09/09/buil ... on-part-ii](http://www.grimrock.net/2011/09/09/building-the-dungeon-part-ii) ([http://www.grimrock.net/wp-content/uplo ... 7/code.jpg](http://www.grimrock.net/wp-content/uploads/2011/07/code.jpg))
btw3: For translaters - ScrambleWriter.lua respon characters font.

```
0001    GGET     0   0      ; "ScrambleWriter"
0002    TGETS    0   0   1  ; "__init"
0003    CALL     0   2   1
0004    KSTR     1   3      ; " ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789.,!?+-:;()'""
0005    TSETS    1   0   2  ; "glyphs"
0006    TNEW     1   0
0007    TSETS    1   0   4  ; "targetText"
0008    TNEW     1   0
0009    TSETS    1   0   5  ; "currentText"
0010    MOV      2   0
0011    TGETS    1   0   6  ; "setText"
0012    KSTR     3   7      ; ""
0013    CALL     1   1   3
0014    GGET     1   9      ; "FontType"
0015    TGETS    1   1  10  ; "Dream"
0016    TSETS    1   0   8  ; "font"
```
## Post #122
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-08T07:40:21+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Just a question - is someone trying to find out last missing filenames?  I tried everything but nothing new
## Post #123
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2012-05-08T10:46:17+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Yes. I always play the game with unpacked files for getting error for missing files. But, I've found nothing...
## Post #124
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-08T11:07:33+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So it's a unused in game files or from demo version with prefix _demo or something like that
## Post #125
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-08T11:14:27+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Now I'm missing only 46 files, all other files are known 

There is nothing from demo, because there is no demo
## Post #126
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-08T11:50:32+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

[http://www.gamershell.com/download_85422.shtml](http://www.gamershell.com/download_85422.shtml)

PS: X write bruteforcer
## Post #127
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-08T13:13:14+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

It is not demo, just some old beta 

heh, I did, but it is usefull only for short texts. I used it for getting some unknown suffixes like text_01 etc. But some filenames are more then 10 chars long and it is pain to guess.
## Post #128
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-08T14:04:30+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Well, if you want, here is actual filelist. And as I said, only 46 files is missing.


 hashtable.rar
(45.5 KiB) Downloaded 25 times
## Post #129
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-08T15:10:29+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Thanks X
## Post #130
- Username: montagneyaya
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 09, 2012 4:42 am
- Post datetime: 2012-05-12T22:51:58+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Hello,
I have question (maybe stupid).

I have the steam version of Legend of Grimrock
If I extract the .dat file in the game folder normally i can delete the .dat file, but if I delete the .dat file the game doesn't start.
And if I keep the .dat file, I think it will override the extract file.
What should I do ?

Sorry for my bad english.
## Post #131
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-12T23:55:46+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

All modified files you need pack back (use Patch button)
## Post #132
- Username: montagneyaya
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 09, 2012 4:42 am
- Post datetime: 2012-05-13T01:35:01+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

OK, thanks.
## Post #133
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-16T09:20:58+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

LOL, I just found (eh brute force) one filename

```
CB8D7982  assets/models/wall_sets/prison/door_cxl2i9b.mesh

```

How the hell should I guess this one?  Looks like another temporary file.
## Post #134
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-16T11:02:31+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

oh lol great 44 left  ?
## Post #135
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-16T18:25:36+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Ekey
>
> oh lol great 44 left  ?
41 left. Still trying to bruteforce names
## Post #136
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-16T19:22:21+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

huh share bruteforcer
## Post #137
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-17T08:18:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

7 files left
## Post #138
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-17T12:40:06+00:00
- Post Title: Re: Legend of Grimlock [.dat file]


## Post #139
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-17T16:34:29+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So, here it is  All filenames decrypted. 
Thanx all for help and shame on devs for including so many temporary and unused files in final product 

Simply redownload last version. Everything is done and ready for next patch 

Legend of Grimrock DAT File Extractor
[http://raptor.cestiny.cz/download/legen ... actor.html](http://raptor.cestiny.cz/download/legend-of-grimrock-dat-file-extractor.html)
## Post #140
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-17T16:42:03+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

So good job.
## Post #141
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-23T09:40:40+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Anyone have some spare time to reverse the remaining .lua files?    It doesn't seem a new patch will come anytime soon, and the lua files here work with the first patch, so I think they'll work with the new ones too.
## Post #142
- Username: marcosjvc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 24, 2012 8:40 am
- Post datetime: 2012-05-24T00:53:49+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from lostprophet
>
> Anyone have some spare time to reverse the remaining .lua files?    It doesn't seem a new patch will come anytime soon, and the lua files here work with the first patch, so I think they'll work with the new ones too.

I think I have some spare time... the thing is, I don't have enough practice with Lua, and the video links provided by Ekey are dead.
## Post #143
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-05-24T08:07:07+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from marcosjvc
>
> lostprophet wrote:Anyone have some spare time to reverse the remaining .lua files?    It doesn't seem a new patch will come anytime soon, and the lua files here work with the first patch, so I think they'll work with the new ones too.

I think I have some spare time... the thing is, I don't have enough practice with Lua, and the video links provided by Ekey are dead.
Well, if you're still interested, I bought the game on Steam, and can send you the remaining lua files. Or anyone for that matter.
## Post #144
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-05-24T11:44:19+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

What is the hash method they use?
## Post #145
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-24T11:50:26+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Mr.Mouse
>
> What is the hash method they use?

32bit FNV-1a
## Post #146
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-24T12:53:37+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Simple code 

```
const
  c_b = $811C9DC5;
  c_n = $01000193;
var
  I, N:Integer;
  Next:LongWord;
begin
  Result := c_b;
  N := StrLen(Values);
for I := 0 to N - 1 do
begin
  Next := Byte(Values[I]);
  Result := Result xor Next;
  Result := Result * c_n;
 end;
end;
```
## Post #147
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-05-24T14:25:48+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Or  

```
var
    i: Integer;
const
    FNV_offset_basis = 2166136261;
    FNV_prime = 16777619;
begin
    //FNV-1a hash
    Result := FNV_offset_basis;
    for i := 1 to Length(s) do
        Result := (Result xor Byte(s[i])) * FNV_prime;
end;
```
## Post #148
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-05-24T14:29:47+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

ok, and now pure ASM code, pls
## Post #149
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-05-24T17:43:55+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

C# will suit  ?
## Post #150
- Username: marcosjvc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 24, 2012 8:40 am
- Post datetime: 2012-05-29T04:13:26+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from lostprophet
>
> marcosjvc wrote:lostprophet wrote:Anyone have some spare time to reverse the remaining .lua files?    It doesn't seem a new patch will come anytime soon, and the lua files here work with the first patch, so I think they'll work with the new ones too.

I think I have some spare time... the thing is, I don't have enough practice with Lua, and the video links provided by Ekey are dead.
Well, if you're still interested, I bought the game on Steam, and can send you the remaining lua files. Or anyone for that matter.

I bought it too
## Post #151
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-09T22:39:44+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Any news, any hope on the missing .lua files to be reversed?  (Hopefully) No one will answer, because everyone's on the beach by now
## Post #152
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-07-15T17:32:10+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Someone can explain how to decompiling ?

I use luajit to get a bytecode file it's ok but after ? How to get a editable *.lua with it.

Video posted by Ekey not work anymore 

Thanks.
## Post #153
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-07-23T14:20:17+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

No one knows ?
## Post #154
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-07-23T15:02:13+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Smash15195
>
> No one knows ?
I still have the tutorial video, I can upload it today
## Post #155
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-07-23T18:01:26+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

pls thanks

Do you have the decompiled *.lua ?
## Post #156
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-23T20:17:24+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from Smash15195
>
> pls thanks

Do you have the decompiled *.lua ?
It is better to wait for the official release Level Editor with Lua API.
## Post #157
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-07-23T22:02:09+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

you think we can translate the game with it ?
## Post #158
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-24T06:21:58+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Maybe
## Post #159
- Username: KDraka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 23, 2012 1:33 pm
- Post datetime: 2012-07-25T18:42:54+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from lostprophet
>
> Smash15195 wrote:No one knows ?
I still have the tutorial video, I can upload it today

Thank you. I'm waiting for you. I really want to translate this game.
## Post #160
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-07-26T03:51:01+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

> Reply from KDraka
>
> lostprophet wrote:Smash15195 wrote:No one knows ?
I still have the tutorial video, I can upload it today 

Thank you. I'm waiting for you. I really want to translate this game.
Yeah, my bad, here you go, sorry for the delay  

```
http://www20.zippyshare.com/v/34753967/file.html
```
## Post #161
- Username: Smash15195
- Rank: beginner
- Number of posts: 24
- Joined date: Fri Apr 08, 2011 4:35 am
- Post datetime: 2012-07-26T12:45:51+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

i gonna watch that, thx.
## Post #162
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-21T10:20:37+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Does anyone know what this is converted back to luajit?

```
0001    GGET     2   0      ; "Managers"
0002    TGETS    2   2   1  ; "perfhud"
0003    MOV      3   2
0004    TGETS    2   2   2  ; "update"
0005    MOV      4   1
0006    CALL     2   1   3
0007    GGET     2   3      ; "Boot"
0008    MOV      3   2
0009    TGETS    2   2   4  ; "foundation_update"
0010    MOV      4   1
0011    CALL     2   1   3
0012    GGET     2   0      ; "Managers"
0013    TGETS    2   2   5  ; "transition"
0014    MOV      3   2
0015    TGETS    2   2   2  ; "update"
0016    MOV      4   1
0017    CALL     2   1   3
0018    GGET     2   0      ; "Managers"
0019    TGETS    2   2   6  ; "changelog"
0020    MOV      3   2
0021    TGETS    2   2   2  ; "update"
0022    MOV      4   1
0023    CALL     2   1   3
0024    RET0     0   1

```


The closest I can get for the first part is 

```
Managers.perfhud:update()
```


which translates to:

```
0002    TGETS    0   0   1  ; "perfhud"
0003    MOV      1   0
0004    TGETS    0   0   2  ; "update"
0005    CALL     0   1   2
0006    RET0     0   1

```


which is missing a MOV.
## Post #163
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T13:59:32+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Byte Code MOV added after you write next code which begins command Boot

```
Boot bla bla bla
```
## Post #164
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-21T15:38:58+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Still missing a MOV 

```
0002    TGETS    0   0   1  ; "perfhud"
0003    MOV      1   0
0004    TGETS    0   0   2  ; "update"
0005    CALL     0   1   2
0006    GGET     0   3      ; "Boot"
0007    TGETS    0   0   4  ; "foundation_update"
0008    CALL     0   1   1
0009    RET0     0   1

```


also the bytecode values appear to be very different eg 

Original:

0001    GGET     2   0      ; "Managers"
0002    TGETS    2   2   1  ; "perfhud"

New:

0001    GGET     0   0      ; "Managers"
0002    TGETS    0   0   1  ; "perfhud"
## Post #165
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-21T15:52:07+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Obviously invalid decompiled code. Anyway i decompiling only basic scripts and can't help u.
## Post #166
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-08-22T14:21:28+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Turned out a single MOV is getting a previous local but now I'm a stuck on another part, I know you said you've only done simple scripts but any idea about how to solve this?


Original:

0001    TGETS    1   0   0  ; "_hud_debuff_blackboard"
0002    TGETS    2   1   1  ; "wounded"
0003    GGET     3   3      ; "GameSession"
0004    TGETS    3   3   4  ; "game_object_field"

My code

0001    TGETS    1   0   0  ; "_hud_debuff_blackboard"
0002    TGETS    2   1   1  ; "wounded"
0003    GGET     3   2      ; "GameSession"
0004    TGETS    3   3   3  ; "game_object_field"

As far as I can tell the values in blue refer to the table index, mine seems to be 1 less which would suggest something gets added to the table inbetween 'TGETS' and 'GGET 'that doesn't get compiled (at least not as its own opcode). my initial thought is something to do with a local (as they dont get compiled as an opcode) but creating a new one and initializing it always adds an extra move/call.

Edit:

So after some investigation and a chat with the luajit guy I worked it out. Heres the code in case anyone is interested:

bytecode

```
0002    TGETS    2   1   1  ; "wounded"
0003    GGET     3   3      ; "GameSession"
0004    TGETS    3   3   4  ; "game_object_field"
0005    TGETS    4   0   5  ; "_game"
0006    TGETS    5   0   6  ; "_game_object_id"
0007    KSTR     6   1      ; "wounded"
0008    CALL     3   2   4
0009    ISF          3
0010    JMP      4 => 0013
0011    KSHORT   3   1
0012    JMP      4 => 0014
0013 => KSHORT   3   0
0014 => TSETS    3   2   2  ; "level"
```


decompiled

```
local a = arg1._hud_debuff_blackboard
local b = a.wounded
b.level = GameSession.game_object_field(arg1._game,arg1._game_object_id,"wounded") and 1 or 0
....more code
End

```
## Post #167
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2012-10-15T18:38:35+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Ok, because developers decided there are many modders with unofficial tool, they changed DAT file format and encrypted LUA scripts. But no problem, simply use new version of my tool. For old archives use old one.

Legend of Grimrock DAT File Extractor
[http://raptor.cestiny.cz/download/legen ... actor.html](http://raptor.cestiny.cz/download/legend-of-grimrock-dat-file-extractor.html)

7 hashes are unknown for me now, but maybe they are not important
## Post #168
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T12:20:51+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Brute-force
## Post #169
- Username: Moo
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jul 25, 2012 7:04 am
- Post datetime: 2014-08-21T16:01:05+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

Some more:

```
B1511EAA:assets/cinematics/tutorial.lua
5C030F45:assets/dungeons/menu/dungeon.lua
77AA26B1:assets/shaders/d3d9/crystal_ps_main.d3d9_shader
36A3978F:assets/shaders/d3d9/crystal_ps_main_alpha_test.d3d9_shader
904775CA:assets/shaders/d3d9/crystal_unlit_ps_main.d3d9_shader
41DE517A:assets/shaders/d3d9/crystal_unlit_ps_main_alpha_test.d3d9_shader
2CBFAEB7:assets/shaders/d3d9/crystal_vs_main.d3d9_shader
B5DB8356:assets/shaders/d3d9/crystal_vs_main_normal_map.d3d9_shader
87224DE0:assets/shaders/d3d9/crystal_vs_main_normal_map_skinning.d3d9_shader
6FA75953:assets/shaders/d3d9/crystal_vs_main_skinning.d3d9_shader
C5CAA818:assets/shaders/d3d9/dream_main_ps.d3d9_shader
53D7888E:assets/shaders/d3d9/dream_main_vs.d3d9_shader
04B11187:assets/textures/portraits/dead.tga
8F97B1E6:assets/textures/portraits/empty.tga
3BE16F47:assets/textures/portraits/human_female_01.tga
454DB4B2:assets/textures/portraits/human_female_02.tga
04E30F48:assets/textures/portraits/human_male_01.tga
403E1131:assets/textures/portraits/human_male_02.tga
9C876A12:assets/textures/portraits/human_male_03.tga
C00E2E4B:assets/textures/portraits/human_male_04.tga
67061E0C:assets/textures/portraits/human_male_05.tga
A9C17616:assets/textures/portraits/insectoid_female_01.tga
C8A6E67B:assets/textures/portraits/insectoid_female_02.tga
EB6604D5:assets/textures/portraits/insectoid_male_01.tga
099FD16C:assets/textures/portraits/insectoid_male_02.tga
355BBDA6:assets/textures/portraits/lizardman_female_01.tga
6A1CA1E5:assets/textures/portraits/lizardman_male_01.tga
C8F4A3FC:assets/textures/portraits/lizardman_male_02.tga
2104B83B:assets/textures/portraits/lizardman_male_03.tga
432C0EC9:assets/textures/portraits/minotaur_female_01.tga
F6627ED6:assets/textures/portraits/minotaur_male_01.tga
17C2583B:assets/textures/portraits/minotaur_male_02.tga
BFB243FC:assets/textures/portraits/minotaur_male_03.tga
21ACA7CF:assets/textures/portraits/toorum.tga
28BA5F8F:shaders/d3d9/mesh_geometry_main.d3d9_shader
06B65D05:shaders/d3d9/mesh_geometry_main_alpha_test.d3d9_shader
FC898FEE:shaders/d3d9/mesh_geometry_main_normal_map.d3d9_shader
14157E26:shaders/d3d9/mesh_geometry_main_normal_map_alpha_test.d3d9_shader
3B6FDF3C:shaders/d3d9/mesh_main.d3d9_shader
FF62DAC3:shaders/d3d9/mesh_main_normal_map.d3d9_shader
F950467F:shaders/d3d9/mesh_main_normal_map_skinning.d3d9_shader
D6B5DFBE:shaders/d3d9/mesh_main_skinning.d3d9_shader
D2AF95C4:shaders/d3d9/mesh_material_main.d3d9_shader
A90834E4:shaders/d3d9/mesh_material_main_alpha_test.d3d9_shader
7497C0A4:shaders/d3d9/mesh_notebook_main.d3d9_shader
0492E76B:shaders/d3d9/mesh_notebook_main_normal_map.d3d9_shader
1B6704C7:shaders/d3d9/mesh_notebook_main_normal_map_skinning.d3d9_shader
393B4C26:shaders/d3d9/mesh_notebook_main_skinning.d3d9_shader
2407EF0A:shaders/d3d9/mesh_notebook_opaque_main.d3d9_shader
87C54A51:shaders/d3d9/mesh_notebook_opaque_main_normal_map.d3d9_shader
280EE865:shaders/d3d9/mesh_notebook_unlit_main.d3d9_shader
496A2D3A:shaders/d3d9/mesh_shadow_shadow_dirlight_ps.d3d9_shader
8AC00ECA:shaders/d3d9/mesh_shadow_shadow_dirlight_ps_alpha_test.d3d9_shader
5925E052:shaders/d3d9/mesh_shadow_shadow_ps.d3d9_shader
D9810532:shaders/d3d9/mesh_shadow_shadow_ps_alpha_test.d3d9_shader
9A2806E4:shaders/d3d9/mesh_shadow_shadow_vs.d3d9_shader
8C8A0F66:shaders/d3d9/mesh_shadow_shadow_vs_skinning.d3d9_shader
1670831D:shaders/d3d9/mesh_unlit_main.d3d9_shader
08E01943:shaders/d3d9/mesh_unlit_main_alpha_test.d3d9_shader

```


Brute force isn't such a good idea, as with such a simple hash function, false positives are too easy to get. Things like "shaders/d3d9/ssao__yfhv9.d3d9_shader" are examples of that, if you ask me.
## Post #170
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2015-01-24T21:08:12+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

First post in this year and the most repeated question iiis:

It's currently possible to translate this damn game?
## Post #171
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-01-24T22:06:54+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

It is. You "just" have to recreate .lua files from their bytecode form. For example, guys from ZoG made [unofficial russian translation](http://www.zoneofgames.ru/games/legend_of_grimrock/files/4930.html).
## Post #172
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2015-01-24T22:16:44+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I already know this decompile technique from this thread.
Maybe my question was out of precession. What I actually mean was
is there are a better solution like these method to edit the localization scripts
of LoG. Another question could be is there are a way to use extern files like
S.T.A.L.K.E.R. with the /gamedata DIR?
## Post #173
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-01-24T22:38:21+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

I suppose there is no another way, because they are working on LoG2 with this long and boring method.
## Post #174
- Username: HijackTheRipper
- Rank: beginner
- Number of posts: 27
- Joined date: Fri Aug 29, 2014 9:28 pm
- Post datetime: 2015-01-26T18:41:57+00:00
- Post Title: Re: Legend of Grimlock [.dat file]

really? jesus christ...

edit: byte2lua converter on my to do list
