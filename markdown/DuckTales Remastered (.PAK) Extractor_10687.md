## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-13T21:06:08+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Tool for unpack PAK files

```
        DTRPAKUnpacker <inFile>

[Example]
        DTRPAKUnpacker amazon.pak
```


PS: Additional /wave Ha   se
[DTRPAKUnpacker.rar](https://xentaxbackup.github.io/file/6555_DTRPAKUnpacker.rar)
## Post #2
- Username: Rjack
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 14, 2012 4:53 pm
- Post datetime: 2013-08-14T05:40:28+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Thanks Ekey, it works great. Is there any chance you would make a packer?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-14T09:07:12+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Tools for repack makes Haoose. I think he share it later.
## Post #4
- Username: Rjack
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2013-08-18T21:14:54+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

[http://games-gen.com/soft/DuckTalesTools.exe](http://games-gen.com/soft/DuckTalesTools.exe)
Unpacker/Packer for PAK-files
## Post #5
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-04T15:44:18+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Wrote a console packer tool for those WayForward's resource packs (I hate GUI so much!).
Download it here [https://drive.google.com/folderview?id= ... sp=sharing](https://drive.google.com/folderview?id=0BxJga0T44nMedW9oTDRGb1o5NG8&usp=sharing) (paktools-0.1.zip, along with the cpp source code)
Mediafire mirror: [http://www.mediafire.com/download/oo9y2 ... ls-0.1.zip](http://www.mediafire.com/download/oo9y2304sm3i2g4/paktools-0.1.zip)
Github repository: [https://github.com/artlavrov/paktools](https://github.com/artlavrov/paktools)
Binary release (and linux version): [https://github.com/artlavrov/paktools/r ... -1.0.0.zip](https://github.com/artlavrov/paktools/releases/download/1.0.0/paktools-bin-1.0.0.zip)
## Post #6
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2014-10-05T15:17:38+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

> Reply from lavrov
>
> Binary release (and linux version): https://github.com/artlavrov/paktools/r ... -1.0.0.zip
BloodRayne Betrayal?
## Post #7
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-05T20:45:54+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

BloodRayne support (use -c option for packing)
[https://github.com/artlavrov/paktools/r ... -1.0.1.zip](https://github.com/artlavrov/paktools/releases/download/1.0.1/paktools-bin-1.0.1.zip)
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-10-17T19:23:31+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Compress / Decompress code for files with signature WFLZ > [https://code.google.com/p/wflz/](https://code.google.com/p/wflz/)
## Post #9
- Username: lavrov
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 04, 2014 11:39 pm
- Post datetime: 2014-10-18T19:21:44+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

> Reply from Ekey
>
> Compress / Decompress code for files with signature WFLZ > https://code.google.com/p/wflz/
Looks like [https://github.com/meh2481/wfLZEx](https://github.com/meh2481/wfLZEx) (forked by me as [https://github.com/artlavrov/wfLZEx](https://github.com/artlavrov/wfLZEx)) includes those two files (wfLZ.c has been renamed to *.cpp for some reason) to work with .anb files (there is a lot of extra code added to work with images). Doesn't compress them back though. I'll see what I can do.
Upd: I guess, according to this piece of code, .anb format is still unknown and there's no way to pack images back (well, maybe it's possible to replace them with smaller files).

```
{
	if(memcmp ( &(vData.data()[i]), "ZLFW", 4 ) == 0)	//Found another file
...
```
## Post #10
- Username: xjermariox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 20, 2016 5:11 am
- Post datetime: 2016-12-19T22:04:37+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Hate to bump such an old topic up, but seeing how Wayforward's Half-Genie Hero is about to release has there been any luck between then and now to repack .anb files for mods and such? Thanks
## Post #11
- Username: Evilangel
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Jun 25, 2021 1:45 pm
- Post datetime: 2021-09-29T22:19:39+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

Hello there, looking for advices, im trying to translate shantae risky's revenge  wayforward pc port from gog (english only) to spanish

The ducktool works fine. 

im having trouble with this source:
[https://drive.google.com/drive/folders/ ... xS6ipd1VCQ](https://drive.google.com/drive/folders/0B7LaUGSR3677MFlBRlpJT2c3Uk0?resourcekey=0-badkNeKanpwTxS6ipd1VCQ)

when i extract/import texts from .loctext files and imported them again using .au3 import/export; the size its different and the game crashes when i pack everything even without doing any changes.
## Post #12
- Username: butter tray
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 03, 2023 6:50 am
- Post datetime: 2023-09-03T18:19:24+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

> Reply from Haoose ↑Mon Aug 19, 2013 5:14 am at Mon Aug 19, 2013 5:14 am
>
> 
http://games-gen.com/soft/DuckTalesTools.exe
Unpacker/Packer for PAK-files is there a chance you have it on a diffrent site? cuase the previous one does not work
## Post #13
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-06T18:21:39+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

@butter tray: Here is mirror for that tool: [link](https://mega.nz/file/fdBHULxI#OxZGllS4wM00iOHZiJ9RdSf78Uc5bgxx6RExzXfJw8U)
## Post #14
- Username: butter tray
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Sep 03, 2023 6:50 am
- Post datetime: 2023-09-06T18:46:24+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

> Reply from Spiritovod ↑Thu Sep 07, 2023 2:21 am at Thu Sep 07, 2023 2:21 am
>
> 
@butter tray: Here is mirror for that tool: link

it wont let me download it it says "Sorry, this file is infected with a virus. Only the owner is allowed to download infected files."
## Post #15
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-06T19:00:52+00:00
- Post Title: DuckTales Remastered (*.PAK) Extractor

@butter tray: I've updated the link to different hosting. Apparently google false detected the tool because it's packed with protector.
