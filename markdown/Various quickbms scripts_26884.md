## Post #1
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-20T16:30:33+00:00
- Post Title: Various quickbms scripts

Since zenhax is now out of service (probably permanently), here is copy of my scripts which are not present in other places. Unreal engine related scripts are still available and supported at [rin forum](https://cs.rin.ru/forum/viewtopic.php?f=10&t=100672) (as well as mirror for scripts and pack listed below).

Various scripts pack: [download](https://drive.google.com/file/d/1GNZ_u-IcFfYhN9FSRU3kc09e0X-TB-e7/view?usp=sharing) (updated)
AssetStudio pack: [download](https://drive.google.com/file/d/1M6z7loFZEKeqbHOISniatI_hR3LUR6mE/view?usp=sharing) (updated)

Notice: All scripts are provided as-is, they may be outdated and doesn't work with current game versions. Also support for them is limited to particular games. Other scripts and tools should be available in respective topics at xentax - but if something is missing, please let me know.

Supported games (in alphabetical order):
Babylon's Fall - extracting pkz, dtt, dat files
Bleach Brave Souls - decrypting pb, byte files
Borderlands 2 - extracting textures from HD textures pack
Brave's Rage - decrypting assets
Bus Derby - extracting textures from dti files
Calabiyau - decrypting lua files
Cat up a tree - extracting vna files
Closers RT - decrypting bmf, tbd, ttr, scn, spd files
Coropata - extracting pac files
Diabotical - extracting dbp files
Digimon ReArise - decrypting assets
DIRT 5 - extracting ndx/dat files
DRAG - extracting data/0x files
Dragon Quest Rivals - decrypting assets and fix textures
Dragon Quest XI (including S) - all-in-one-pack
Dune Spice Wars - extracting pak files
Engage Kill - decrypting assets
Evangelion Slide Puzzle - extracting dat files
Fuser - extracting mogg files from uexp
Gamota (various games) - extracting pak files
Gears 5 - test scripts for extracting b2container files
Giana Sisters - converting pak to sbpack
Girls Punzer - decrypting assets
Goddess Destiny - decrypting png files
Gundam Senki - extracting bfpk files
Inspector Waffles - decrypting/encrypting particular files
Invizimals Battle Hunters - extracting obb files (npakdata)
Kingdoms Reborn - extracting audio from paka files
Lego Star Wars The Skywalker Saga - extracting dat files, converting texture and nxg_textures files
Life is Strange 2 - decrypting saves
Lost Ark (including LAUTool) - extracting lpk files, decrypting bnk/wem files
M.A.R.S - decrypting upk files
Metroid Dread - extracting pkg files, extracting bctex textures
My Hero Academia The Strongest Hero - extracting various file types
My Hero Ultra Impact - decrypting assets
NEO The World Ends with You - decrypting assets
Netease (Messiah engine) (including Diablo Immortal) - extracting mpk files, converting textures
Ni no Kuni remastered - extracting mnupak 
Omega Labyrinth Life - decrypting svd files
One Piece Burning Will (better to use respective AssetStudio) - decrypting assets
Panilla Saga - decrypting png files
Project W - merging lbres into proper packages (for old versions)
Rainbow Six Mobile - converting textures from Texture2DArray
Rockman X Dive (Mega Man X Dive / Offline) - decrypting assets and textdata
Sailing Era - decrypting assets
Singularity - extracting raw HD textures from tfc file
Super Robot Wars 30 - decrypting cpk
Super Smash Bros Crusade - extracting pak files
Tekken 7 - extracting some mods
Tokyo Necro - extracting npk files 
Tour de France 2022 - extracting pkg files
True Crime - extracting textures from tag files
Utawarerumono Lost Flag - decrypting assets
Wargroove 2 - extracting dat files

-------------------------------------------------------

Additional notes: Netease (Messiah engine) texture script currently supports compressed (ZZZ4, LZMA) and uncompressed textures of the following formats - WEBP, RGBA, DXT1/5, BC7, ASTC 4x4/5x5/6x6/8x8/8x6/10x10/12x12, ETC1, ETC2 RGBA. For most output formats you need to use PVRTexTool.

Credits to aluigi for some base scripts (some of them are just fixes for existing scripts) and to Ekey for original LAUTool.
## Post #2
- Username: BearKuku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2023 9:44 am
- Post datetime: 2023-06-21T01:48:02+00:00
- Post Title: Various quickbms scripts

thank you very very much.
I had one question with Lost Ark in steam
when I used BMS to unpack the game file data2.lpk, I obtained EFTable_GameMsg.db. However, when I tried to open the file with DB Browser and SQLiteStudio, there was no data displayed. Is there any way to open this file correctly? Thank you very much.
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-21T12:56:24+00:00
- Post Title: Various quickbms scripts

@BearKuku: The game is using custom database format. I don't know if there is a solution for it available somewhere.
## Post #4
- Username: BearKuku
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2023 9:44 am
- Post datetime: 2023-06-21T15:42:29+00:00
- Post Title: Various quickbms scripts

@Spiritovod
Ok, thank you very much
## Post #5
- Username: Rinorsi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 03, 2023 4:53 pm
- Post datetime: 2023-08-03T09:07:52+00:00
- Post Title: Various quickbms scripts

Hello,when I used script to messiah engine game(Ace Racer,mpk files),I got so many files so I dont to know how to find texture or sprite(I only used assetstudio so I dont know how to use).
it had many folder and most file types do not have suffixes,A small portion of the suffix names are ".4"
I have been searching for methods for a long time, but they have not yielded any results.
Can you help me extract the image resources in the game? I want to know the method of unpacking,Thank you very much if possible!!!
（my Engish is not good,im Chinese）
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-08-03T20:17:12+00:00
- Post Title: Various quickbms scripts

@Rinorsi: You can run texture script from the same folder on extracted files to convert textures if they're present. Though some false positive results are possible and the game may use unsupported texture formats (currently supported formats are listed in additional notice at the bottom of the first post).
## Post #7
- Username: Rinorsi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 03, 2023 4:53 pm
- Post datetime: 2023-08-05T10:44:00+00:00
- Post Title: Various quickbms scripts

I used a exture_convert_v4.bms script, but it didn't have any effect.
( signature of 3 bytes at offset 0x0000000000000000 doesn't match the one)


This is game :[http://racerna.onelink.me/w15e/bkbdw92q](http://racerna.onelink.me/w15e/bkbdw92q)
could you help me pls?
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-08-05T17:47:19+00:00
- Post Title: Various quickbms scripts

@Rinorsi: I've updated texture script, it now supports additional formats used by the game. But like it was said above, it would be better to use script on the whole extracted folder, output will be only compatible textures. You can read how such things can be done in gui/cli modes from official [quickbms documentation](https://aluigi.altervista.org/papers/quickbms.txt) ("usage" section).
## Post #9
- Username: Rinorsi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 03, 2023 4:53 pm
- Post datetime: 2023-08-05T19:05:32+00:00
- Post Title: Various quickbms scripts

The new script is working, thank you very much!!!Thanks♪(･ω･)ﾉ
## Post #10
- Username: chloesmiles514
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 04, 2023 6:35 am
- Post datetime: 2023-10-03T22:43:46+00:00
- Post Title: Various quickbms scripts

I tried decrypting the pb files for Bleach Brave Souls with your script, but it didn't seem to fully decrypt everything. I was able to decrypt the models but that's mostly it. I have the most recent version of this mobile game as of 10/3/2023.

An example would be the directory "com.klab.bleach/files/files/rmfs/Characters". Is there perhaps a different key for these pb files?

Edit: I tried the same game file path (BLEACH Brave Souls/home/persistent/files/rmfs/Characters) for the Steam PC version in case this script was for the PC version specifically but got the same result.
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-04T11:33:18+00:00
- Post Title: Various quickbms scripts

@chloesmiles514: I checked latest steam version and script still works fine with respective files. You're probably confused because of extension, but most pb files are png. I've updated script in the archive, output format for those files should be more clear now.
## Post #12
- Username: chloesmiles514
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 04, 2023 6:35 am
- Post datetime: 2023-10-04T15:04:02+00:00
- Post Title: Various quickbms scripts

> Reply from Spiritovod ↑Wed Oct 04, 2023 7:33 pm at Wed Oct 04, 2023 7:33 pm
>
> 
@chloesmiles514: I checked latest steam version and script still works fine with respective files. You're probably confused because of extension, but most pb files are png. I've updated script in the archive, output format for those files should be more clear now.

Thank you, I was just about to edit my previous message after I found out that the pb files had the PNG header. Sorry for the bother
## Post #13
- Username: Ozen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 10, 2023 8:45 pm
- Post datetime: 2023-10-10T12:48:39+00:00
- Post Title: Various quickbms scripts

I am trying to decrypt Lost ark wem and bnk files, but when i drag them on the LAU steam tool, nothing happens
## Post #14
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-10T18:02:14+00:00
- Post Title: Various quickbms scripts

@Ozen: It's a command line tool, which requires some parameters to work. You can run it without any parameters to see usage examples.
## Post #15
- Username: lightning2022
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 06, 2022 3:15 pm
- Post datetime: 2023-10-17T07:42:00+00:00
- Post Title: Various quickbms scripts

First of all thank you for the various scripts;
I just wanted to ask you if these scripts or another one would be useful with "Captain Tsubasa: Dream team" that was developed by Klab as I believe that it might have the same structure and encryption of Bleach as they were developed by the same company. Thus, if you could help me with decrypting even the assets only i would be so grateful
## Post #16
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-17T12:55:11+00:00
- Post Title: Re: Various quickbms scripts

@lightning2022: This is different game with most likely different encryption, even if it's from the same developer. I have no plans to look into it.
