## Post #1
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-06-13T14:48:35+00:00
- Post Title: Krater (PC)

Hello!
Is there anybody knows something about the files?

The data folder builds up from folders named 0 to 105
in folder 0:
files: 1,2,3,4,5...99

in folder 1:
files: 101,102,103...199

in folder 105:
files 10500,10501...10547

and some random named files. (for example: 3ff9e9c5f68b4235)
None of the files have attribute name.
## Post #2
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-16T19:36:53+00:00
- Post Title: Krater (PC)

XX\XXYY - files without extension. for example:
krater\data\83\8364 - DDS DXT1 texture
krater\data\25\2589 - compiled Lua script (named scripts/settings/questlog.lua)
we can decompile scripts with any lua 5.1 decompiler (luadec or unlua), but need crop first 4 bytes.

files 3ff9e9c5f68b4235, 9e13b2414b41b842, 30d3ac7d103556ae, etc...

```
long unpackedSize;
long zero; // \x00\x00\x00\x00
forever {
  long zsize; // size of packed block
  char data[zsize];
  if (zsize < 0x10000) {
    // zlib packed data, unpacked size is 0x10000
  } else {
    // not packed data, size is 0x10000
  }
}
```


file exploded_database.db

```
long filesCount;  // number of files XX\XXYY, 10545 in v1.0.3
for (i = 0; i < filesCount; i++) {
  longlong resourceUnit;
  longlong resourseName;
  long langId;  // 0-english localization, 1-french, 2-??, 4-german, 8-sweden...
  long fileName;  // number
  long fffs;  // \xFF\xFF\xFF\xFF
}
long footer; // \x08\x00\x00\x00
char footerData[64];
}
```


"unpacked" files 3ff9e9c5f68b4235, 9e13b2414b41b842, 30d3ac7d103556ae, etc...

```
long entries; // number or files
char headerData[64]; // equal to 'footerData[64]' from 'exploded_database.db'
char zeros[192]; // filled by zero

// list of ids
for (i = 0; i < entries; i++) {
  longlong resourceUnit;
  longlong resourseName;
}

// files
for (i = 0; i < entries; i++) {
  longlong resourceUnit;
  longlong resourseName;
  long numLangs;
  long zero;  // \x00\x00\x00\x00

  for (i=0; i<numLangs; i++) {
    long landId[i];
    long size[i];
    long zero[i];  // \x00\x00\x00\x00
  }

  for (i = 0; i < numLangs; i++)
    char entry[size[i]];  // nameless filedata
    // copyEntryToFile();
  }
}

```


font descriptors:

```
float size; // vertical height, px
float lineHeight;  // distance in pixels between each line of text.
float base; // number of pixels from the absolute top of the line to the base of the characters
float textureWidth;
float textureHeight;
long glyphCount;
for (i = 0; i < glyphCount; i++) {
  long glyphCode;  // UTF8
  float x;  // left position of the character image in the texture
  float y;  // top ...
  float width;  // width of the character image in the texture
  float height;  // height ...
  float xOffset;  // how much the current position should be offset when copying the image from the texture to the screen
  float yOffset;  // ...
  float xAdvance;  // How much the current position should be advanced after drawing the character
}

```


known resourcesUnit (hash):

```
9EFE0A91 6AAE7880 - font descriptors
A439F7FF E16B7399 - ogg files in one file
AD9C6D9E D1E5E77A - game engine packages
D30FB410 AB2B970D - localization
E217D12C FA8D4EA1 - compiled Lua scripts
```


hash generator (Qt code, from MurmurHash2, 64-bit versions, by Austin Appleby):

```
{
    const quint64 m = 0xc6a4a7935bd1e995ULL;
    const quint32 r = 47;
    const quint64 *data = (const quint64 *)key;
    const quint64 *end = (len >> 3) + data;
    quint64 h = seed ^ (len * m);
    while(data != end) {
        quint64 k = *data++;
        k *= m;
        k ^= k >> r;
        k *= m;
        h ^= k;
        h *= m;
    }
    const quint8 *data2 = (const quint8 *)data;
    switch(len & 7) {
    case 7:  h ^= quint64(data2[6]) << 48;
    case 6:  h ^= quint64(data2[5]) << 40;
    case 5:  h ^= quint64(data2[4]) << 32;
    case 4:  h ^= quint64(data2[3]) << 24;
    case 3:  h ^= quint64(data2[2]) << 16;
    case 2:  h ^= quint64(data2[1]) << 8;
    case 1:  h ^= quint64(data2[0]);
    default: h *= m;
    };
    h ^= h >> r;
    h *= m;
    h ^= h >> r;
    return h;
}
```


