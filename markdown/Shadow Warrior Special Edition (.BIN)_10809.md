## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-26T20:13:14+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Passwored zip's

PWD: @#viSS1t_*wWW.flY1nG!W1Ld&H0gR0X.c0M^!
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2013-09-26T20:26:56+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Hell yeah Ekey you are rock.
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-10-04T16:32:10+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

[http://www.fly1ngw1ldh0gr0x.com/](http://www.fly1ngw1ldh0gr0x.com/)

Polish registrant.. thats neat! maybe they're planning an arg for their next game?
## Post #4
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-05-07T18:13:49+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Hey guys, I have successfully extracted the BIN files, and am looking to get the models inside into 3ds max. Problem is, they're in the havok format, of the havok game engine. Are there any tools or scripts that can convert these models into something workable in 3ds max?
## Post #5
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-08T17:08:14+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

> Reply from Pepper
>
> http://www.fly1ngw1ldh0gr0x.com/

Polish registrant.. thats neat! maybe they're planning an arg for their next game?
Thx!


=)
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-05-10T19:19:20+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

> Reply from Haoose
>
> Pepper wrote:http://www.fly1ngw1ldh0gr0x.com/

Polish registrant.. thats neat! maybe they're planning an arg for their next game?
Thx!


=)

Oh nice they updated it! before it said they'd be adding something special at some point after being found. anyways it's way fun, have a blast!
## Post #7
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-05-10T19:51:47+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Pepper
For six months no one before me had not taken the key. It is a great fortune. Well it's someone who [can write about it](https://twitter.com/Haoose/status/464455740762365952), and the key is not left in an unknown direction. Thank you, Ekey and developers! =)
## Post #8
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-06-02T11:01:08+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Lol
New key =)
[](http://makescreen.ru/i/cde07f1691bcc2109791546b98c851.jpg)
[](http://makescreen.ru/i/a7817110bd069a427d556eb587a641.jpg)
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-02T19:49:04+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Yep actived by me 5 days ago ;p
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-06-07T11:29:22+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

New key for Hard Reset. I have already this maybe useful for someone  47VRG-JNFGT-5NAE5
## Post #11
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2014-06-24T20:25:11+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

New key...
## Post #12
- Username: rolemodel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 28, 2014 7:05 pm
- Post datetime: 2014-10-28T11:09:29+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

Yes has anyone figured out how to open the hxk file types of the meshes?   The method I've seen that works for hkx files like skyrim I don't find working.   the hkxcmd command prompt program is the only one I've used and it never creates anything(no kf files).
## Post #13
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2015-04-01T11:10:16+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

any idea how to extract new dx11 archives?
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-05-03T13:51:16+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

```
# BIN extractor (for game version 1.5.0)
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

comtype zlib
get FILES long
savepos POS
math DATSTART = 0x4
for i = 0 < FILES
  get NAMESZ long
  xmath DATSTART "DATSTART + NAMESZ + 0x1C"
  goto DATSTART  
next i
math DATSTART += 0x4
goto POS
for j = 0 < FILES
  get NAMESZ long
  getdstring NAME NAMESZ
  get SIZE long
  get ZSIZE long
  get OFFSET long
  xmath OFFSET "DATSTART + OFFSET"
  get NULL long
  getdstring UNK 0x8
  clog NAME OFFSET ZSIZE SIZE
next j

```


Extraction is easy. But repacker would be great. 
Have somebody a clue what are that 8 UNK bytes? Checksum / hash? Some files has the same "UNK" bytes. Example:

```
data/localisation_unicode/cn/bossfights.uni		D8 12 42 C5 E4 54 D0 01
data/localisation_unicode/cn/chapter_name.uni		1C 66 63 C5 E4 54 D0 01
data/localisation_unicode/cn/checkpoints.uni		1C 66 63 C5 E4 54 D0 01
data/localisation_unicode/cn/comic.uni			D8 12 42 C5 E4 54 D0 01
data/localisation_unicode/cn/dialogs_and_objectives.uni	1C 66 63 C5 E4 54 D0 01
...
data/localisation_unicode/pl/achievements.uni		C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/bossfights.uni		C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/chapter_name.uni		43 2C BA C6 E4 54 D0 01
data/localisation_unicode/pl/checkpoints.uni		43 2C BA C6 E4 54 D0 01
data/localisation_unicode/pl/comic.uni			C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/dialogs_and_objectives.uni	43 2C BA C6 E4 54 D0 01
...
data/localisation_unicode/ru/achievements.uni		85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/bossfights.uni		85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/chapter_name.uni		45 37 CD C6 E4 54 D0 01
data/localisation_unicode/ru/checkpoints.uni		45 37 CD C6 E4 54 D0 01
data/localisation_unicode/ru/comic.uni			85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/dialogs_and_objectives.uni	A6 98 CF C6 E4 54 D0 01

```


pc_arch_scripts.bin

```
http://www28.zippyshare.com/v/34GNR4uM/file.html
```
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-05-03T14:12:18+00:00
- Post Title: Shadow Warrior: Special Edition (*.BIN)

it seems that it is just uint64 ID, nothing else..., but not sure
## Post #16
- Username: tsl16b
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Dec 27, 2010 8:16 pm
- Post datetime: 2015-05-10T01:39:04+00:00
- Post Title: Re: Shadow Warrior: Special Edition (*.BIN)

Here's my try:

```
# script for QuickBMS http://quickbms.aluigi.org

get			FilesCount		long
savepos		DirStart

for i = 0 < FilesCount
 get			FileNameLength		long
 getdstring	FileNameStr		FileNameLength
 get			UncompressedSize	long
 get			CompressedSize		long
 get			StartPos		longlong
 get			FileTime		time64
 print		"%FileTime% %FileNameStr%"
next i
```

It would be great to touch file date somehow to a specified value in a TIME64 on the file created by CLog.
## Post #17
- Username: siSINka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 24, 2014 11:46 pm
- Post datetime: 2015-05-19T19:51:04+00:00
- Post Title: Re: Shadow Warrior: Special Edition (*.BIN)

Anybody knows where are fonts for DX11 version?
## Post #18
- Username: [HYBRID BEING]
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 15, 2015 4:14 am
- Post datetime: 2015-09-14T20:56:24+00:00
- Post Title: Re: Shadow Warrior: Special Edition (*.BIN)

Was trying to get Hoji's mask into usable format. No success. Was able to view model in Havok Standalone Tool though.



Clipboard 1.png (207.04 KiB) Viewed 190 times


I upgraded both hoji_mask_cs.hkx and animation/idle.hkx to version hk_2010.2.0-r1 (original version Havok-6.6.0-r1), and model opened in Havok Tool just fine, even loaded the textures (although, for some reason i don't know, mirrored upside down). Next tried using hkxcmd extractkf, but this generated 1KB file, which obviously i wasn't able to import into 3D Max. I also tried upgrading files to hk_2012.2.0-r1 and convert to SMD with hktcnv, but it just crashed with IndexOutOfRangeException.
## Post #19
- Username: bekir007
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 02, 2012 8:52 pm
- Post datetime: 2016-04-02T12:16:54+00:00
- Post Title: Re: Shadow Warrior: Special Edition (*.BIN)

> Reply from merlinsvk
>
> Code: Select all# Game: Shadow Warrior (PC)
# BIN extractor (for game version 1.5.0)
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

comtype zlib
get FILES long
savepos POS
math DATSTART = 0x4
for i = 0 < FILES
  get NAMESZ long
  xmath DATSTART "DATSTART + NAMESZ + 0x1C"
  goto DATSTART  
next i
math DATSTART += 0x4
goto POS
for j = 0 < FILES
  get NAMESZ long
  getdstring NAME NAMESZ
  get SIZE long
  get ZSIZE long
  get OFFSET long
  xmath OFFSET "DATSTART + OFFSET"
  get NULL long
  getdstring UNK 0x8
  clog NAME OFFSET ZSIZE SIZE
next j


Extraction is easy. But repacker would be great. 
Have somebody a clue what are that 8 UNK bytes? Checksum / hash? Some files has the same "UNK" bytes. Example:
Code: Select alldata/localisation_unicode/cn/achievements.uni		D8 12 42 C5 E4 54 D0 01
data/localisation_unicode/cn/bossfights.uni		D8 12 42 C5 E4 54 D0 01
data/localisation_unicode/cn/chapter_name.uni		1C 66 63 C5 E4 54 D0 01
data/localisation_unicode/cn/checkpoints.uni		1C 66 63 C5 E4 54 D0 01
data/localisation_unicode/cn/comic.uni			D8 12 42 C5 E4 54 D0 01
data/localisation_unicode/cn/dialogs_and_objectives.uni	1C 66 63 C5 E4 54 D0 01
...
data/localisation_unicode/pl/achievements.uni		C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/bossfights.uni		C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/chapter_name.uni		43 2C BA C6 E4 54 D0 01
data/localisation_unicode/pl/checkpoints.uni		43 2C BA C6 E4 54 D0 01
data/localisation_unicode/pl/comic.uni			C2 A6 B0 C6 E4 54 D0 01
data/localisation_unicode/pl/dialogs_and_objectives.uni	43 2C BA C6 E4 54 D0 01
...
data/localisation_unicode/ru/achievements.uni		85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/bossfights.uni		85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/chapter_name.uni		45 37 CD C6 E4 54 D0 01
data/localisation_unicode/ru/checkpoints.uni		45 37 CD C6 E4 54 D0 01
data/localisation_unicode/ru/comic.uni			85 74 C8 C6 E4 54 D0 01
data/localisation_unicode/ru/dialogs_and_objectives.uni	A6 98 CF C6 E4 54 D0 01


pc_arch_scripts.bin
Code: Select allhttp://www28.zippyshare.com/v/34GNR4uM/file.html
isn't there anybody that can repack? if i use this script for repack, game (dx11) crashes.
## Post #20
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2016-04-02T13:18:26+00:00
- Post Title: Re: Shadow Warrior: Special Edition (*.BIN)

Here, my BIN packer, made in AutoIT.

[http://www65.zippyshare.com/v/4kXkNyYT/file.html](http://www65.zippyshare.com/v/4kXkNyYT/file.html)
