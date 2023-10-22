## Post #1
- Username: Evil Finalist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 14, 2014 7:17 am
- Post datetime: 2017-11-30T17:50:47+00:00
- Post Title: Tales Of Series: Collection of Tools

Hi there, everyone.
I am founder of Russian Tales of fan website called "Temple of Tales" ([https://www.temple-tales.ru](https://www.temple-tales.ru)).
Since 2014 I have changed the focus of website, and now you can see us mentioned as "Temple of Tales Translations".
We'd begun to specialise in Tales of games translations to Russian.
In the past few years we've gathered many works (texts, textures, etc.), and the vast majority of it helped us to fully
translate some games and port several translations. We've taken almost every major title in the series:
(  ) Tales of Phantasia (PS1)
(  ) Tales of Eternia (PS1)
(+) Tales of Destiny Director's Cut (PS2)
(  ) Tales of Destiny 2 (PS2)
(  ) Tales of Symphonia (PS3, PC)
(  ) Tales of Symphonia: Dawn of the New World (PS3)
(  ) Tales Of Rebirth (PS2)
(  ) Tales of the Abyss (PS2)
(+) Tales of Vesperia (PS3, X360)
(  ) Tales of Graces f (PS3)
(  ) Tales of Xillia (PS3)
(  ) Tales of Xillia 2 (PS3)
(  ) Tales of Zestiria (PS3, PC)
(+) Tales of Berseria (PS3, PC)

You can check out progresses of translations here: http://temple-tales.ru/translations.html

I have recieved many messages via email asking to help with different "Tales of" translations, as well as to share the software.
I was suprised to see that people who asked me were from different countries. And in the end I've decided to openly publish everything.
I'm sure it'll help many to start and complete their projects, or maybe just have fun looking through the resources.
Of course, I will not upload everything at once. I'll upload things bit by bit, as our own projects progress.

Also I sincerely hope there will be other people, not only me, who'd like to share their own software.
I'm asking for your assistance at gathering the full collection of software capable of hacking "Tales of" games.
---------------------------------------------------------------------------------------------------------------------
List of tools that are placed in this topic:
(1) Tales of Berseria Tools                     | Platforms: PC, PS3
(2) Swizzling Tool                                  | Platforms: PS3
(3) Tales of Vesperia Tools                     | Platforms: Xbox 360, PS3
(4) Tales of Destiny Director's Cut Tools | Platforms: PS2
---------------------------------------------------------------------------------------------------------------------
(1) Tales of Berseria Tools
Platforms: PC, PS3
http://temple-tales.ru/translations/too ... gerRus.rar
decrypt:
    Decrypt TLFILE.TLDAT file of PC version (must have FILEHEADER.TOFHDB FILEHEADER.TOFHDA in order to decrypt).

unpack/patch:
    Unpacking and packing TLFILE.TLDAT FILEHEADER.TOFHDB (compatible with PC & PS3 versions, in addition automatically
	changes format of textures to *.DDS during unpacking).

unsdb/sdb [0/1] [ansi/utf8]:
    Text dumper to extract/insert the script from the *.SDB files (works with all types of SDB, also compatible with
	PC & PS3 versions). Commands "0/1" allow you to adjust the process of tag break (tags are placed before the text),
	and these commands allow you to adjust text extraction in proper encoding "ansi/utf8".

 Attention! Please read this before using this programm!
a) Patch - to pack files in TLFILE correctly you must place new files in folder called "TLFILE_FILES".
   During packing process the programm would automatically check every file located in "TLFILE_FILES" folder.
   Do not place subdirectories with new files into "TLFILE_FILES" folder, because this utility works directly with
   files located in "TLFILE_FILES" folder.
b) After activating "patch" command there will be no new TLFILE archive. It'll be instantly made into TLFILE
   which is specified in command line or in executive BAT file. I highly advice you to make a backup copy of original TLFILE.
c) While packing TLFILE programm would understand only original names of unpacked files. Don't change them.
d) In case you'd like to change the text inside SDB using packing command "sdb",
   SDB and TXT files should be located in the same directory (folder).
e) While packing SDB programm would understand only original structure of TXT files. That means you cannot change
   neither tags nor number of lines.
---------------------------------------------------------------------------------------------------------------------
(2) Swizzling Tool
Platforms: PS3
http://temple-tales.ru/translations/too ... gerRus.rar
Swizzling Tool is a swizzling and deswizzling textures of DDS formats for Tales of Vesperia, Tales of Xillia,
Tales of Xillia 2, Tales of Zestiria & Tales of Berseria. It can be used for modding the textures.
Compatible only with PS3 version. 
unswiz/swiz:
    Swizzling and deswizzling textures of DDS formats.