in localizations files used only 32-bit hash, for example:

```
hash64 = MurmurHash64A(stringId, ...) // hash64 = 0x1d3be1796d7cc1bf
hash32 = (hash64 >> 32)               // hash32 = 0x1d3be179
text = localizer(hash32)              // text = "New weapon"
```

[link to Google Docs](https://docs.google.com/folder/d/0B5VCF_v6rzV0eElBVXlJV1p1ZTg/edit) with a lot of bms script.
## Post #3
- Username: hunpatrik
- Rank: veteran
- Number of posts: 101
- Joined date: Tue Jan 05, 2010 4:21 am
- Post datetime: 2012-06-16T20:30:02+00:00
- Post Title: Krater (PC)

I'm only interested in lang files and font files if some chars are missing. If you find something interesting for me, please post it.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-17T00:28:04+00:00
- Post Title: Krater (PC)

the following unpacking script for quickbms is based on the info provided by hhrhhr, let me know if it works:

```
get unpackedSize long
get zero long
savepos OFFSET
get PAK_SIZE asize
putvarchr MEMORY_FILE unpackedSize 0
log MEMORY_FILE 0 0
append
for OFFSET = OFFSET < PAK_SIZE
    get zsize long
    savepos OFFSET
    if zsize < 0x10000
        clog MEMORY_FILE OFFSET zsize 0x10000
    else
        log MEMORY_FILE OFFSET zsize
    endif
    math OFFSET += zsize
    goto OFFSET
next
append

#get unpackedSize asize MEMORY_FILE
get NAME basename
string NAME += "_unpacked"
log NAME 0 unpackedSize MEMORY_FILE
```
## Post #5
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-17T01:22:06+00:00
- Post Title: Krater (PC)

it work, but MEMORY_FILE... the game has a files size of 100-300MB ;)
better use TEMPORARY_FILE, then at end of script something like this:

```
log name 0 unpackedSize 1
```

unpackedSize is always smaller then ASIZE (which is a multiple of 64 KB)

> Reply from hunpatrik
>
> I'm only interested in lang files and font files if some chars are missing
fonts are in: 6486, 6487, 6494, 6496, 6751-6803; just rename it to *.dds 
if you change them, the most important thing that matched the size to bytes. i used the nvcompress  utility and it did dds-file a few bytes smaller, so the game crashes. have to add some 0x00 to the end.

p.s.
2aluigi
is it possible to automatically delete the temporary file?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-06-17T14:58:27+00:00
- Post Title: Krater (PC)

eh no, the deletion of the temporary_file is asked to the final user.

instead of memory_file it's possible to use also directly the final file but every time the user must confirm the appending or press 'a' to do it automatically.

fixed the unpackedsize thing
## Post #7
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-17T17:29:34+00:00
- Post Title: Krater (PC)

localization found:
6477 - (0x00) english
6478 - (0x01) french (Le service en ligne est désactivé sur votre compte ¾ en raison de paramètres de contrôle parental.)
6479 - (0x02) ???? (null)
6480 - (0x04) german (Onlinedienste für dein ¾-Konto wurden durch die Kindersicherungseinstellungen deaktiviert.)
6481 - (0x08) ???? (Onlinetjänsten är avstängd på ditt ¾-konto på grund av)
6482 - (0x10) polish? (Zepsuty filtr)
6483 - (0x20) ???? (null)
6484 - (0x40) ???? (Tu cuenta Вѕ tiene el servicio online desactivado por ajustes de control paterno.)
6485 - (0x80) ???? (Il servizio online non ГЁ abilitato sul tuo account Вѕ a causa delle impostazioni del filtro contenuti.)

only english strings is complete, all other is very limited or filled with zeros.

structure:

```
long stringsCount;
for (i = 0; i < stringsCount; i++) {
  long stringID;
  long stringOffset;
}
// zeroended strings data
// [EOF]
```


p.s.
filenames 6477 - 6485 may change in furute versions. they can be found in the exploded_database.db by hash D3 0F B4 10 AB 2B 97 0D 9A DB 11 66 F8 70 44 B6
(hash, 4-bytes flags, 4-bytes filename).
## Post #8
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-18T10:28:05+00:00
- Post Title: Krater (PC)

ok, now is packed ogg files (hash A439F7FFE16B7399):

