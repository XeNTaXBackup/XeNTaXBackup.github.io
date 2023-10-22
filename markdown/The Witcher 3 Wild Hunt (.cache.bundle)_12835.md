## Post #1
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-05-12T06:20:17+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

Samples below :-

```
http://www.solidfiles.com/d/c7620a6bdb/Witch3.7z
```


Please take a loot at the archives !
## Post #2
- Username: Skykila
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-05-12T07:29:36+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

```
http://aluigi.org/papers/bms/others/witcher3.bms
```
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-12T07:40:40+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from ShivShubh
>
> Please take a loot at the archives !I surely will NOT. Neither "loot" nor look.
The loader (*.exe, downloader Morstar?) from that page is (or contains or loads) a PUP



Witch3.7z.exe-virus.JPG (82.19 KiB) Viewed 726 times



edit: 
```
This software is not a virus or a Trojan. It is detected as a "potentially unwanted program" (PUP). PUPs are any piece of software that a reasonably security- or privacy-minded computer user may want to be informed of and, in some cases, remove. PUPs are often made by a legitimate corporate entity for some beneficial purpose, but they alter the security state of the computer on which they are installed, or the privacy posture of the user of the system, such that most users will want to be aware of them.
```
## Post #4
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-05-12T08:31:34+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

@shakotay2, mate you have click on wrong download link that's why it gave you an exe file to download instead of an 7z file.

BTW thanks @Michaelss for the bms link !

edit: bms script seems to work only with .bundle files

any way out for .cache files ?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-12T08:47:49+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from ShivShubh
>
> @shakotay2, mate you have click on wrong download link that's why it gave you an exe file to download instead of an 7z file.and you, mate, are contributing spreading PUPs:



howTpSpreadPUPs.JPG (13.54 KiB) Viewed 715 times



There are dozens of file hosters that do not.
Why not use them?
## Post #6
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2015-05-12T09:08:41+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

Anyone found the location of localization files. I'd like to get started on that.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-12T09:57:14+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from stalja
>
> Anyone found the location of localization files. I'd like to get started on that.speaking of which?
*.w2strings or *.sqlite not contained in blob.bundle.

cutscenes not to be loaded into W2 cutscenes editor:
Version 162 is not supported. Highest supported version is 115. 
Failed to load '..\cs001_little_ciri_intro\cs001_little_ciri_intro.w2cutscene'.

No usable w2mesh files found.

This is what I could retrieve:



cave_entrance_proxy_d.jpg (98.48 KiB) Viewed 701 times
## Post #8
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2015-05-12T12:01:13+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

anyone found ingame zone maps textures?

shakotay2: how did you convert w3 texture (wbx?) to dds?

is w2 redkit working with w3 files?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-12T14:51:21+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from Lord Vaako
>
> shakotay2: how did you convert w3 texture (wbx?) to dds?just loading a DXT1 without a header (it was an xbm texture file).

> is w2 redkit working with w3 files?AFAICS it does not with the files I tested (w2mesh, w2cutscene, w2scene).
("Warning	Version 162 is not supported.")

(When faking them from version 0xA2 to version 0x59 or 0x73 the REDkit crashed to desktop.)
## Post #10
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2015-05-12T16:40:59+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from shakotay2
>
> just loading a DXT1 without a header (it was an xbm texture file).
One more noob question  - so I have to strip xbm header and add dds one? Am I right or wrong?

is this xbm file?

