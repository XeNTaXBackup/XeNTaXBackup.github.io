## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-31T14:32:32+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

Unpacker v0.0.4 r7
Download: [here](https://www.sendspace.com/file/tx4s0d)

Supported games
* Anomaly 2
* Anomaly: Korea
* Anomaly: Warzone Earth
* Anomaly: Warzone Earth - Mobile Campaign
* Anomaly: Defenders
* This War of Mine

Packer v0.0.2 r3
Download: See attach

Warning : Make backup of original archives.

Result
Edited file l01n.bin (Language pack)



Have fun 
[BSPacker_0.0.2.r3.7z](https://xentaxbackup.github.io/file/8394_BSPacker_0.0.2.r3.7z)
## Post #2
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-05-24T00:55:55+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

Excellent, thank you. I wanted to unpack the intro videos.
## Post #3
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-09-18T21:57:10+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

I user ASDATPacker to repack audio files of Anomaly 2, but it's not work in game!! no audio plays!
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-01T21:58:19+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from sarzamin
>
> I user ASDATPacker to repack audio files of Anomaly 2, but it's not work in game!! no audio plays!
Packer for experemental

> Unpacker updated to 0.0.3 r6 > added names for Defenders serie.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-15T21:45:49+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

Base list updated for game > This War of Mine (1st post)
## Post #6
- Username: michanlew
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 29, 2012 8:21 am
- Post datetime: 2014-11-18T09:09:57+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> Base list updated for game > This War of Mine
Good day! Prompt if possible to open and edit textures This War of Mine  .texture ?? Thank you. Sorry for my English.
## Post #7
- Username: sirmabus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 12:14 pm
- Post datetime: 2014-11-21T10:23:34+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

Thanks for this. 
Better then nothing but with the latest "This War of Mine" data file your unpacker misses are large percent of them.

Any chance you have a new version, release your source code, and, or update it?

Thanks,
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-21T14:10:51+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from sirmabus
>
> 
Better then nothing but with the latest "This War of Mine" data file your unpacker misses are large percent of them.
What you mean?
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-21T15:07:22+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> What you mean?

Filenames.list probably.
## Post #10
- Username: sirmabus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 12:14 pm
- Post datetime: 2014-11-21T18:36:26+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

Yea, hard to say. Could be just the file names as many are going to to the "__Unknown" folder.
Works but since there are so many files, some binary, some text, it's some work to sort them out.

Are all the names explicitly in those ".idx" files?

For now just inject a DLL ro sump file type I want as it loads in "This War of Mine.exe"
I see at least one section of it uses zlib "1.2.3" (at least for the game save files).
Maybe later I'll dig in and figure out the format like you do. Thanks.
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-11-21T18:45:55+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from merlinsvk
>
> Filenames.list probably.
Well in base list only those names that i could find.
## Post #12
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-11-22T00:08:09+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> merlinsvk wrote:Filenames.list probably.
Well in base list only those names that i could find.

Anyone know how to edit .binfont and where is text's location? Thanks!
## Post #13
- Username: sirmabus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 29, 2011 12:14 pm
- Post datetime: 2014-11-22T08:31:28+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

I just hook 0x6E4320 (AFAIK current game exe) lua_load() to dump the Lua text files.
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-22T11:37:12+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from namquang93
>
> 
Anyone know how to edit .binfont and where is text's location? Thanks!

Texts are in common.dat as l10n.bin file. And I've tried to make converter to .binfont, but I can't figure out how long is the header, and what resolution is correct. And what's even worse, there are 300+ font textures, most of them are nonamed (only hash). :-/
## Post #15
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-11-22T12:33:55+00:00
- Post Title: 11 Bit Studios Games  (*.DAT)

> Reply from merlinsvk
>
> namquang93 wrote:
Anyone know how to edit .binfont and where is text's location? Thanks!

Texts are in common.dat as l10n.bin file. And I've tried to make converter to .binfont, but I can't figure out how long is the header, and what resolution is correct. And what's even worse, there are 300+ font textures, most of them are nonamed (only hash). :-/

So difficult to translate!
## Post #16
- Username: globeioi
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Feb 26, 2012 7:31 pm
- Post datetime: 2014-11-22T16:17:18+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

anyone know l01n.bin structure or l01n.bin convert to text file?
## Post #17
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2014-11-23T12:07:46+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Hi i tried to unpack and pack again the file scenes.dat from "Anomaly Defenders"  and now the game won't start i updated the filelist too

Any hint?

Thanks
## Post #18
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-11-23T12:42:06+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from globeioi
>
> anyone know l01n.bin structure or l01n.bin convert to text file?

I think swuforce can help us!
## Post #19
- Username: Kazooie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 25, 2014 2:41 am
- Post datetime: 2014-11-24T19:03:46+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

How to extract the files?
## Post #20
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-11-24T19:11:28+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Use Ekey's unpacker (in first post in this thread), or Aluigi's BMS script for Anomaly series.
## Post #21
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-03T06:41:49+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

anyone need this? Chinese translation。
[http://dl.3dmgame.com/201411/52925.html](http://dl.3dmgame.com/201411/52925.html)
I want know how to translation,Study together.
## Post #22
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2014-12-03T08:42:32+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from geraldhu
>
> anyone need this? Chinese translation。
http://dl.3dmgame.com/201411/52925.html
I want know how to translation,Study together.

You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
## Post #23
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-03T12:07:21+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from shadowlonely1989
>
> geraldhu wrote:anyone need this? Chinese translation。
http://dl.3dmgame.com/201411/52925.html
I want know how to translation,Study together.

You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
看上去你是中国人，能具体交我如何操作吗？初学者不好意思啦。
## Post #24
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-03T13:01:50+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from geraldhu
>
> shadowlonely1989 wrote:geraldhu wrote:anyone need this? Chinese translation。
http://dl.3dmgame.com/201411/52925.html
I want know how to translation,Study together.

You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
看上去你是中国人，能具体交我如何操作吗？初学者不好意思啦。

E....Search results are:wow!
## Post #25
- Username: XrayStyleZ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 29, 2014 9:48 pm
- Post datetime: 2014-12-03T22:31:24+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from shadowlonely1989
>
> You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
Is it work? If yeah do normally instruction "how to translate", please.
## Post #26
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2014-12-04T08:42:11+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from XrayStyleZ
>
> shadowlonely1989 wrote:You can use Cartographer to dump text with your table to extract text and use atlas to insert your text.
Is it work? If yeah do normally instruction "how to translate", please.

Open hex and find, create your table, example, a=64, b=...., end=..., line=....
After translated, you can use Atlas to insert text!
## Post #27
- Username: momo
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 28, 2010 10:13 am
- Post datetime: 2014-12-13T12:12:15+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

.idx file repacked by Ekey's Packer is needed to change the header(first 3 bytes) for This War of Mine.

00 00 00 -> 00 06 01

And I've added some file names of This War of Mine to FileNames.list.
[FileNames.7z](https://xentaxbackup.github.io/file/8268_FileNames.7z)
## Post #28
- Username: namquang93
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Apr 09, 2012 3:40 pm
- Post datetime: 2014-12-15T05:58:31+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from momo
>
> .idx file repacked by Ekey's Packer is needed to change the header(first 3 bytes) for This War of Mine.

00 00 00 -> 00 06 01

And I've added some file names of This War of Mine to FileNames.list.

Hi! Could you help me repack this file, please? I have a big problem! Thanks for any help, here is my problem:
## Post #29
- Username: bloodzone
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 29, 2014 5:46 pm
- Post datetime: 2014-12-28T16:37:17+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

I don't speak english...sorry

question---
anomaly DAT unPacker v0.0.3 r6
anomaly DAT Packer v0.0.1 r1
Use program. 

"This War of Mine" translate into Korean.
After the combined file size is over.
16MB -> 160MB 
How can be solved?

sorry my...english....T-T

plz..help me...
## Post #30
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-28T18:33:46+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Size is OK. Packer does not use compression, that's why is file bigger then original.
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-12-28T21:17:54+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Tools updated. See first post.

[*] - Unpacker - Updated base names.
[*] - Packer - Now file data's compressing while packing.
## Post #32
- Username: bloodzone
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 29, 2014 5:46 pm
- Post datetime: 2014-12-29T20:38:22+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> Tools updated. See first post.

[*] - Unpacker - Updated base names.
[*] - Packer - Now file data's compressing while packing.

Thank you
## Post #33
- Username: bloodzone
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Nov 29, 2014 5:46 pm
- Post datetime: 2014-12-31T20:25:54+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

{mr|he}{fr|she}....
Will fix any output file be translated in the game?
I did not find it....
## Post #34
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-31T21:21:30+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Why is there "his" and "her" in the screenshot? You should translate it into Korean. I'm also translating and have no problems with this.
## Post #35
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-02-19T17:56:09+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Hi,

The .7z archive for the unpacker is broken apparently. Could you fix that?
## Post #36
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-02-19T18:16:55+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Both archives are OK. Tested it right now (unpacked them with 7zip 9.20 & WinRAR 5.11).
## Post #37
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-02-22T18:59:01+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from merlinsvk
>
> Both archives are OK. Tested it right now (unpacked them with 7zip 9.20 & WinRAR 5.11).

My bad. I was using an older version of 7z file manager.
## Post #38
- Username: pokrishka
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 12, 2015 5:32 am
- Post datetime: 2015-07-11T21:54:41+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Hello,

I would love to rename This War of Mine characters, I suppose this can be done by this software? Can somebody help me to understand how can I do this?
## Post #39
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2015-07-14T15:03:26+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

11 Bit Studios Games (Toolset) [https://yadi.sk/d/BdAOgcRNhAo6S](https://yadi.sk/d/BdAOgcRNhAo6S)
## Post #40
- Username: shadowlonely1989
- Rank: veteran
- Number of posts: 83
- Joined date: Sun Nov 30, 2014 8:49 am
- Post datetime: 2015-07-29T02:32:39+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> Tools updated. See first post.

[*] - Unpacker - Updated base names.
[*] - Packer - Now file data's compressing while packing.

Could you take and look This War Of Mine .obb (Android version)? Thanks!
## Post #41
- Username: 18and18and18
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 02, 2018 2:26 pm
- Post datetime: 2018-05-02T06:34:02+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Thank you ! I want unpack the music from forstpunk.
## Post #42
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-07-05T06:34:56+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from Ekey
>
> Unpacker v0.0.4 r7
Download: here

Supported games
* Anomaly 2
* Anomaly: Korea
* Anomaly: Warzone Earth
* Anomaly: Warzone Earth - Mobile Campaign
* Anomaly: Defenders
* This War of Mine

Packer v0.0.2 r3
Download: See attach

Warning : Make backup of original archives.

Result
Edited file l01n.bin (Language pack)

Have fun

Links are dead!
Please Someone Upload Unpacker tool...
## Post #43
- Username: adrianna
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 07, 2018 7:54 am
- Post datetime: 2018-11-05T16:33:43+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Please, upload .DAT Unpacker tool, if possible? He is nowhere else to find.
## Post #44
- Username: Zekfad
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 16, 2018 10:45 pm
- Post datetime: 2018-11-27T17:18:32+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Link is dead. Anyone else has downloaded unpacker, can someone share?
## Post #45
- Username: syzible
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 21, 2018 11:07 pm
- Post datetime: 2019-03-09T23:18:43+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

The link is dead!
## Post #46
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2019-03-10T10:20:30+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

Reupload of BSunpacker v0.0.4 and font/text tools: [https://files.fm/u/shx24hzc](https://files.fm/u/shx24hzc)
## Post #47
- Username: znar10
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 22, 2019 4:46 am
- Post datetime: 2019-05-26T20:42:01+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

dead links
## Post #48
- Username: adrianna
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 07, 2018 7:54 am
- Post datetime: 2019-05-27T09:12:20+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

znar10, [BSUnpacker v0.0.4](https://drive.google.com/file/d/1LcSU2Ln9uZVtDCQAVKhfrYKVQo_m_4D8/view?usp=sharing)
## Post #49
- Username: znar10
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 22, 2019 4:46 am
- Post datetime: 2019-05-31T22:11:38+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

thanks
## Post #50
- Username: znar10
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 22, 2019 4:46 am
- Post datetime: 2019-05-31T22:12:13+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from adrianna ↑Mon May 27, 2019 5:12 pm at Mon May 27, 2019 5:12 pm
>
> 
znar10, BSUnpacker v0.0.4
thnaks
## Post #51
- Username: adrianna
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 07, 2018 7:54 am
- Post datetime: 2020-10-05T19:07:36+00:00
- Post Title: Re: 11 Bit Studios Games  (*.DAT)

> Reply from adrianna ↑Mon May 27, 2019 5:12 pm at Mon May 27, 2019 5:12 pm
>
> 
znar10, BSUnpacker v0.0.4
It seems now google thinks that all archives with .exe or .dll are viruses.

New link, unpacker and packer:
[https://yadi.sk/d/VBSZrDdV5mCeDQ?ncrnd=5857](https://yadi.sk/d/VBSZrDdV5mCeDQ?ncrnd=5857)