```
long zero;
for (i = 0; i < numOggs; i++) {
  long hash1;  //
  long hash2;  // as filename
  long offset;  // absolute
  long size;    // head + ogg
}
// offset
long headSize;  // 68
long oggSize;
char someHeaderData[60];
char oggData[oggSize]
// saveOggData(*oggData)
...
// repeat numOggs times

```


total number of oggs - 4358
## Post #9
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-18T13:18:08+00:00
- Post Title: Krater (PC)

this is all what i have.
script for ungzip 3ff9e9c5f68b4235, 9e13b2414b41b842, 30d3ac7d103556ae...
example output: 3ff9e9c5f68b4235 -> 3ff9e9c5f68b4235.big
—
script for unpack prevouis file
example output: 3ff9e9c5f68b4235.big -> dir\file
directory names: _%hash1%_%hash2% (for known name write "textures", etc.)
filename: %hash3%_%hash4%_%langId% (only scripts has name)
—
script for copy and sort files XX\XXYY use info from exploded_database.db (used as source)
example output: 64\6477 -> localization\9adb1166_f87044b6_0.lang
—
script for convert localization files (*.lang) to readable xml
example output: 9adb1166_f87044b6_0.lang -> 9adb1166_f87044b6_0.xml
Code: Select all<s id="004f425e">Tunnel Varg</s>
<s id="0096b2e6">Devil's pit ghast</s>
<s id="009b0253">Buffs Intelligence</s>
<s id="00af0e3b">of Programming</s>
script for unpack ogg files (*.oggpak)
example output: 6e4c394b_147c9ae5_0.oggpack -> dir\file
directory name: %source_name%
filename: %hash3%_%hash4%