```
00000010h: 69 38 FB 02 92 C5 0D 00 5A 05 00 00 5A 05 00 00 ; i8ű.’Ĺ..Z...Z...
00000020h: 3F 67 A6 90 06 00 00 00 A0 00 00 00 9E 00 00 00 ; ?g¦.... ...ž...
00000030h: 98 E3 DA A2 3E 01 00 00 0E 00 00 00 B6 CE 0F 56 ; ăÚ˘>.......¶Î.V
00000040h: 00 00 00 00 00 00 00 00 00 00 00 00 AE 01 00 00 ; ............®...
00000050h: 01 00 00 00 55 4B BB EC BE 01 00 00 01 00 00 00 ; ....UK»ěľ.......
00000060h: CB 46 96 44 00 00 00 00 00 00 00 00 00 00 00 00 ; ËF–D............
00000070h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ; ................
00000080h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ; ................
00000090h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ; ................
000000a0h: 00 43 42 69 74 6D 61 70 54 65 78 74 75 72 65 00 ; .CBitmapTexture.
000000b0h: 77 69 64 74 68 00 55 69 6E 74 33 32 00 68 65 69 ; width.Uint32.hei
000000c0h: 67 68 74 00 63 6F 6D 70 72 65 73 73 69 6F 6E 00 ; ght.compression.
000000d0h: 45 54 65 78 74 75 72 65 43 6F 6D 70 72 65 73 73 ; ETextureCompress
000000e0h: 69 6F 6E 00 54 43 4D 5F 44 58 54 4E 6F 41 6C 70 ; ion.TCM_DXTNoAlp
000000f0h: 68 61 00 74 65 78 74 75 72 65 47 72 6F 75 70 00 ; ha.textureGroup.
00000100h: 43 4E 61 6D 65 00 43 68 61 72 61 63 74 65 72 44 ; CName.CharacterD
00000110h: 69 66 66 75 73 65 00 72 65 73 69 64 65 6E 74 4D ; iffuse.residentM
00000120h: 69 70 49 6E 64 65 78 00 55 69 6E 74 38 00 74 65 ; ipIndex.Uint8.te
00000130h: 78 74 75 72 65 43 61 63 68 65 4B 65 79 00 00 00 ; xtureCacheKey...
00000140h: 00 00 00 00 00 00 01 00 00 00 08 E5 88 5B 10 00 ; ...........ĺ[..
00000150h: 00 00 CD 5A 32 83 16 00 00 00 64 6D 59 16 1D 00 ; ..ÍZ2....dmY...
00000160h: 00 00 E6 C8 AD BB 24 00 00 00 AF 56 47 9D 30 00 ; ..ćČ­»$...ŻVGť0.
00000170h: 00 00 41 72 E0 07 44 00 00 00 E3 00 C5 57 53 00 ; ..Arŕ.D...ă.ĹWS.

...

00000520h: 57 55 4C 2A CC 01 55 55 5E 53 8D 2A CC 01 5D 71 ; WUL*Ě.UU^SŤ*Ě.]q
00000530h: 69 4D 6D 2A CB 01 51 51 55 55 8D 2A CB 01 45 65 ; iMm*Ë.QQUUŤ*Ë.Ee
00000540h: 7D 55 0C 1A AB 01 CF 2C 34 EF EB 09 CC 09 03 A9 ; }U..«.Ď,4ďë.Ě..©
00000550h: A9 A9 CB 09 CB 09 00 00 00 00                   ; ©©Ë.Ë.....

```
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-12T19:31:38+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from Lord Vaako
>
> so I have to strip xbm header and add dds one?yep

> is this xbm file?looks like. Dunno why you posted the hex data since it should be clear from the file extension which is *.xbm for TheWitcher2 textures and for the ones from W3 in the blob.bundle, too.
## Post #12
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2015-05-12T21:40:00+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

I tried 3 different scripts to convert xbm (found inside W3 blob.bundle) -> dds but none of them work for me 
Could you share your script/solution/more details shakotay2?
Thanks in advance
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-13T06:25:19+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from Lord Vaako
>
> Could you share your script/solution/more details shakotay2?
Thanks in advanceMy solution is a modified DDSWithoutD3DX11.exe (D3D SDK) but it can't add headers atm (button Sxxx without function) so it won't help you.

Here's a modified xbm file from the blob.bundle:


 cave_entrance_proxy_d.zip
(24.12 KiB) Downloaded 59 times
## Post #14
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2015-05-13T07:30:48+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

Concerning XBM - from what I'm seeing it consists of 5 parts: Header, variable list, data1, data2, texture.


Edit: I am apparently wrong ...

I was looking at \environment\architecture\human\common\basement\textures\arc_basement01.xbm and the following seemed to make sense

Header offset 58 holds the address of data2 block in little endian. Data2 block is x bytes long. Second to last 4 bytes (meaning - offset (len(data2)-8) of data2 block) holds the length of texture data. I am guessing the last data is DDS texture without header.

shakotay2 discovered a texture which has the same data structure with data2 block being of different size than the one I was looking at. I am yet to determine how length of data2 is calculated (based on the variable list maybe?)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-13T12:37:01+00:00
- Post Title: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from stalja
>
> I am yet to determine how length of data2 is calculated (based on the variable list maybe?)this "data2" block seems to contain a bunch of string table indices which are used to define/group variables/datatypes maybe like this:
width  Uint32 (textureGroup?)
height Uint32 (textureGroup?)

TCM_DXTNoAlpha textureGroup
CName ETextureCompression 