---------------------------------------------------------------------------------------------------------------------
(3) Tales of Vesperia Tools
Platforms: Xbox 360, PS3
http://temple-tales.ru/translations/too ... gerRus.rar
unfps/fps:
    unpacking and packing containers of FPS4 format, mostly for SVO files.

uncht/cht/cht_switch:
    text dumper to extract/insert the script from the *.TO8CHTX files.
    command "cht_switch" during insert allows you to switch EN and JP lines.
    commands "ansi/utf8" allow you to adjust text extraction in proper encoding.

untss/tss/tss_switch:
    Ttext dumper to extract/insert the script from the *.TO8SCEL and *.TSS files (scenario.dat & STRING_DIC.SO).
    command "cht_switch" during insert allows you to switch EN and JP lines.
    commands "ansi/utf8" allow you to adjust text extraction in proper encoding.

untss2/tss2:
    command "untss2" extracts all resources from scenario.dat (file format: bin).
    command "tss2" inserts previously extracted resources back into scenario.dat (формат bin).

unscf/scf/scf_switch:
    text dumper to extract/insert the script from the *.cmp files (SCFOMBIN).
    This type of file contains text displayed during battles.
    There are 26 files that you need to edit. All of them are listed below (readme.txt).
    Example: btl.svo\BTL_PACK\BTL_PACK_003\BTL_EP_0070_010_154.cmp

 Attention! Please read this before using this programm!
a) Patch - to pack files correctly you must keep structure of unpacked files' location. In case there are some
   subdirectories, you must leave them as they are, otherwise files won't get updated after packing.
b) After activating commands that patch/pack files there will be no new archive created. It'll be instantly made
   into file which is specified in command line or in executive BAT file. I highly advice you to make a backup
   copy of original file.
c) While packing files programm would understand only original names of unpacked files. Don't change them.
d) In case you'd like to change the text inside TO8CHTX, TO8SCEL or SCFOMBIN using packing commands
   "cht, tss or scf", game files and TXT files should be located in the same directory (folder).
e) While packing TO8CHTX, TO8SCEL or SCFOMBIN programm would understand only original structure of TXT files.
   That means you cannot change neither tags nor number of lines.
f) There are two more files attached to the tools:
   JPCODES (for TO8CHTX).txt
   JPCODES (for TO8SCEL & TSS).txt
   Those files help to replace certain values and tags.
   You can always add more value replacements and adjust them as you'd like.
   Order structure in JPCODES:
   [value1]; [value2]; comments
   "value1" will be replaced with "value2" in file you're patching after running. 
   These files work along with "cht, tss or scf" commands. While running JPCODES.txt should be located in the same
   directory with utility. This tool can only have one name - JPCODES.txt. Don't change it - tool set won't
   recognise other names.
---------------------------------------------------------------------------------------------------------------------
(4) Tales of Destiny Director's Cut Tools
Platforms: PS2
http://temple-tales.ru/translations/too ... gerRus.rar
unpack/pack BIN:
    unpacking and packing main archives BIN.

unmglk/mglk MGLK:
    unpacking and packing containers of MGLK format.

 Attention! Please read this before using this programm!
a) After activating command that "pack" files there will be new archive created (only for BIN).
b) After activating "mglk" command there will be no new MGLK archive. It'll be instantly made into MGLK
   which is specified in command line or in executive BAT file. I highly advice you to make a backup copy of
   original MGLK.
c) While packing BIN or MGLK programm would understand only original names of unpacked files.
   Don't change them.
d) Pack - to pack files in BIN correctly you must place new files in folder called "NAME_FILES".
   During packing the programm would automatically check every file located in "NAME_FILES" folder.
   Do not place subdirectories with new files into "NAME_FILES" folder, because this utility works directly
   with files located in "NAME_FILES" folder. "NAME" is an archive of the same name with the file
   you'd like to patch (DAT.BIN or MOV.BIN). For example, if you'd like to pack files into DAT.BIN,
   then you should name your folder "DAT_FILES".
e) MGLK - to pack files in MGLK correctly you must place new files in folder called "NAME".
   During packing the programm would automatically check every file located in "NAME" folder.
   Do not place subdirectories with new files into "NAME" folder, because this utility works directly
   with files located in "NAME" folder. "NAME" - is an archive of the same name with the file
   you'd like to patch (13558.mglk & etc). For example, if you'd like to pack files into 13559.mglk,
   then you should name your folder '13559'.
---------------------------------------------------------------------------------------------------------------------
.
.
## Post #2
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2017-12-01T07:28:14+00:00
- Post Title: Tales Of Series: Collection of Tools

Thank you very much. We are going to make a Vietnamese fan translation and your tool solved all the problem we had encountered before.
## Post #3
- Username: Sescie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 14, 2017 3:03 am
- Post datetime: 2017-12-13T19:05:54+00:00
- Post Title: Tales Of Series: Collection of Tools