all Lua scipts can be decompiled. i used Java decompiler unluac from [http://sourceforge.net/projects/unluac](http://sourceforge.net/projects/unluac), it failed only on 5 files. luadec from [https://github.com/sztupy/luadec51](https://github.com/sztupy/luadec51) can decompile all, but have not a pretty look for variable names.
i try chage and compile its again (with Lua 5.1.4, 5.2 not supported), but size is changed.

by the way, everything from large archives of files in exactly the same files XX\XXYY. i deleted these archives and play without problems for several hours (but turned off the steam check). these archives is 610Mb of extra data. 

p.s.
sorry for bad english.
## Post #10
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2012-06-18T17:44:28+00:00
- Post Title: Krater (PC)

great news! now i need to learn how to try it haha
## Post #11
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-06-18T19:14:18+00:00
- Post Title: Krater (PC)

Here tool for 6477 file: [http://www.sendspace.com/file/9e7mew](http://www.sendspace.com/file/9e7mew)
Rename the 46f4455f4676790b container, or the game wont load the file.

Im not playing the game so i hope this not causing crashes.

Update: Added exporter
## Post #12
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-18T21:16:02+00:00
- Post Title: Krater (PC)

Well, I injected the modified text file and renamed the file, the game works, but the texts won't load (at least on the Steam version).
## Post #13
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-19T02:15:33+00:00
- Post Title: Krater (PC)

> Reply from swuforce
>
> Here english text and importer for 6477 file
new_6477 have a 2-bytes shift in text area, not equal to original 6477, have a smaller size and bigger index section.
and cannot be reimported again ;)
## Post #14
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-06-19T13:46:46+00:00
- Post Title: Krater (PC)

> Reply from lostprophet
>
> Well, I injected the modified text file and renamed the file, the game works, but the texts won't load (at least on the Steam version).
It creates "new_6477" file. Did you rename it to orig?

> Reply from hhrhhr
>
> cannot be reimported again
You can import only to the original file.
## Post #15
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-19T15:43:29+00:00
- Post Title: Krater (PC)

> Reply from swuforce
>
> lostprophet wrote:Well, I injected the modified text file and renamed the file, the game works, but the texts won't load (at least on the Steam version).
It creates "new_6477" file. Did you rename it to orig?

Oh, so that was my problem. So the reimport feature works, but the game was updated to 1.03 on Friday and it looks like they added extra lines. For example: in the Main menu, where the "Új játék indítása" (Start New Game equivalent in Hungarian) should be, now there is a random conversation from the game.
I can supply the freshest 6477 file, if you need it (or any other file from the game) in PM.

Awesome work swuforce!
## Post #16
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2012-06-20T23:03:00+00:00
- Post Title: Re: Krater (PC)

i would like the scripts files   Can you make changes, and the game still works?
## Post #17
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-20T23:34:49+00:00
- Post Title: Re: Krater (PC)

Game works with modified language file (I tried it with Steam).

On a sidenote: watch carefully, what you translate! As of now, I found 

```
Weapons
```


that SHOULD NOT be translated, since it is part of a variable. If you translate it, on some weapons it will screw up the description.
## Post #18
- Username: Anton666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 23, 2012 3:56 am
- Post datetime: 2012-06-22T20:05:07+00:00
- Post Title: Re: Krater (PC)

swuforce, thanks for the tool.

Tell me, where is stored the markup fonts?
## Post #19
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-22T20:58:19+00:00
- Post Title: Re: Krater (PC)

> Reply from lostprophet
>
> since it is part of a variable. If you translate it, on some weapons it will screw up the description.
this file contains only strings for localization, variable names are not there.
## Post #20
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-06-23T11:59:41+00:00
- Post Title: Re: Krater (PC)

> Reply from hhrhhr
>
> lostprophet wrote:since it is part of a variable. If you translate it, on some weapons it will screw up the description.
this file contains only strings for localization, variable names are not there.
Just try it 
If you translate the word above (I translated it to Fegyverek), ingame move to cursor on top of a class-specific weapon, and instead of for example: "Medikus weapon", it'll say "sv_Fegyverek".
## Post #21
- Username: xentaxus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 16, 2011 2:59 pm
- Post datetime: 2012-06-25T05:08:18+00:00
- Post Title: Re: Krater (PC)

hi all,

i used the quickbms script of aluigi to unpack one of the files in the data directory, file 46f4455f4676790b (it doesn't process any of the 2 *.stream files), i downloaded the luadec51_2.0_win32_bin.zip file from [http://files.luaforge.net/releases/luad ... 32_bin.zip](http://files.luaforge.net/releases/luadec51/luadec51-win32-bin/LuaDec5.1binaryforwin32/luadec51_2.0_win32_bin.zip), i used the oggpack script of hhrhhr with it, 
```
C:\>"C:\lua.exe" "C:\oggpacklua" "C:\Krater\data\46f4455f4676790b_unpacked"
```
 and it outputs this. 
```
C:\lua.exe: C:\oggpacklua:1: '=' expected near 'numOggs'.
```


either i'm doing something wrong, or the file doesn't contain any audio data, or both.

i'm interested in the music of the game.
## Post #22
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-06-25T20:41:51+00:00
- Post Title: Re: Krater (PC)

> Reply from xentaxus
>
> i'm interested in the music of the game.
script 1 - [http://nopaste.info/591e95f801.html](http://nopaste.info/591e95f801.html), save it as "unpack1.bms"
script 2 - [http://nopaste.info/039f7ba9ec.html](http://nopaste.info/039f7ba9ec.html), save it as "unpack2.bms"

step 1:
quickbms.exe -f "*.oggpak" unpack1.bms path_to_exploded_database.db output

all packed oggs will be copied to the "output" directory in the current directory

step 2:
for /r %i in (*.oggpak) do quickbms.exe unpack2.bms %i ogg

all oggs will be unpacked to "ogg" directory

for example, ogg\(e2713844e4f23f47)(8658)\(fae5f25ba0f2d3cc).ogg - start screen theme.
## Post #23
- Username: xentaxus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 16, 2011 2:59 pm
- Post datetime: 2012-07-08T14:57:09+00:00
- Post Title: Re: Krater (PC)

thank you hhrhhr
## Post #24
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-07-11T09:45:17+00:00
- Post Title: Re: Krater (PC)

i'm make some tools for fully automated export/import language files. i hope it will be usefull for translators.
go to https://github.com/hhrhhr/Lua-utils-for-Krater/tags, download auto-import-export.zip and unpack it.
edit _include.bat, change path to game and lang code:
Code: Select all:: game directory
set krater=f:\steam\steamapps\common\krater
:: source language
set src_lang=eng
:: language number (not all known)
set src_lang_num=0
:: target language
set tr_lang=rus
run step0_convert_localization_to_txt.bat, it convert all localized strings to text files in _work directory. these files can be used as backup of original langs
now run step1_unpack_lua_scripts.bat, ~1100 scipts are unpacked and decompiled in _script directory. do not pay attention to errors, not all scripts can be decompiled. errors log can be found in _work\unlua_errors.log
then run step2_export_for_translators.bat, it make _work\for_translate\*.txt.
now you can start translation. do not touch words like "#cooldown seconds", "#damage_multi{percent}", "#cast_time", etc. in result you get this:
Code: Select all[7f18e972]
id  = ability_cast_area_slow_optional_text
eng = It's a trap!
rus = Это ловушка!
[7f18e972] - this is unique string hash, do not modify!
id - ingame ID of string, where hash = MurmurHash(id)
eng - original text
rus (or your lang) - translated text
when you done (or partially done), put all translated files (not necessarily all) in _work\translated directory and...
...run step3_import_translated.bat. check what file _work\game_strings_(your_lang).txt exist, this file contains only translated strings.
and finally run step4_merge_lang_save_bin.bat and look on file _work\game_strings.(your_lang).bin. copy it as krater\data\64\6477 (in v1.0.8) and test in the game.
if you don't backup your original 6477, then empty _work\game_strings_(your_lang).txt (make it 0 bytes) and run step4_merge_lang_save_bin.bat again. this file is not binary equal because i'm clean some tail whitespaces, otherwise it is fully correspond to the original.

p.s.
other .bat and .lua not ready for public :) now i'm work on automated font generation. manually we can change all font for russian translation (original fonts do not support cyrillic glyphs):
[](http://minus.com/lbiJtkCP2kn2t8)
## Post #25
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-19T09:34:10+00:00
- Post Title: Re: Krater (PC)

Need update on the tools, a huge update came out this week and since then I'm getting this:

I have the game, so if you need the latest files (if you don't have them) please PM me.

Thanks in advance.
## Post #26
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-10-19T13:20:04+00:00
- Post Title: Re: Krater (PC)

now the game is using LuaJIT instead of the usual Lua-bytecode.  i do not know the tools to decompile LuaJIT, so updates in this part will not.
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-19T16:05:22+00:00
- Post Title: Re: Krater (PC)

LuaJIT can with simple commands. -bl (Byte Code + Listing)

```
luajit -bl megacool.lua megacool.dec
```
## Post #28
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-10-19T17:42:52+00:00
- Post Title: Re: Krater (PC)

> luajit -bl...
i know. but, old decompiled Lua-bytecode:

```
BootCampArchetypes.norrmalm = {
  price = {
    [2] = 10000,
    [3] = 20000
  },
  name = "bootcamp_norrmalm"
}
BootCampArchetypes.bootcamp = {
  price = {
    [2] = 3000,
    [3] = 20000
  },
  name = "bootcamp"
}
```


decompiled from LuaJIT:

```
0001    TNEW     0   0
0002    GSET     0   0      ; "BootCampArchetypes"
0003    GGET     0   0      ; "BootCampArchetypes"
0004    TDUP     1   4
0005    TDUP     2   2
0006    TSETS    2   1   3  ; "price"
0007    TSETS    1   0   1  ; "norrmalm"
0008    GGET     0   0      ; "BootCampArchetypes"
0009    TDUP     1   7
0010    TDUP     2   6
0011    TSETS    2   1   3  ; "price"
0012    TSETS    1   0   5  ; "bootcamp"
0013    RET0     0   1
```


it is not easy to read and the more they can not be used.
## Post #29
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-19T19:10:47+00:00
- Post Title: Re: Krater (PC)

LuaJIT can decompile only with bytecode. [Here](http://www20.zippyshare.com/v/34753967/file.html) my old tut for manualy bytecode decompiling from Legend of Grimrock. Maybe useful for you.
## Post #30
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2012-10-19T20:32:07+00:00
- Post Title: Re: Krater (PC)

it's informative, but in the game is about a thousand scripts, i used less than a half to find the ID strings.
therefore without automatic decompiler here doing nothing.
## Post #31
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-21T10:39:43+00:00
- Post Title: Re: Krater (PC)

So the problem would be, that it would take way too much time to manually decode the LUAs, right?
Anyway, thanks for your work, you helped me out a lot of times
## Post #32
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-21T11:57:55+00:00
- Post Title: Re: Krater (PC)

> Reply from lostprophet
>
> So the problem would be, that it would take way too much time to manually decode the LUAs, right?
Yeah it's rly long process.
## Post #33
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-10-29T14:10:11+00:00
- Post Title: Re: Krater (PC)

For those, who are still interested in translating Krater.
I contacted one of the developers of Krater ( robert(at)fatshark.se ), who was kind enough to share the most up to date database and localization toolkit with me. So if your language is still not in Krater, but you want to translate/finish your translation, you should contact him.
