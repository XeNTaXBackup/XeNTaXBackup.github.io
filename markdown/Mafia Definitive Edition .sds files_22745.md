## Post #1
- Username: Digital X
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 26, 2020 6:33 am
- Post datetime: 2020-09-25T22:37:34+00:00
- Post Title: Mafia Definitive Edition .sds files

I understand it is very early days for this game, but was curious about the .sds files.

Mafia 2 and 3 have extractors but upon trying Mafia 3 extractor it crashed upon opening the .sds file, I assume because the specific version of .sds is too new? I know Mafia DE uses an upgraded version of the Mafia 3 engine, so thought it was worth a shot. All I can find and edit at the moment are values.

I am completely new to Mafia modding but my expertise lies in Spintires/Mudrunner, just looking to get my foot in the door here.

I guess we will be waiting a while?
## Post #2
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2020-09-26T07:58:58+00:00
- Post Title: Mafia Definitive Edition .sds files

Specification of Mafia DE SDS is almost same at the first blush. It's uses OODLE compression algorithm instead ZLIB in previous titles, and additional data in 96 bytes at the end of Compressed Blocks Headers. So it's no big problem to update extraction tools for their authors.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-28T17:21:39+00:00
- Post Title: Mafia Definitive Edition .sds files

Yeah, you're right



There is a slight problem with loading the some resources like as Textures, SoundBanks and some SDS's, but in general it almost works
## Post #4
- Username: bisalinamk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 28, 2019 1:49 pm
- Post datetime: 2020-09-28T17:53:59+00:00
- Post Title: Mafia Definitive Edition .sds files

> Reply from Ekey ↑Tue Sep 29, 2020 1:21 am at Tue Sep 29, 2020 1:21 am
>
> 
Yeah, you're right



There is a slight problem with loading the some resources like as Textures, SoundBanks and some SDS's, but in general it almost works

Any download link?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-28T18:08:28+00:00
- Post Title: Mafia Definitive Edition .sds files

Not ready yet.

WIP. Now works are Textures, SoundBanks and XML's






It's a remains to solve the problem with loading some SDS's.
## Post #6
- Username: Digital X
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 26, 2020 6:33 am
- Post datetime: 2020-09-28T23:58:56+00:00
- Post Title: Mafia Definitive Edition .sds files

You're the creator of this I assume? If so, huge thanks! This is exactly what I am looking for.

Also, I am pretty familar with Unity Asset Bundle Extractor, would this work the same way? As in we can choose a texture in the Resource Explorer, replace with our own, and pack it back up?
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-29T00:17:34+00:00
- Post Title: Mafia Definitive Edition .sds files

> Reply from Digital X ↑Tue Sep 29, 2020 7:58 am at Tue Sep 29, 2020 7:58 am
>
> 
You're the creator of this I assume? If so, huge thanks! This is exactly what I am looking for.
This is modified tool based on Gibbed Resource Explorer.

If we talk about authors, then it looks like this:
Original code by: Rick (Gibbed)
Extended modification for Mafia 3 files by: y.u.s.i.k
Littile modification for Mafia: Definitive Edition files by: Me

> Reply from Digital X ↑Tue Sep 29, 2020 7:58 am at Tue Sep 29, 2020 7:58 am
>
> 
Also, I am pretty familar with Unity Asset Bundle Extractor, would this work the same way? As in we can choose a texture in the Resource Explorer, replace with our own, and pack it back up?
Yep, you can replace any resources
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-29T13:37:53+00:00
- Post Title: Mafia Definitive Edition .sds files

Okay guys, almost done. I need to test the repacking function for other resource's
## Post #9
- Username: mami11x
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 24, 2018 11:54 am
- Post datetime: 2020-09-29T16:25:43+00:00
- Post Title: Mafia Definitive Edition .sds files

2
## Post #10
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2020-09-29T16:43:38+00:00
- Post Title: Mafia Definitive Edition .sds files

> Reply from Ekey ↑Tue Sep 29, 2020 9:37 pm at Tue Sep 29, 2020 9:37 pm
>
> 

Замечательно! Good work!
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-29T18:32:06+00:00
- Post Title: Mafia Definitive Edition .sds files

ResourceExplorer


Like button over there