Awesome, thnks, it's really help for beginners
I would also need something like this for the Path of Exile game? Do you play in PoE? For good walkthroughs, I can give you some exalted orbs.
## Post #4
- Username: Unlimitedskills
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 04, 2018 4:50 pm
- Post datetime: 2018-05-13T10:15:19+00:00
- Post Title: Tales Of Series: Collection of Tools

I have some tools for tales games i will be releasing soon as well. Hope they can aid everyone in your translations.
## Post #5
- Username: Graveyard
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 04, 2017 3:04 am
- Post datetime: 2018-06-15T17:37:02+00:00
- Post Title: Tales Of Series: Collection of Tools

Would it be possible to provide the tools of Tales of Phantasia (PS1) and Tales of Vesperia (Xbox 360)?
## Post #6
- Username: Evil Finalist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 14, 2014 7:17 am
- Post datetime: 2018-06-23T09:27:46+00:00
- Post Title: Tales Of Series: Collection of Tools

UPDATE
Tales of Vesperia Tools
Platforms: Xbox 360, PS3

We've abandonded the idea of JP/EN -> Ru translation.
[http://temple-tales.ru/translations_tovps3.html](http://temple-tales.ru/translations_tovps3.html)

Thankfully, Bandai Namco have announced Tales of Vesperia: Definive Edition which would contain russian subtitles, thus we don't have to make efforts trying to transalte it. It was a huge experience. Despite everything, I was glad to have a chance to work on the resources of this game. And now I post all tools for hacking this jRPG.

> Reply from Graveyard
>
> Would it be possible to provide the tools of Tales of Phantasia (PS1) and Tales of Vesperia (Xbox 360)?
Unfortunately, completely with the version Xbox 360, this set of tools does not help. Only with PS3.
Tales of Phantasia Tools
It is not soon to be expected.
## Post #7
- Username: Graveyard
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Nov 04, 2017 3:04 am
- Post datetime: 2018-07-02T03:06:32+00:00
- Post Title: Tales Of Series: Collection of Tools

> Reply from Evil Finalist
>
> UPDATE
Tales of Vesperia Tools
Platforms: Xbox 360, PS3

We've abandonded the idea of JP/EN -> Ru translation.
http://temple-tales.ru/translations_tovps3.html

Thankfully, Bandai Namco have announced Tales of Vesperia: Definive Edition which would contain russian subtitles, thus we don't have to make efforts trying to transalte it. It was a huge experience. Despite everything, I was glad to have a chance to work on the resources of this game. And now I post all tools for hacking this jRPG.
Graveyard wrote:Would it be possible to provide the tools of Tales of Phantasia (PS1) and Tales of Vesperia (Xbox 360)?
Unfortunately, completely with the version Xbox 360, this set of tools does not help. Only with PS3.
Tales of Phantasia Tools
It is not soon to be expected.

Thanks.
## Post #8
- Username: Evil Finalist
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 14, 2014 7:17 am
- Post datetime: 2018-07-14T16:01:34+00:00
- Post Title: Tales Of Series: Collection of Tools

UPDATE
Tales of Destiny Director's Cut Tools
Platforms: PS2

A few months ago we started the translation of Tales of Destiny Director's Cut into Russian language.

Artist (working with textures): https://twitter.com/cameliemimika

At the moment we have not figured out all the file formats. But this is temporary.
We are working on it. But I decided that it's worth sharing tools.
The main reason is that after ABSOLUTE ZERO have abandoned their projects, a group of people contacted me.
They want to make their own translation of this game from Japanese into English.
I intend to support them with everything possible for analyzing resources.
I hope, sooner or later, our projects will be released.
## Post #9
- Username: weirdalsuperfan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Apr 23, 2019 5:54 pm
- Post datetime: 2019-07-01T18:31:17+00:00
- Post Title: Tales Of Series: Collection of Tools

Do you have the Tales of Symphonia tools? I want to extract the Japanese text strings from it. Or would you happen to have those text files?
## Post #10
- Username: Calvolandia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 18, 2020 6:04 am
- Post datetime: 2020-12-17T22:15:21+00:00
- Post Title: Tales Of Series: Collection of Tools

Bit of a newbie here, but would it be possible to use tales of berseria pc files to port all of the spanish text with the tools posted here?

PD: also, could anybody do it for me, please?
## Post #11
- Username: amirsonb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 22, 2021 10:47 pm
- Post datetime: 2021-05-22T14:53:05+00:00
- Post Title: Tales Of Series: Collection of Tools

Hi, I found your site after seeing the TOD DC made by Life Bottle Productions.

I was wondering if you have the tools for Tale of Rebirth. I played it using translation guide. I wanted to create a translation patch for it, just like how Life Bottle Productions did.
