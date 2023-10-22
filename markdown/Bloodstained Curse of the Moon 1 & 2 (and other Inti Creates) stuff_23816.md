## Post #1
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-05-02T05:48:28+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Hello everyone, I managed to find out very little information about these games from the interwebs, so maybe someone will find this useful.

Here's a tool for decrypting/encrypting (if you can really call it encryption, it's not using AES or any other real encryption algorithm) datafiles from COTM1 and COTM2. Not all files encrypted, and I think some are compressed in addition to being encrypted. It's a very simple single file C program, should compile and work fine with gcc, clang, msvc, pretty much anything.

It may also work for some other Inti Creates games, but I haven't tried.

I have no idea where the game code reads or calculates the keys for the "encryption algorithm", but it seems there are four different possible keys used with the same decryption code, one per data type ("obj", "bft", "set" or "scroll").

The same keys seem to work for both COTM1 and COTM2 on all platforms.

Also, in the PC versions of both games, the filenames have been obfuscated changing each file's name to the MD5 hash of the actual filename. It is possible to recover the original filenames by logging them as the game accesses them (by eg. hacking the binary to report them via OutputDebugStringA), or using file listings from console versions which don't have obfuscated filenames. Note that for some filenames, you'll need to add a platform specific "Win/" directory prefix before hashing the filename (on Switch, these files would be in an actual "NX/" subdirectory inside the romfs, for some reason there is no equivalent subdirectory inside the PS4 version's package).

Using these methods, I have recovered original filenames for all but two of the files in the the DataHash directory on PC for COTM2. (I played through the game multiple times taking different routes, but the logger didn't catch anything which would match those two when MD5 hashed, unfortunately it's not really feasible to brute force the remaining ones, at least not with only a single albeit reasonably powerful GPU, the filenames could be up to 20-30 characters or even more, and may contain at least lowercase and capital letters, numbers, underscores and a single dot.)

For COTM1, I have recovered 261 of 296 filenames based on file listings from console versions. I'll need to play through it a few times with a logger patched one day...

Next up is going to be figuring out the actual map and background graphics formats. I want to write a program which can show the maps. 

Btw. if you want to look at them, use the "set" key for map*.stb files and "scroll" key for map*.scb files. *.osb files use the "obj" key.

The zip includes the encdec.c program and MD5 filename hash lists for COTM1 and COTM2.