WorldDiffuse residentMipIndex Uint8 
textureCacheKey Uint32 (textureGroup?)

edit: ok, that's not fully correct. It should be something like "textureGroup: WorldDiffuse" for example

In fact it should give some kind of struct type for CBitmapTexture:



struct-CBitmapTexture.JPG (23.72 KiB) Viewed 598 times

W2 xbm - although it's a Z:\W3_Assets folder (from march 2013)
## Post #16
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-16T02:34:37+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

almost all .xbm files contain only a small preview image. the rest textures are in content?\texture.cache. 
here are a couple of scripts to extract the data — [https://github.com/hhrhhr/Lua-utils-for-Witcher-3](https://github.com/hhrhhr/Lua-utils-for-Witcher-3) , needed Lua 5.3 and lua-zlib.

some maps from game (extracted, merged from tiles, cropped and optimized):
[](https://mega.co.nz/#F!yphkSDzC!9e4ko2SOFimiFY-w5xYJww)
## Post #17
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2015-05-18T22:57:03+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

String files came with the release of the game. Anyone has any info on how to approach the new w3strings format?
## Post #18
- Username: dubh
- Rank: n00b
- Number of posts: 13
- Joined date: Mon May 23, 2011 4:34 pm
- Post datetime: 2015-05-18T23:54:21+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

The .redscripts format is also different from the .w2scripts format.

edit: Someone make a repacker for .bundle files please.
## Post #19
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-19T19:36:16+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> almost all .xbm files contain only a small preview image. the rest textures are in content?\texture.cache. 
here are a couple of scripts to extract the data — https://github.com/hhrhhr/Lua-utils-for-Witcher-3 , needed Lua 5.3 and lua-zlib.

some maps from game (extracted, merged from tiles, cropped and optimized):

Getting an error when I try to unpack.

```
stack traceback:
	[C]: in function 'string.unpack'
	./mod_dds_header.lua:25: in local 'MAKEFOURCC'
	./mod_dds_header.lua:28: in main chunk
	[C]: in function 'require'
	./unpack_textures.lua:3: in main chunk
	[C]: in ?

```
## Post #20
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-19T19:50:28+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from stalja
>
> String files came with the release of the game. Anyone has any info on how to approach the new w3strings format?
I think that the files are very simple, but the contents is just xor-ed. look at any br.w3strings, inside there is almost clean text (UTF16 with some html tags).

> Reply from designgears
>
> Getting an error when I try to unpack.
full command line?
## Post #21
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-19T19:56:02+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> designgears wrote:Getting an error when I try to unpack.
full command line?

lua ./unpack_textures.lua texture.cache unpack
## Post #22
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-19T20:24:46+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

I think that you are using the wrong Lua. try to test:

```
Lua 5.3
> lua -e "print(string.unpack('<L', '\xD2\x02\x96\x49'))"
1234567890      5
```
## Post #23
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-19T20:33:13+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> I think that you are using the wrong Lua. try to test:
Code: Select all> lua -e "print(_VERSION)"
Lua 5.3
> lua -e "print(string.unpack('<L', '\xD2\x02\x96\x49'))"
1234567890      5

Odd, I have 5.3 installed. I get the same error with your test.
## Post #24
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-19T21:08:10+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

"<L " means ["native sized little endian unsigned long"](http://www.lua.org/manual/5.3/manual.html#6.4.2). maybe you are using a big endian or/and 16-bit platform?

let's try one byte:

```
255     2
```
## Post #25
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-19T21:48:21+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> "<L " means "native sized little endian unsigned long". maybe you are using a big endian or/and 16-bit platform?

let's try one byte:
Code: Select alllua -e "print(string.unpack('B', '\xFF'))
255     2

That works.

I am running Fedora 64bit on virtualbox.
## Post #26
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-19T22:01:25+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

I can only advise to try all conversion options from here ([http://www.lua.org/manual/5.3/manual.html#6.4.2](http://www.lua.org/manual/5.3/manual.html#6.4.2)) with string "DXT1", for example, find inoperative and inform maintainer of lua package.
## Post #27
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-20T00:38:14+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> I can only advise to try all conversion options from here (http://www.lua.org/manual/5.3/manual.html#6.4.2) with string "DXT1", for example, find inoperative and inform maintainer of lua package.

Well, it even fails on their demo page.

[http://www.lua.org/cgi-bin/demo](http://www.lua.org/cgi-bin/demo)

Very annoying.
## Post #28
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-20T01:04:08+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

use "<I4" instead of "<L".

> I[n]: an unsigned int with n bytes (default is native size)
## Post #29
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-20T01:10:44+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> use "<I4" instead of "<L".

> I[n]: an unsigned int with n bytes (default is native size)

Ahh, that seems to have done the trick!
## Post #30
- Username: designgears
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu May 01, 2014 4:34 am
- Post datetime: 2015-05-20T02:08:38+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> use "<I4" instead of "<L".

> I[n]: an unsigned int with n bytes (default is native size)

This does work, but the files that come out aren't valid dds files.

edit---

Ahh, needed to change <L below too.
## Post #31
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-20T02:35:04+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

just in case, to inform you that I have no crystal ball to guess the desire and the contents of incorrect files.
## Post #32
- Username: kalleoskar
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Dec 25, 2008 10:17 pm
- Post datetime: 2015-05-20T21:41:29+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

repack possible with same script? ty
## Post #33
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2015-05-21T11:28:26+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from hhrhhr
>
> stalja wrote:String files came with the release of the game. Anyone has any info on how to approach the new w3strings format?
I think that the files are very simple, but the contents is just xor-ed. look at any br.w3strings, inside there is almost clean text (UTF16 with some html tags).
designgears wrote:Getting an error when I try to unpack.
full command line?

Not a simple XOR. They are probably using a hash/key. Anyone around that is able to make an unpacker/repacker for this?
## Post #34
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-05-21T14:44:59+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

"unpacker" [is quite simple](https://github.com/hhrhhr/Lua-utils-for-Witcher-3/blob/master/inspect_w3strings.lua), but the decoder - not yet. and yes, strings [are not just xored](http://zenhax.com/viewtopic.php?f=9&t=964).
## Post #35
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-05-22T10:26:15+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Anyone figured out how to open .buffer files
## Post #36
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-05-22T17:21:15+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

witcher3.map for 1.0.2
Maybe helps =)
[http://rghost.ru/private/7VSl9kGzJ/f1a2 ... e5039d546d](http://rghost.ru/private/7VSl9kGzJ/f1a2a962690a5baa7a6977e5039d546d)
## Post #37
- Username: nav00811
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Dec 21, 2014 7:49 pm
- Post datetime: 2015-05-24T07:55:03+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Haoose Just wanted to ask that how to use witcher.map file...
## Post #38
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2015-05-24T17:15:10+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Anyone checked the models from game? Similar format with W2 ones?
## Post #39
- Username: slayer983
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jun 30, 2012 4:26 am
- Post datetime: 2015-05-31T16:05:28+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Mod mod mod, all works about with this files. This is boring and some people dislikes from mods. anybody coder not dealing with Localization files, .w3strings files.
## Post #40
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-06-02T17:06:41+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

someone try extract 3d models/textures?
## Post #41
- Username: NuclearTester
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 06, 2015 11:14 am
- Post datetime: 2015-06-06T03:27:53+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Captured some textures and found that plant life textures look very interesting. I wonder what purpose all that smudging around the texture serves. Any idea?
## Post #42
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-06-06T10:28:27+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from NuclearTester
>
> Captured some textures and found that plant life textures look very interesting. I wonder what purpose all that smudging around the texture serves. Any idea?

Nothing particular. Just how many artists do textures for small, detailed meshes like hair or, in this case, foliage. An alpha channel will hide the excess (the "smudges").
## Post #43
- Username: NuclearTester
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 06, 2015 11:14 am
- Post datetime: 2015-06-06T19:35:21+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from ssringo
>
> NuclearTester wrote:Captured some textures and found that plant life textures look very interesting. I wonder what purpose all that smudging around the texture serves. Any idea?

Nothing particular. Just how many artists do textures for small, detailed meshes like hair or, in this case, foliage. An alpha channel will hide the excess (the "smudges").

No, this doesn't look accidental and it's obvious to me that the process serves some purpose. So my question still stands why textures for small detailed meshes with transparency are done this way.
## Post #44
- Username: romainoir
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 07, 2015 7:06 am
- Post datetime: 2015-06-06T23:11:39+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Most of the time we make a selection of the alpha channel (transparency) and then blur the edges in a second layer. This methods prevents from small artifacts on the edges.
My question is : which kind of image do you get ? (.dds/.tif/.tga/...) and can you repack them in the archive ?
## Post #45
- Username: NuclearTester
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 06, 2015 11:14 am
- Post datetime: 2015-06-07T00:26:50+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Thanks for explanation. That makes sense. Unfortunately, I don't know how to unpack/repack. It's possible to get any texture/object/shader with this handy tool: [http://developer.amd.com/tools-and-sdks ... erfstudio/](http://developer.amd.com/tools-and-sdks/graphics-development/gpu-perfstudio/)
## Post #46
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-06-07T00:42:50+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from NuclearTester
>
> Unfortunately, I don't know how to unpack/repack
1) [viewtopic.php?p=106145#p106145](http://forum.xentax.com/viewtopic.php?p=106145#p106145)
2) [https://github.com/hhrhhr/Lua-utils-for-Witcher-3](https://github.com/hhrhhr/Lua-utils-for-Witcher-3)
3) lua unpack_textures.lua texture.cache output_dir
4) profit
## Post #47
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2015-06-07T07:37:07+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

character parts replacment. know how to do?
## Post #48
- Username: ilmarvolken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 13, 2015 3:43 am
- Post datetime: 2015-06-12T20:07:56+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Hi all. Do anyone know where to get quickBMS scripts for witcher3 (like w2_xbm2dds.bms, w2_dds2xbm.bms for witcher2) to unpack/pack .xbm texture files of witcher3?
## Post #49
- Username: stiffy360
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 11, 2014 11:17 am
- Post datetime: 2015-06-29T14:58:56+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from NuclearTester
>
> ssringo wrote:NuclearTester wrote:Captured some textures and found that plant life textures look very interesting. I wonder what purpose all that smudging around the texture serves. Any idea?

Nothing particular. Just how many artists do textures for small, detailed meshes like hair or, in this case, foliage. An alpha channel will hide the excess (the "smudges").

No, this doesn't look accidental and it's obvious to me that the process serves some purpose. So my question still stands why textures for small detailed meshes with transparency are done this way.

When a texture mipmaps pixels tend to bleed over, so they smudge the base texture around the edges of the alpha channel so when they bleed they are of a similar color. If you have black or white on the edges, and move far away from the branch, it'll bleed over black/white.
## Post #50
- Username: Alianin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 28, 2012 12:07 am
- Post datetime: 2015-07-06T22:58:04+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

I'm not sure what I'm missing here. I'm trying to unpack the textures.cache, but I'm getting this error:

```
lua: unpack_textures.lua:109: '=' expected near 'skip'
```

I'm using the latest Lua-utils-for-Witcher-3.
## Post #51
- Username: hhrhhr
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Mar 18, 2010 2:02 pm
- Post datetime: 2015-07-06T23:24:33+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

> Reply from Alianin
>
> Code: Select alllua: unpack_textures.lua:109: '=' expected near 'skip'
Your Lua does not support goto statement.
## Post #52
- Username: UT1987
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 13, 2015 5:40 am
- Post datetime: 2015-07-12T21:52:20+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Hi guys,

i try to extract the textures for learning the speedtree (LOD, MatIDs Billboard (distance + streaming) and the Terrain shadows maps and Pigment maps.
Unfortunately I have no idea how works lua scripting. I try it with the lua demo programs but the failed to compile with this comment: input:1: unexpected symbol near '@'

How can i install lua language correctly on my pc with this batch tool?

regards,
ulrich


@ok is done
## Post #53
- Username: ssringo
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-08-14T11:44:20+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

The Witcher 3: Wild Hunt now with the mod support
[http://thewitcher.com/news/view/1094](http://thewitcher.com/news/view/1094)

Download Witcher_3-Modkit:
[http://filedelivery.nexusmods.com/Misc/ ... da68d1a8af](http://filedelivery.nexusmods.com/Misc/Witcher_3-Modkit.zip?ttl=2147483647&setec=78d94d62ba63789b37da8eda68d1a8af)
## Post #54
- Username: jediyoshi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 11, 2014 3:15 pm
- Post datetime: 2015-08-15T05:44:19+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Is there no actual mesh for the eyes? Not seeing anything but textures
## Post #55
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2015-08-17T00:08:52+00:00
- Post Title: Re: The Witcher 3 Wild Hunt (*.cache*.bundle)

Looked at a couple models and it seems like the tools convert meshes with bones and weights. However, it seems like bone parenting data doesn't export with the meshes (or doesn't exist at all). Assuming the bones/weights did export properly, putting the skeleton's together will be rather time consuming with what we have now. Hopefully someone can use what CDPR has released and get a good, proper tools for converting models.