Downloading link in attach! Happy modding 
[Link.zip](https://xentaxbackup.github.io/file/18784_Link.zip)
## Post #12
- Username: mami11x
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 24, 2018 11:54 am
- Post datetime: 2020-09-29T20:39:54+00:00
- Post Title: Mafia Definitive Edition .sds files

3
## Post #13
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-29T21:07:52+00:00
- Post Title: Mafia Definitive Edition .sds files

> Reply from mami11x ↑Wed Sep 30, 2020 4:39 am at Wed Sep 30, 2020 4:39 am
>
> 
thank you! you can share tools text xbin file?
[https://zenhax.com/viewtopic.php?p=33629#p33629](https://zenhax.com/viewtopic.php?p=33629#p33629)
## Post #14
- Username: Digital X
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 26, 2020 6:33 am
- Post datetime: 2020-09-29T23:22:37+00:00
- Post Title: Mafia Definitive Edition .sds files

Thanks, for me at least, the nginx web server throws up a 403 forbidden error. However Mirror 2 works fine. May just be my end.

Is there a tutorial of how to edit/replace the files?

In sds/generic/bolt_ace there is a lot of hex with text on the side, this is beyond me.

I have found the starting up sound, how would I go about replacing it?

I feel so bad for asking this, I just don't have the foggiest what I am doing with most of these files.

EDIT: On the beer case.dds I see "replace resource", Once I have chosen a texture what would I do then so the game can read it? In the extractor it shows 64x64 which is extremely small. My Commodore 64 has more resolution lol.
## Post #15
- Username: mami11x
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 24, 2018 11:54 am
- Post datetime: 2020-09-29T23:46:42+00:00
- Post Title: Mafia Definitive Edition .sds files

4
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-30T01:48:28+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

@Digital X - It's a simple.



First - You need a export this resource by click "Save To File" button and edit it.
Second - After editing press "Replace Resource" button and select edited file.
Third - Press "Save Replaced Resource".
Finish - Press "Save Archive" if you've finished modding resources.

Note: Always make backup copies of your archives just in case 

@mami11x - I already helped you! Tool works perfectly. Did you read the readme inside archive?  It describes in detail how to use the tool.

Proofs
## Post #17
- Username: mami11x
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Feb 24, 2018 11:54 am
- Post datetime: 2020-09-30T06:41:17+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

1
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-30T09:55:13+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

> Reply from mami11x ↑Wed Sep 30, 2020 2:41 pm at Wed Sep 30, 2020 2:41 pm
>
> 
I cannot use it for Mafia DE. can you guide me You can send me the tools file.
Take the trouble to explain your "I cannot use it for Mafia DE" means? Download tool here > [https://zenhax.com/viewtopic.php?p=33629#p33629](https://zenhax.com/viewtopic.php?p=33629#p33629)
Open readme and read guide of usage. It's a batch application.

Export

```
Mafia_III_XBIN_Text_Tool.exe -e stringtable_en_common_group.xbin stringtable_en_common_group.txt
```


Import

```
Mafia_III_XBIN_Text_Tool.exe -i stringtable_en_common_group.xbin stringtable_en_common_group.txt
```
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-30T11:46:25+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Mafia Definitive Edition Script Hook
Download: [here](https://github.com/MartinJK/Mafia-Definitive-Edition-ScriptHook/releases)

Thanks to [MartinJK](https://github.com/MartinJK) for release
## Post #20
- Username: Grand5
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 30, 2020 11:44 pm
- Post datetime: 2020-10-01T14:23:34+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Does anyone know how to pack the pck file back? I pulled the music from the pck file and made my own in wem format. But how do you add it to the game now? Answer, please. Sorry for my English.
## Post #21
- Username: VObject
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 08, 2020 5:34 pm
- Post datetime: 2020-10-08T09:39:13+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

> Reply from Grand5 ↑Thu Oct 01, 2020 10:23 pm at Thu Oct 01, 2020 10:23 pm
>
> 
Does anyone know how to pack the pck file back? I pulled the music from the pck file and made my own in wem format. But how do you add it to the game now? Answer, please. Sorry for my English.

Could you share how you got the files from .pck and converted audio to wem?
I think that if some people knew how to export files, then perhaps they could do the import.

This is a really needed feature, many people would to replace new remake music to classic.
## Post #22
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2020-10-08T17:50:28+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Well, I used a BMS script by AlphaTwentyThree for PCK files with an AKPK header to get the wem files.
## Post #23
- Username: deneverfaszu
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 22, 2015 8:52 pm
- Post datetime: 2020-10-09T20:09:56+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

There's an issue with XBIN editing.   

I don't know if it's Delutto's XBIN repacker or the Resource Explorer itself but after I reach 827099 characters and repack the xbin the game fails to load. (Game starts, gives a black screen, Steam overlay loads then crash). Please, if somone knows how to solve this issue help me. I really want to translate the game.
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-10T00:30:10+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Wait for release Mafia2Toolkit with a XBIN Editor >  [https://github.com/Greavesy1899/Mafia2Toolkit/releases](https://github.com/Greavesy1899/Mafia2Toolkit/releases)
## Post #25
- Username: VObject
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 08, 2020 5:34 pm
- Post datetime: 2020-10-10T06:40:17+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Luigi made a script that can export / import pck files.

[https://drive.google.com/file/d/113db_i ... sp=sharing](https://drive.google.com/file/d/113db_iZR_nI8soiNXQlprGH2KV_nT_77/view?usp=sharing)

when exporting, select quickbms.exe - pck2.bms - your pck file - folder for export
when importing, select reimport.bat or reimport2.bat - pck2.bms - your pck file - the same folder

How to make a correct .Wem file now?
The game did not accept .Wem file that i made throught Audiokinetic Wwise program
## Post #26
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-10-16T01:45:37+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Small tool for extract textures from images_streaming.pckg -
[https://www112.zippyshare.com/v/DVFuZrtd/file.html](https://www112.zippyshare.com/v/DVFuZrtd/file.html)
## Post #27
- Username: sanityofficial
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 23, 2020 11:29 pm
- Post datetime: 2020-10-23T15:37:20+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Hi guys, it's been a while since the topic is created but I'm having an issue importing the xbin file I translated. At the first time I used the tool, tool worked fine and there were no problems. I translated the main menu & imported the xbin file and it worked well. But after I started editing more lines and import the new xbin file, the game started crashing. I tried deleting some lines and put back the original line between 13000&17000. line - it worked but when I even edit one line between 13000&17000. line - the game starts crashing again. Can someone help me with this?
## Post #28
- Username: dogandroad
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 04, 2020 10:22 am
- Post datetime: 2020-11-16T07:06:12+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

> Reply from Ekey ↑Wed Sep 30, 2020 9:48 am at Wed Sep 30, 2020 9:48 am
>
> 
@Digital X - It's a simple.



First - You need a export this resource by click "Save To File" button and edit it.
Second - After editing press "Replace Resource" button and select edited file.
Third - Press "Save Replaced Resource".
Finish - Press "Save Archive" if you've finished modding resources.

Note: Always make backup copies of your archives just in case 

@mami11x - I already helped you! Tool works perfectly. Did you read the readme inside archive?  It describes in detail how to use the tool.

Proofs

Hi, Ekey. Is there anyway to exctract the model? I can see the texture with mafia toolkit. But the files in model folder is COMPILED.
## Post #29
- Username: aria1996
- Rank: advanced
- Number of posts: 48
- Joined date: Fri Mar 20, 2020 3:33 am
- Post datetime: 2021-01-30T06:39:27+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

hi guys 
I have a problem can you help me?
[Annotation 2021-01-30 095049.png](https://xentaxbackup.github.io/file/19424_Annotation 2021-01-30 095049.png)
## Post #30
- Username: norskpl
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 28, 2017 6:11 am
- Post datetime: 2021-02-02T18:01:41+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

> Reply from aria1996 ↑Sat Jan 30, 2021 2:39 pm at Sat Jan 30, 2021 2:39 pm
>
> 
hi guys 
I have a problem can you help me?

Hi. Which Toolkit version do you use? Check Mafia Toolkit discord, we will can help you easier then.
## Post #31
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-03-07T12:55:50+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Hey guys, when will be avaliable to export models?
## Post #32
- Username: VObject
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Oct 08, 2020 5:34 pm
- Post datetime: 2021-05-22T12:57:19+00:00
- Post Title: Re: Mafia Definitive Edition .sds files

Made a video tutorial to edit .pck audio file in Mafia DE. Enjoy. 
[https://www.nexusmods.com/mafiadefiniti ... /videos/18](https://www.nexusmods.com/mafiadefinitiveedition/videos/18)