(removed, see [viewtopic.php?p=176034#p176034](https://forum.xentax.com/viewtopic.php?p=176034#p176034))

edit: oh yeah, if you rename map00.stb to map01.stb (look at the hash lists), you'll get a debug map (in both games) when you start the game! nothing that interesting or useful there, though.

edit2: forgot the line for ARGV0 in the args enum...

edit3: "bft" key is used for fonts, and the keys for all four data types are generated like this:

```
#define BASEKEY 0xA1B34F58CAD705B2LL

uint64_t type2key (const char *type)
{
  uint64_t key;
  int i, l;
  char buf[12];
  
  strcpy(buf,type);
  strcat(buf,WTFSTRING);
  
  l = strlen(buf);
  
  key = BASEKEY;
  
  for (i=0; i<l; i++)
  {
    key += buf[i];
    key *= 141;
  }
  
  return key;
}

```


(this gives correct 64-bit keys with input "obj", "bft", "scroll" or "set")

The scroll, font and obj data have been zlib compressed before obfuscation, set data seems uncompresed. The first four bytes are a header which tells the required length for decompression buffer.

Here are raw RGBA views of BMPFont.bfb and Win/map01.scb after deobfuscation and zlib decompression (imgur links because it seems only one attachment per post is permitted and I'll only make a 2nd post when/if I can do something interesting like editing the stage layout, or someone else posts which just happened):

[pic1](https://i.imgur.com/yxOOuEG.png)
[pic2](https://i.imgur.com/7tib6cd.png)

I stll don't know the actual header (after decompression), stage layout, etc., etc. formats.

I changed the name of the program to inti_encdec since it also works for other Inti Creates games. The version in the zip can now decode/encode larger files which are found in games other than COTM1/COTM2. It can also now decode/encode the system and game save data files in COTM1 and COTM2! (but probably not any of the other games, the save keys are different between COTM1 and COTM2 so probably the other games all use their own keys too).

I have also added file lists for other games to the zip (thanks RandomTBush) plus added the missing files to the COTM1/COTM2 lists.

I have tested decoding & re-encoding the map01 files with it and the game still loads it fine.  Next up will be figuring out the actual map formats...
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-05-03T05:08:49+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Ah, if only I had this sorta thing earlier. Excellent! 

I actually went through the effort of matching the MD5s to the filenames myself a while back, here's the remaining hash/filename pairs you missed from Curse of the Moon 1:

```
c9b695137c3dbd390150e4348f074456 Patch/BMPFont.bfb
1bfe6e6cf774a0870c018295951bf12b Patch/Calibration.ttb
84e0bdd4f11b909afd106b92b7fa2eec Patch/Calibration00.osb
71252704d813442e58c71c759d4d4ad1 Patch/EndingText00.osb
f9cf939192ce50e965fa11c4a0de01b2 Patch/GraphicText00.osb
98fbc7acc38ac990b17a5378670d554c Patch/GraphicText04.osb
be2e9161a3a6bb7ef65ca32561ac77e4 Patch/IconClear00.osb
8689aef4b3ef37c2971f133a5f0a459e Patch/map01.scb
0fd633200c773c7e84f748b628328cc2 Patch/map01.stb
e60dfd11647f3c2e1177d03c2eb8fa0c Patch/map02.scb
32cc4ef02249169f6e0a7fc79054a1a7 Patch/map02.stb
c4c6b279e307d8b2f7f46fc63430e8b5 Patch/map03.scb
b004be0f1bee105e0833d8b6456b6b75 Patch/map03.stb
5c035e8886b9d1ce24515a858f7efdb2 Patch/map04.scb
1ea347e5b1a0403acf227c16e11eee22 Patch/map04.stb
2bf50e8a81ac3922e77961d4964c4bbe Patch/map05.scb
5af88824a4446fe0d2f1aaa909038549 Patch/map05.stb
88d5983aa1760c94ccc8dfe103b21382 Patch/map06.scb
02d49b6034dac68b8bb19fa07edf4fcd Patch/map06.stb
4c14f860a52c402993341f172fd74f4e Patch/map07.stb
ae64a0c89814868a34acb4b62200548c Patch/map08.scb
9f8740b5f4013f455c4092d25d7441ec Patch/map08.stb
268d9be0086f14534c599281eec71c0f Patch/map09.scb
a53f870e5c4c376ec19450a8e8ba3d7f Patch/map09.stb
4112b562760811b246db33484dce725b Patch/MapDemo00.osb
88023ef468a04af2f2901a6a3683cf11 Patch/MapDemo03.osb
48fb4636e9cd3dacf77a6a6bf98e5703 Patch/Openingext00_en.osb
ad3cd8a3bda596b1547359e2479e0625 Patch/Option.ttb
39b9333c89ce132badcc0c2de3a58912 Patch/OptionKeyboard.ttb
2f493b619a9cf9f79e8291655dbc5e36 Patch/PauseMenu.ttb
7ce96b6103c39567090f03eb5dff9e56 Patch/Side01.osb
635acf9a9f63b05d9b1ce9382633a8a6 Patch/Staffroll_Picture00.osb
ccda2e2e84f49dfd56530e35616a3b44 Patch/Title00.osb
8e2a602aadb120226e2393c6afb24dcf Patch/Window00.osb
```


And one from Curse of the Moon 2:

```
7f51424d446ad5e968e5251366c617ce Win/Window00.osb
```


That should just leave one file from Curse of the Moon 2 (db5f673dd61144c9c37e7b388e74e42e), which apparently doesn't belong to CotM2 at all, as it's the Demonpillar (zk04_im0.osb) from Dragon Marked for Death.

(EDIT: I can also confirm that your program also works just fine with files from both Blaster Master Zero 2 and Mighty Gunvolt Burst! I assume Dragon Marked for Death will work too, if the leftover file in CotM2 is any indication.)
(EDIT the 2nd: Yep, Dragon Marked for Death also works, barring a handful of files.)
## Post #3
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-05-03T06:32:04+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Oh yeah, I got my file list for COTM1 from an unpatched Switch version, that explains why all the Patch/* files were missing. MapList.json was missed because I didn't think to check if any of the hashes from COTM2 match COTM1. The proper filename for the file from the wrong game could probably be found from the console versions of that game.

Btw. which RGBA viewer are you using? I can't figure out how to get the colors right in BinxelView. Wrong R/G/B/A byte ordering I guess, actually it seems the program may not have proper support for 32bpp RGBA at all, only 24bpp RGB.

I thought I could avoid having to write any graphics code until later (if/when I have enough of the formats figured out for drawing the actual stage maps), but if there's not a better raw RGBA data viewer I guess it can't be helped...
## Post #4
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-05-03T07:12:17+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

> Reply from xttl ↑Mon May 03, 2021 2:32 pm at Mon May 03, 2021 2:32 pm
>
> 
Oh yeah, I got my file list for COTM1 from an unpatched Switch version, that explains why all the Patch/* files were missing. MapList.json was missed because I didn't think to check if any of the hashes from COTM2 match COTM1. The proper filename for the file from the wrong game could probably be found from the console versions of that game.

Btw. which RGBA viewer are you using? I can't figure out how to get the colors right in BinxelView. Wrong R/G/B/A byte ordering I guess, actually it seems the program may not have proper support for 32bpp RGBA at all, only 24bpp RGB.

I thought I could avoid having to write any graphics code until later (if/when I have enough of the formats figured out for drawing the actual stage maps), but if there's not a better raw RGBA data viewer I guess it can't be helped...Yeah, that would explain it then, heh.

Anyway, I use [TiledGGD](https://www.romhacking.net/utilities/646/) for previewing the files, with the following adjustments: Image > Format > 32 Bit per pixel, Palette > Colour order > RGB, and Palette > Alpha Settings... > Uncheck "Ignore Alpha value", then you can just adjust the width and height with the arrow keys, and shift the image with Page Up/Page Down. Some files in CotM2 specifically (including the unused file) will look like an outline / silhouette in the program, that's because they use palettes located above the image (which is then applied to the image's red channel).
## Post #5
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-05-04T03:47:06+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Updated the zip in first post:
Turns out, the key is NOT supposed to be reset every 384kB, large files (which some Inti games other than COTM1/COTM2 have) can now be unpacked and repacked successfully. Thanks to RandomTBush for testing this.
Added system and game save data decryption/encryption for COTM1 and COTM2. The same code (actually it's just the same obfuscation applied twice with different keys) could also work for other Inti games, but game specific keys/keystrings are required.
Added three new possible asset types/keys to the list "txt20170401", "snd90210", "json180601", cannot be tested with any files from COTM1/COTM2. (unless with something from inside one of the large archive files..?)

(the save data may well be checksummed in addition to the obfuscation, I haven't tried to edit it yet)

I may need to update the tool to use memorymapped files, compress/decompress in chunks and/or encode/decode inside the same buffer to reduce memory use a bit if there are compatible games with even larger files out there...

edit: another little update:
 - added key for tb2 files from Blaster Master Zero 2 & Dragon Marked for Death
 - the program is using memory mapped files now, and decodes/encodes inside a single buffer (should require less memory for large files)
## Post #6
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-06-26T04:43:32+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Hey, uh, I was Googling around and found this topic. Big Inti fan, been searching this kind of stuff as it came up.

It sounds like you guys are using this tool to mod the games? Texture swaps, potential save edits, stage swaps... On the Steam versions? That's really hype, if true. I'm pretty not so good at this kind of thing but I wanna learn and probe the games, regardless.
## Post #7
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-06-27T02:06:53+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Sorry for not posting any updates in a long time! I haven't forgotten about this, just have had other things to do (and some difficulties doing much of anything at all...)

> Reply from DMFDLancer ↑Sat Jun 26, 2021 12:43 pm at Sat Jun 26, 2021 12:43 pm
>
> 
It sounds like you guys are using this tool to mod the games? Texture swaps, potential save edits, stage swaps... On the Steam versions? That's really hype, if true. I'm pretty not so good at this kind of thing but I wanna learn and probe the games, regardless.

Stage swapping was always and is possible without any tools or knowledge about the file formats and obfuscation if you just know the correct MD5 hashed filenames. The main stage definition files are named "map##.stb" (or, in patched COTM 1 for some stages, "Patch/map##.stb").

So if you wanted to eg. swap the first real stage (map01) in COTM 2 with the debug stage (map00), you need to calculate the MD5 hashes for "map00.stb" and "map01.stb". On pretty much any Linux/Unix command line (including WSL), commands "echo" and "md5sum" (or in some cases just "md5") can be used for this:

```
8404a4d77634c07774590adce322c008  -
$ echo -n "map01.stb" | md5sum
2d463c71d6c85a02eb19a07b04a550d8  -

```


which means: just rename 8404a4d77634c07774590adce322c008 to 2d463c71d6c85a02eb19a07b04a550d8 in the DataHash directory/folder to replace the first stage with the debug stage.

In COTM 1, you may need to replace "Patch/map01.stb" instead:

```
0fd633200c773c7e84f748b628328cc2  -

```


so rename 8404a4d77634c07774590adce322c008 to 0fd633200c773c7e84f748b628328cc2.

If you insist on using Windows without WSL (or at least cygwin, msys or something), I'm sure there are good tools to calculate MD5 hashes from strings for Windows too, or you could look up some javascript thing from the webs which runs on your browser. Windows since Vista (or 7?) has included a command line tool called certutil which can MD5 (and SHA1, SHA256, etc.) hash files but I don't know if you can somehow pipe strings to it... you'd also need an echo command that can omit newline characters anyway. Powershell could probably be used for hashing strings somehow, but I know next to nothing about it.

(or: you could just use the filename hash list text files from the encdec tool zip and be done with it)

Graphics modifications are already possible with the tool from this thread. There are huge limitations though: since not much is known about the actual format the level and sprite graphics data is, you'll have to edit everything as unstructured raw graphics data. You won't be able to make an existing sprite frame larger for example, you can just draw over what's already there. You also have no control over how tiles are reused to build other frames.

Graphics ripping is very possible, and I think so far the only thing somebody has used this tool & info for. That does also need some more manual work than it would require if the sprite/background formats were fully understood.

Everything else (editing stage layouts or creating wholly new stages, editing saves, etc.) needs further reverse engineering of the game executable and/or extensive guessing by looking at and carefully editing/corrupting the descrambled and decompressed data. You can de/rescramble and de/recompress all level and save data (among other things) with the tool in this thread, but without knowing the actual data formats it isn't possible to do anything interesting. So far, by editing the level "set" (.stb) or "scroll" (.scb) files, I have only managed to either make the game crash, make items, enemies and triggers from certain rooms or all rooms on a stage disappear, or make a couple of misplaced tiles or invisible barriers appear here and there.

The scrambling and compression methods, and probably most if not all of the actual file formats are the same between the PC/Steam and console versions, so if and when this stuff is figured out, it will also be possible to edit the console versions (assuming you have access to a hacked or developer console, of course).

Personally, I'll be happy if I can just figure out enough of the map format to write a map viewer/editor for COTM 1 and 2. (or someone else figures it out and posts the code/info here ;)

oh yeah, in theory you could also already translate the game to another language since you can de/rescramble and de/recompress both the font graphics files and the ttb files which contain all or most of the text, but you'd have to live with the length of the original text unless you figure out the ttb format (it probably isn't very complex)
## Post #8
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-06-30T11:23:37+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Well, here is a tool (source included) which can dump and rebuild TTB files in COTM1 and COTM2 (possibly other Inti games too) which contain all the in-game text.


 inti_textconv.zip
(40.96 KiB) Downloaded 47 times



Refer to the file lists included to see which data files (under Data/ or DataHash/) are the TTB files.

First, convert the TTB file to a plain text file like this:

```
textconv d <ttbfile> <textfile>
```


eg. to convert PauseMenu.ttb:

```
textconv d 208b1e0c2edfd32ad57b9ff7e03d64b7 PauseMenu.txt
```


then edit the file with any text editor which supports UTF-8, and convert it back to a TTB like this

```
textconv e PauseMenu.txt 208b1e0c2edfd32ad57b9ff7e03d64b7
```


Do not try to change the TXT file structure (don't touch any of the numbers and don't try to split the text for a TTB record to multiple lines, don't add empty lines, etc.).

With this tool you could, for example, translate the games to any language. The text length CAN be changed! (though you should probably stay within a reasonable range of the original text to avoid any possible problems with text positioning and dialog box size, also pay attention to the "\n" newlines and line lengths)

If you need characters which are not included in the original font, then you'll need to edit the BMPFont/BMPFont2 files (as raw graphics since there is no special tool for this yet...). I could help with this is required.

The game uses UTF-8 encoding internally for both the English and Japanese text. It seems SOME (kana) but not all (kanji) Japanese characters work even if the game is set to English mode. Also, all English/latin alphabet characters seem to still work when the game is in Japanese mode. If you are willing to break Japanese support, this can be used to add any diacritics required by your target language.

There are other unused characters in the font too (eg. PlayStation and Switch button graphics, on PC it always uses the Xbox graphics) that may be possible to use for this purpose, but I don't have the character values used for these.

Note that parts of the original English text use the double-width "ideographic space" unicode character (U+3000) instead of a regular space (U+0020), especially text that is displayed using the smaller font (in eg. PauseMenu.ttb). Do not try to change these to regular spaces (or you'll get no space at all when the text is displayed).

If the original text uses C-style formatting specifiers (if you see a percent sign somewhere), do not change the amount or order of those formatting specifiers. See MainGame.ttb from COTM1 or COTM2 for examples of this.

Any more questions, ask here.

edit: seems some versions of Windows notepad may add garbage bytes (BOM) to the beginning when a text file is (re)saved as UTF-8 which confused the "parser" in textconv, updated the zip with a fixed version

edit2: whoops, encoding was not scrambling the last four bytes of the output ttb file, fixed
## Post #9
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-01T20:48:31+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Sorry, I'm just really really dumb with this kind of stuff lol

Gonna see later if I can modify Dragon Marked For Death's JSON files. They're readily readable (at least they should be after I use your app, if the Switch files are any indication) and there's data corresponding to damage mechanics and stat growth.

I don't know how much this info could help, but Inti staff mentioned in a stream Q&A that every Inti Creates game from Gunbike to Megaman to Gunvolt to CotM all run on the same Inti Creates Engine, or more recently (Burst, CotM2, Gunvolt 3 IIRC) it's successor. I imagine it's a nested doll situation?
## Post #10
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-02T11:03:52+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

IIRC RandomTBush tried it, and the JSON key found from COTM2's executable unfortunately does not work for the JSON files from DMFD. None of the others found so far worked either, so it needs more research, probably just new keystrings. I have only purchased copies of COTM1 and COTM2 myself so it is kind of difficult for me to look at the other games, but I'll see what I can do.

(actually, I also have the Mega Man legacy collections on PC and MM9 on PS3, but the MM9/MM10 version of the engine is much older and probably different enough that I'm not going to bother with it for now)

Btw. COTM1 and COTM2 also have one JSON file each which is completely unprotected (not compressed, not scrambled), but it also seems completely unused by the game. It's "MapList.json" = Data/b507cdff033c27d984488a2bc3f3d2ba or DataHash/b507cdff033c27d984488a2bc3f3d2ba

I wonder if the other games really use the JSON files either? (possibly, since Inti bothered to protect them on PC after all...)

Also IIRC console versions of DMFD have the JSON files completely unprotected (but that does not really help if you want to modify them on PC, because almost certainly the PC version will refuse to read unprotected data files if you copied one over from a console version).

edit: ok, I've figured it out, I'll update inti_encdec to decode/encode JSON files from DMFD PC soon
for anyone curious, the trick is to zlib decompress first, then descramble after with a key generated from password/keystring "xN5sUeRo"
I did not expect there would be filetypes which are scrambled before they are compressed (zlib does not even really decompress the scrambled files, on the contrary) so I have to restructure the program a bit.
## Post #11
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2021-07-02T22:17:14+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Oh yeah, and I found out why the BISAR/BIGRP files from CotM and MGB wouldn't decrypt either, xttl -- you need to change "COMP_YES" to "COMP_NO" for the "snd" type, as they're not compressed.
## Post #12
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-02T23:52:07+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Yeah, I fixed that some time ago already (set snd filetype to not compressed) but didn't get around to upload a new version of the program...

Btw. snd filetype is NOT for bigrp files, only for bisar. The bigrp files don't look like compressed or scrambled at all (at least the main header at the start of file isn't, and not all of the contents are either because plain MIDI MThd/MTrk headers among other things can be found inside the bigrp files from COTM1 & COTM2).

Anyway, here's a new version of program which handles snd/bisar files correctly and also can decode & encode JSON files from DMFD PC (use "json2" filetype):


 inti_encdec_v2d.zip
(192.81 KiB) Downloaded 73 times



Note that I changed the order of command line arguments, filetype comes right after the command now, eg.:

```
inti_encdec e scroll Map01.scb ab255c3c30bf31caf83d9819abf32b55
```


edit: damn it I knew I'd forget something again, fixed json2 output (was not writing header properly)

edit2: fixed one incorrect printed status message, also added support for DMFD PC save data as filetype "save3" (look for "SystemData.bin" wherever the game puts save files, probably in game dir, somewhere under your Steam directory or Windows user home dir, not really tested because I don't have the game myself, I'll remove the filetype if it doesn't work) -- redownload if you got "v2" without "b"

edit3: removed save3 filetype since it isn't working as expected

edit4: restored save3 filetype, you'll need to input your SteamID to descramble/scramble savegames from DMFD PC
## Post #13
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-03T04:41:28+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Welp, HitConstParam.json was gutted on Steam. It's just this cResHudWorkCtrl thing... It used to be stuff like mpPlayerStatusGrowRate. I'm gonna see if I can impact anything with the others, as those seem to be hud related, but it's not looking great.
## Post #14
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-03T04:43:12+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

> Reply from DMFDLancer ↑Sat Jul 03, 2021 12:41 pm at Sat Jul 03, 2021 12:41 pm
>
> Welp, HitConstParam.json was gutted on Steam. It's just this cResHudWorkCtrl thing... It used to be stuff like mpPlayerStatusGrowRate. I'm gonna see if I can impact anything with the others, as those seem to be hud related, but it's not looking great.

I wonder what happens if you copy the file from a console version, modify it and and encode it?

...probably they just moved that stuff into the executable or another (binary) datafile...

I guess it could even be just a leftover in the console versions too, like MapList.json in COTM / COTM2? Unless someone with a hacked console and the game has already tested that modifying it does really effect the game...
## Post #15
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-03T05:56:38+00:00
- Post Title: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Tried removing HitConstParam, and cramming in the console one, nada.

I did mess with hud_stage_chat, and I stretched the chat wheel out to oblivion by boosting every coordinate I could find. That's technically a mod, I guess.    The file was identical to the old Switch version, but with some stuff trimmed. (No declared names or something?)

I'm really slow at this, but I'll keep plugging away and see if I can do something. Maybe I can "downpatch" to whatever ancient Switch version I have? Either that or I'll break something in a weird way like I did when I was doing file swaps between GV2 and iX.

EDIT: Tried the save data decoder for Dragon. Uhhhhh... I think it worked? Either way it's totally unreadable. There's a bit at the start (#Ÿ®h   ‘w   and some NUL characters, according to Notepad++) that match but the rest is totally different. I'll mention that there's a config.json in the same folder, but that's just a display selector.
## Post #16
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-03T07:49:02+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from DMFDLancer ↑Sat Jul 03, 2021 1:56 pm at Sat Jul 03, 2021 1:56 pm
>
> EDIT: Tried the save data decoder for Dragon. Uhhhhh... I think it worked? Either way it's totally unreadable. There's a bit at the start (#Ÿ®h   ‘w   and some NUL characters, according to Notepad++) that match but the rest is totally different. I'll mention that there's a config.json in the same folder, but that's just a display selector.

If you see a lot of 00 bytes everywhere in the file that's a good sign, especially if it's a new save file (but even if it isn't). That means descrambling worked properly. Won't be useful for actual editing of the save data though unless the format is figured out, there may even be checksums.
## Post #17
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-03T18:46:11+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from xttl ↑Sat Jul 03, 2021 3:49 pm at Sat Jul 03, 2021 3:49 pm
>
> If you see a lot of 00 bytes everywhere in the file that's a good sign, especially if it's a new save file (but even if it isn't). That means descrambling worked properly. Won't be useful for actual editing of the save data though unless the format is figured out, there may even be checksums.

Nope, it's all stuff like €Bæ%DXbÒ7>BîÝèB before and after decoding. No readable text, and there are precisely two pairs of 00 in the entire thing. It's a fairly fresh file, only one character on one save has been played.

If sharing save data is allowed on here I can give you a fresh one, if necessary.
## Post #18
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-04T10:25:12+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

Okay I removed the save3 filetype for now. I am not a moderator but I'd guess it's ok if you send the save file via PM.

Btw. I went ahead and got the zip file password for the big "disc" file (which is really a zip) in Mega Man Legacy Collection 2 on PC. Has it been published somewhere already? (do I just fail at searching the internet?)

It's a really long 254 byte chunk of garbage, so it's kind of difficult to share and use (are there any unzip programs which support eg. parsing C-style \x escapes when entering the password? not everyone and everything is using the same character encoding and it has a lot of non-ASCII chars), but I also made a modified version of the miniunz program from [here](https://github.com/madler/zlib/tree/master/contrib/minizip) which can read the password from a file.

Password in hexdump -C format here:

```
00000010  dc 90 63 e0 e3 90 c8 9e  52 92 ad 94 42 8b 50 9f  |..c.....R...B.P.|
00000020  9e 81 cc 9c 91 94 e0 e8  eb 8a f8 8d 61 8e 87 34  |............a..4|
00000030  96 79 e9 71 e7 cd 33 e6  43 96 82 9a ba 9d 91 e1  |.y.q..3.C.......|
00000040  fb e3 ef 9f 67 e0 df 77  81 40 2e 84 9f 8b d4 9b  |....g..w.@......|
00000050  a9 95 98 8f ee e3 9f 88  a9 90 98 9c ad 95 d7 e3  |................|
00000060  4d 96 f0 e7 74 e4 40 ea  46 9c aa 81 93 e2 58 92  |M...t.@.F.....X.|
00000070  98 e7 ef 8b d9 8d 8c 8f  dd 8c 40 8b f6 e2 cf e2  |..........@.....|
00000080  e3 9f 66 99 60 96 a8 83  7e 83 83 e6 e9 92 73 e2  |..f.`...~.....s.|
00000090  c4 90 a0 95 90 e0 c4 e4  ce 9e fb 9d 62 96 65 e7  |............b.e.|
000000a0  c0 81 4b e5 6f 92 b4 8c  47 9f 53 8b 99 82 64 8d  |..K.o...G.S...d.|
000000b0  b4 e0 a2 81 e1 99 56 e9  6d e6 e6 8c cb e4 91 e6  |......V.m.......|
000000c0  e4 96 e1 81 6f 83 90 91  9b 8d 42 8a 86 c6 e4 69  |....o.....B....i|
000000d0  e8 8c 90 72 8e 86 9a b0  e4 95 9d 8d 8f bd 8a ca  |...r............|
000000e0  84 5f 93 e7 89 b5 94 7c  95 63 95 62 e7 56 e6 80  |._.....|.c.b.V..|
000000f0  e7 a9 9b eb e1 5a 8d be  9d d7 9c 52 e9 c5        |.....Z.....R..|
```


I'll post the modified miniunz program + source later.

edit: here, 

 mmlc2_unzip.zip
(99.62 KiB) Downloaded 29 times


get the minizip/miniunzip sources from the zlib github repo linked above and apply included diff if you want to compile it yourself

To extract "disc" zip from MMLC2 (password bin file is included in attachment):

```
miniunz -s mmlc2pass.bin -x <path_to_discfile> [-d targetdir]
```


Note: if you want to replace files (to mod the game), it is not necessary to password protect the replacement files (so not having a modified minizip program also shouldn't be a problem)
## Post #19
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-05T02:32:36+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

It seems Dragon Marked for Death PC generates unique scrambling passwords for the save file based on the player's SteamID. The passwords used are last 32 bits of the SteamID as a hex number appended to the same old save data scrambling keys as seen in COTM1.

I updated the program in post [viewtopic.php?p=176034#p176034](https://forum.xentax.com/viewtopic.php?p=176034#p176034) with support for entering a SteamID on the command line for filetype save3.
## Post #20
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-06T03:32:20+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

Sorry, was busy.

So it's supposed to be mostly null characters? Uh, any idea what I should try and change?

It seems that in-game files and characters just don't exist in the save until you make them...
## Post #21
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-06T18:30:30+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from DMFDLancer ↑Tue Jul 06, 2021 11:32 am at Tue Jul 06, 2021 11:32 am
>
> So it's supposed to be mostly null characters?

That's corrrect. It's also the case in COTM/COTM2.

> Reply from DMFDLancer ↑Tue Jul 06, 2021 11:32 am at Tue Jul 06, 2021 11:32 am
>
> Uh, any idea what I should try and change?

None whatsoever.  But to get started, you may try this:

1. make a backup copy of the save file
2. change settings or do something (progress) in the game
3. exit game and compare backup with new save file

However, it's very likely that the save file is checksummed, so any modifications would require knowledge of where the checksum is stored and how it is calculated. (you'll see if the game always says your savefile is corrupted whenever you make changes, or just discards the savefile) If you just want to cheat in the game, it's a lot easier to just use a tool like Cheat Engine and change values runtime.

> Reply from DMFDLancer ↑Tue Jul 06, 2021 11:32 am at Tue Jul 06, 2021 11:32 am
>
> It seems that in-game files and characters just don't exist in the save until you make them...

Yeah most likely.
## Post #22
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-07T04:14:22+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

Welp, messed around and it's rejecting my modded save. That blows. I'd try more but it really feels like I'm getting nowhere fast.

Messing with Dragon specifically has always been weird... It loathes Cheat Engine and becomes unstable, it seems any progress with cheats was halted with the final patch, and tends to break saves if you tried anything.

In theory, I could decode somebody's save and make it my own. Just gotta find somebody willing to share lol

Edit: [https://github.com/piratesephiroth/DMFDSaveTool](https://github.com/piratesephiroth/DMFDSaveTool)

Huh, somebody made a save tool already. Dunno how this flew under my radar. Gonna try it later.
## Post #23
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-07-07T05:09:47+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from DMFDLancer ↑Wed Jul 07, 2021 12:14 pm at Wed Jul 07, 2021 12:14 pm
>
> Edit: https://github.com/piratesephiroth/DMFDSaveTool

Huh, somebody made a save tool already. Dunno how this flew under my radar. Gonna try it later.

Ah cool, would have saved me some effort if I knew about that earlier since it contains the Inti scrambling algo.

Perhaps some of the other info available from that tool's code could be applicable to COTM(2) as well, such as the checksumming. Hmm..!
## Post #24
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-10T16:15:31+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

[https://twitter.com/2612watts/status/14 ... 0794931201](https://twitter.com/2612watts/status/1413783640794931201)

Hey, did you see this? Or is this you?

The pics make it look like you can swap stages between BMZ2 and CotM2.
## Post #25
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-07-16T18:45:16+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

Found something, dunno how obvious or helpful it is.

[https://steamcommunity.com/app/1149440/ ... 013117636/](https://steamcommunity.com/app/1149440/discussions/0/2573194192013117636/)

Dragon Marked For Death seems to use Microsoft Visual C++ Runtime, as indicated by the error. I imagine all of the Steam ports use it?

Actually yeah, SteamDB says which versions they use. Dragon uses the 2019 version.
## Post #26
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-08-03T05:35:48+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

Hey, been a while.

BMZ3 dropped, and I wanna look through it. Do you need to update something, or need anything from me?
## Post #27
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-08-03T23:28:39+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from DMFDLancer ↑Sun Jul 11, 2021 12:15 am at Sun Jul 11, 2021 12:15 am
>
> Hey, did you see this? Or is this you? The pics make it look like you can swap stages between BMZ2 and CotM2.

Not me. Yeah, seems the stage format is compatible between games. You can do that (swap stages) on PC too if you look up the hashed filenames for both games.

> Reply from DMFDLancer ↑Tue Aug 03, 2021 1:35 pm at Tue Aug 03, 2021 1:35 pm
>
> BMZ3 dropped, and I wanna look through it. Do you need to update something, or need anything from me?

Game executable and some sample files with proper (not MD5 hashed) filenames. To get unhashed filenames, you'll either need to look at a console version of the game (at least so far all the games have had hashed filenames only on PC), or play PC version which has been patched to log filenames. I'll ask a few people if they already have the game.
## Post #28
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2021-08-15T18:07:40+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from xttl ↑Wed Aug 04, 2021 7:28 am at Wed Aug 04, 2021 7:28 am
>
> 
DMFDLancer wrote: ↑Sun Jul 11, 2021 12:15 amHey, did you see this? Or is this you? The pics make it look like you can swap stages between BMZ2 and CotM2.

Not me. Yeah, seems the stage format is compatible between games. You can do that (swap stages) on PC too if you look up the hashed filenames for both games.
DMFDLancer wrote: ↑Tue Aug 03, 2021 1:35 pmBMZ3 dropped, and I wanna look through it. Do you need to update something, or need anything from me?

Game executable and some sample files with proper (not MD5 hashed) filenames. To get unhashed filenames, you'll either need to look at a console version of the game (at least so far all the games have had hashed filenames only on PC), or play PC version which has been patched to log filenames. I'll ask a few people if they already have the game.
Hello. I've sent you a pm regarding BMZ3 and one other thing couple days ago.
On another note, pc version of Gunvolt Chronicles -  Luminous Avenger iX encrypts save files too, of course. I'm trying to possibly import my switch save data. The password I found in EXE seems to be this: "yC2YQDHx". It doesn't seem to be using the second password, or I didn't find it. Nor does it encrypt with the help of steamid. At least comparing to DMFD .exe. Could support be added for this one? I can send over my save data from PC and Switch version (switch doesn't look encrypted, extracted it with checkpoint app). Keep up the great work. : D
## Post #29
- Username: xttl
- Rank: n00b
- Number of posts: 15
- Joined date: Sun May 02, 2021 1:18 pm
- Post datetime: 2021-08-18T03:47:13+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from Kharaxel ↑Mon Aug 16, 2021 2:07 am at Mon Aug 16, 2021 2:07 am
>
> Hello. I've sent you a pm regarding BMZ3 and one other thing couple days ago.
On another note, pc version of Gunvolt Chronicles -  Luminous Avenger iX encrypts save files too, of course. I'm trying to possibly import my switch save data. The password I found in EXE seems to be this: "yC2YQDHx". It doesn't seem to be using the second password, or I didn't find it. Nor does it encrypt with the help of steamid. At least comparing to DMFD .exe. Could support be added for this one? I can send over my save data from PC and Switch version (switch doesn't look encrypted, extracted it with checkpoint app). Keep up the great work. : D

Yeah, I saw the PM. Been kind of busy with other (mostly non-computer) stuff.

So far all save files have been using double scrambling so my guess is this one does that too, but I haven't seen the executable so it's only a guess. Did you use Ghidra or IDA to check all calls to the password hashing / keygen functions but couldn't find another one which looks like it's being used together with the first? Or were you just looking at strings?

The next update of inti_encdec can read those "filetype" defs from a textfile so anyone can try new passwords and settings without a C compiler.
## Post #30
- Username: Kharaxel
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 29, 2008 8:56 pm
- Post datetime: 2021-08-18T13:52:26+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 stuff

> Reply from xttl ↑Wed Aug 18, 2021 11:47 am at Wed Aug 18, 2021 11:47 am
>
> 
Kharaxel wrote: ↑Mon Aug 16, 2021 2:07 amHello. I've sent you a pm regarding BMZ3 and one other thing couple days ago.
On another note, pc version of Gunvolt Chronicles -  Luminous Avenger iX encrypts save files too, of course. I'm trying to possibly import my switch save data. The password I found in EXE seems to be this: "yC2YQDHx". It doesn't seem to be using the second password, or I didn't find it. Nor does it encrypt with the help of steamid. At least comparing to DMFD .exe. Could support be added for this one? I can send over my save data from PC and Switch version (switch doesn't look encrypted, extracted it with checkpoint app). Keep up the great work. : D

Yeah, I saw the PM. Been kind of busy with other (mostly non-computer) stuff.

So far all save files have been using double scrambling so my guess is this one does that too, but I haven't seen the executable so it's only a guess. Did you use Ghidra or IDA to check all calls to the password hashing / keygen functions but couldn't find another one which looks like it's being used together with the first? Or were you just looking at strings?

The next update of inti_encdec can read those "filetype" defs from a textfile so anyone can try new passwords and settings without a C compiler.

Yeah, I was merely looking at strings. I actually have Ghidra, needed it a while back for some ue4 .pak password finding. I'll send over the .exe your way, though I'll also try to check this out myself. As a matter of fact, I might actually check with GV2 and 1 as well. And that update sounds very cool. Can't wait.
## Post #31
- Username: comfycookie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 23, 2021 9:36 am
- Post datetime: 2021-08-23T02:08:30+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

I am attempting to view the osb files from BMZ2 and there is nothing comprehensive visible in spite of the fact that I am using the settings for TiledGGD that were recommended. Is there a step I'm missing?

E: Actually this issue seems to only be with the character sprites... I was able to properly view the sprite of Planet A, albeit with some incorrect colors, but the sheets for Eve just seem to be a garbled mess
Edit 2: Nevermind it was just WAY wider than I thought it was, but the palette is not showing correctly
## Post #32
- Username: DMFDLancer
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 26, 2021 12:02 pm
- Post datetime: 2021-10-21T21:36:20+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

> Reply from comfycookie ↑Mon Aug 23, 2021 10:08 am at Mon Aug 23, 2021 10:08 am
>
> 
I am attempting to view the osb files from BMZ2 and there is nothing comprehensive visible in spite of the fact that I am using the settings for TiledGGD that were recommended. Is there a step I'm missing?

E: Actually this issue seems to only be with the character sprites... I was able to properly view the sprite of Planet A, albeit with some incorrect colors, but the sheets for Eve just seem to be a garbled mess
Edit 2: Nevermind it was just WAY wider than I thought it was, but the palette is not showing correctly

In some Inti games the pallet is handled on the fly, such as DMFD. Are they showing up as all black? You might need to color them manually with some kind of art program, preferably with a tool that can swap out the color on the entire picture.
## Post #33
- Username: DetonateGBF
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 27, 2022 6:49 pm
- Post datetime: 2022-01-27T11:03:26+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Hello I've recently bought luminous avenger ix2 and i'd like to know how to use the encoder with it. 
The executable for inti_encdec_v2d keeps closing whenever i try to open it.
## Post #34
- Username: SusCX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 8:19 pm
- Post datetime: 2022-01-30T13:28:27+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Also me too, i'm facing the same problem and all the files except some strange file in "Sounds" folder with ".bisar" extension, are strongly encrypted.
## Post #35
- Username: NotCafe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 28, 2019 9:45 am
- Post datetime: 2022-03-15T00:30:39+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

hello xttl, i really appreciate the work you have done so far, that said let me tell you i have search every ttb file and theres only text for some parts of the menu, now the intro text, dialogues (like when you rescue party members) and different endings are nowhere to be found
edit1: im referring to cotm1 just in case
## Post #36
- Username: RusselCS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 26, 2022 10:05 pm
- Post datetime: 2022-04-26T14:09:46+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Hey, I know this thread hasn't had much activity as of late, but I was wondering if there was any documentation on how the sound files worked for these games?
Trying to get clean sound rips for Mighty Gunvolt Burst, which appear to be in these .bigrp files, and I'm not sure where to begin when trying to decipher these files.

Any tips?
## Post #37
- Username: steventylerseanherr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 02, 2020 3:54 am
- Post datetime: 2022-04-27T23:10:34+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

not sure entirely but mgb uses sequenced music
afaik no one has created a working player for them yet
but i think i have seen a converter to convert it to midi though i think its flawed conversion
be nice to have some way to play these whenever cause i love mgb and mighty number 9 music
## Post #38
- Username: RusselCS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 26, 2022 10:05 pm
- Post datetime: 2022-05-17T03:46:58+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

Everything being sequenced might present a problem.
Once again, I'm not looking for OST rips. I'm looking for sounds.
Some sounds can be recorded by deleting the bigrp file for certain stages, thereby disabling the music and allowing them to be recorded cleanly... but other sounds are embedded within the bigrp file because these files also function as a soundbank for everything in that stage.

That has the potential to be a big roadblock for certain things on a project I'm working on.
If you're looking for the OST for Mighty Gunvolt Burst, though, it came in a CD with the collector's edition (Called Gal Gunvolt Burst) when it released on console.

Anyway, thanks for the info on these files being entirely sequenced. Might be helpful, but at this point might just be a roadblock.
## Post #39
- Username: DeepWeeb
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 12, 2019 7:13 am
- Post datetime: 2022-07-29T02:32:13+00:00
- Post Title: Re: Bloodstained: Curse of the Moon 1 & 2 (and other Inti Creates) stuff

I found about this just now because Gunvolt 3 came out, and thing is that the whole encryption thing has been a on-going issue, seems like Inti have become increasingly protective of their assets. First on PC you couldn't open the music files with Foobar2000 and then they went as far as to messing up the names of all of the files to be unreadable, and now it has bleed into their console releases as well.   

So, any easy explanation on how all of this works? And if it can be used on the Switch version of the games without a SteamID and without knowing the file list beforehand?
