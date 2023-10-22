## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-10T18:07:59+00:00
- Post Title: Batman audio/subs language switcher

Experimental tool to switch audio/subs language independently. Means you can play with English audio + Portuguese subs, or Portuguese audio + English subs, or any other combination.

This will work with Batman Arkham: Knight, Origins, City. This also may work with other games based on wwise.

Warning! This is not supported by the game, so it requires to unpack & change a lot of game files, use on your own risk!

For example, if you wish to play Portuguese subs + English audio:

0. set Portuguese language in game
1. use 1.bat in the game folder to unpack all game packages (requires Gildor's decompress)
2. change numbers "1 1" in 2.bat to "1 8" (switch languages 1 and 8 )
3. run 2.bat in "unpacked" folder to patch unpacked files
4. replace the files (backup originals if needed)
5. rename English(US) and Portuguese(Brazil) folders, so the game will look for audio in Portuguese folder and it will find English audio there.
6. rename all the files inside from INT_1.WAD to PTB_1.WAD and so on.
[Bnk_switch.rar](https://xentaxbackup.github.io/file/9535_Bnk_switch.rar)
## Post #2
- Username: Ed Stark
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 11, 2015 1:37 pm
- Post datetime: 2015-08-13T07:17:35+00:00
- Post Title: Batman audio/subs language switcher

HI daemon1,

It would be possible to leave this tool compatible with Batman Origins??
With English audio + Portuguese subs.....
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-13T16:06:58+00:00
- Post Title: Batman audio/subs language switcher

Yes, it will be possible for all games and all language combinations. Just wait for updates.
## Post #4
- Username: Ed Stark
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 11, 2015 1:37 pm
- Post datetime: 2015-08-15T04:56:27+00:00
- Post Title: Batman audio/subs language switcher

> Reply from daemon1
>
> Yes, it will be possible for all games and all language combinations. Just wait for updates.

Waiting anxiously.......
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-15T06:40:37+00:00
- Post Title: Batman audio/subs language switcher

New version. Now all languages supported for Knight, Origins & City.

Ed Stark, use origins version, change numbers in 2.bat to "1 7", because in origins there are only 7 languages.
## Post #6
- Username: Ed Stark
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 11, 2015 1:37 pm
- Post datetime: 2015-08-16T07:11:42+00:00
- Post Title: Batman audio/subs language switcher

> Reply from daemon1
>
> New version. Now all languages supported for Knight, Origins & City.

Ed Stark, use origins version, change numbers in 2.bat to "1 7", because in origins there are only 7 languages.

Followed his instructions, but this error appears......
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-16T07:19:33+00:00
- Post Title: Batman audio/subs language switcher

I hope you backed up this file. It doesn't contain audio banks. Just replace it with original, and it must work.

The problem is that I can't yet make a list of packages that need to be patched. Arkham knight works with all packages unpacked. It seems Origins have some exceptions.
## Post #8
- Username: gustavobonja
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 17, 2015 6:24 am
- Post datetime: 2015-08-16T23:26:34+00:00
- Post Title: Batman audio/subs language switcher

Hi, i have a problem with step 3, what do i exactly have to do?

EDIT: nvm i got it but,still the same core.upk error,and i solved it but my game crashes now.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-17T04:36:28+00:00
- Post Title: Batman audio/subs language switcher

do not change core.upk file
## Post #10
- Username: gustavobonja
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 17, 2015 6:24 am
- Post datetime: 2015-08-17T05:06:05+00:00
- Post Title: Batman audio/subs language switcher

now i got a few upk errors,i got the original one but, the problem is,the error message goes so fast i can't even read

EDIT: ok i got the list of the upk's that can cause trouble,so don't change these:

GFxUI
Startup
IpDrv
Core
AkAudio
Engine
OnlineSubsystemSteamworks
BmGame

but my game still crashing...
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-17T15:14:15+00:00
- Post Title: Batman audio/subs language switcher

> Reply from gustavobonja
>
> but my game still crashing...

and what is the error message ?
## Post #12
- Username: gustavobonja
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 17, 2015 6:24 am
- Post datetime: 2015-08-17T15:30:29+00:00
- Post Title: Batman audio/subs language switcher

This

Fatal error!

Ozzy_[2014-03-07_09.25] 364844 2014-03-07_09.25.15 (Wwise: 2012.2.1 #4427) Game

Address = 0x45d8b7   (filename not found) [in C:\Program Files (x86)\WB Games\Batman - Arkham Origins\SinglePlayer\Binaries\Win32\BatmanOrigins.exe]
Address = 0x494eb3   (filename not found) [in C:\Program Files (x86)\WB Games\Batman - Arkham Origins\SinglePlayer\Binaries\Win32\BatmanOrigins.exe]
Address = 0x4513ff   (filename not found) [in C:\Program Files (x86)\WB Games\Batman - Arkham Origins\SinglePlayer\Binaries\Win32\BatmanOrigins.exe]
Address = 0x4264da   (filename not found) [in C:\Program Files (x86)\WB Games\Batman - Arkham Origins\SinglePlayer\Binaries\Win32\BatmanOrigins.exe]
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-17T16:29:28+00:00
- Post Title: Batman audio/subs language switcher

> Reply from gustavobonja
>
> filename not found

Maybe you choose wrong language?

What was the command you used in 2.bat and how did you rename the WAD files?
## Post #14
- Username: gustavobonja
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 17, 2015 6:24 am
- Post datetime: 2015-08-17T21:11:24+00:00
- Post Title: Batman audio/subs language switcher

i put 7 as you said earlier here,i just change the folders and rename from INT to POR.

Example: 393E9711_LOC_POR.wad
## Post #15
- Username: Ed Stark
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 11, 2015 1:37 pm
- Post datetime: 2015-08-18T08:15:34+00:00
- Post Title: Batman audio/subs language switcher

> Reply from daemon1
>
> I hope you backed up this file. It doesn't contain audio banks. Just replace it with original, and it must work.

The problem is that I can't yet make a list of packages that need to be patched. Arkham knight works with all packages unpacked. It seems Origins have some exceptions.

Worked perfectly, thank you very much!!!!!!!!!!!! 

May I disclose to the Brazilian community of gamers? With the appropriate credits, of course.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-18T15:47:28+00:00
- Post Title: Re: Batman audio/subs language switcher

Very good. Sure you can share it everywhere.

Maybe you can cooperate with gustavobonja here to find out why he can't make it work?
## Post #17
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-22T15:41:14+00:00
- Post Title: Re: Batman audio/subs language switcher

Just an issue that i found in Arkham Knight, given that the files are decompressed, and the .upk's get a lot bigger (extra 8gb to the total size) , the game suffers from a lot of loadings during gameplay.

Is there a way to compress them back?
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-22T17:51:31+00:00
- Post Title: Re: Batman audio/subs language switcher

Yes, probably. But I need to write a tool for that, and there's no guarantee it will work.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-23T10:58:17+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from BallisticSmith
>
> Just an issue that i found in Arkham Knight, given that the files are decompressed, and the .upk's get a lot bigger (extra 8gb to the total size) , the game suffers from a lot of loadings during gameplay.

Did it really get much worse? 

Origins works almost the same after decompressing all packages.
## Post #20
- Username: BallisticSmith
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 03, 2015 10:02 am
- Post datetime: 2015-08-23T15:53:46+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from daemon1
>
> Did it really get much worse?

Every 10 seconds, the game stutters and the loading symbol appears, but no problem man, i'll just go back to the original one...besides, i think rocksteady will issue a patch in the next few weeks, that has the option to force english audio, since consoles already got this fix, probably the pc will get it too, but thanks anyway
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-23T16:17:28+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from BallisticSmith
>
> Every 10 seconds, the game stutters and the loading symbol appears

Very strange. No idea why is that. The packages are decompressed in memory and must take the same space. Probably they load and unload them every 10 secs, and this can explain why so many people report lags. Files are too big.
## Post #22
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-11T00:42:41+00:00
- Post Title: Re: Batman audio/subs language switcher

This tool don't work to AKEP_RedHoodStory_SF.upk? (Batman Arkham Knight - Redhood Story Pack DLC)

[http://postimg.org/image/80ty5a6ch/](http://postimg.org/image/80ty5a6ch/)
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-11T15:20:29+00:00
- Post Title: Re: Batman audio/subs language switcher

Download "decompress" here [http://www.gildor.org/](http://www.gildor.org/)
## Post #24
- Username: Skrillex
- Rank: advanced
- Number of posts: 66
- Joined date: Sat Aug 23, 2014 1:11 am
- Post datetime: 2015-11-25T01:00:01+00:00
- Post Title: Re: Batman audio/subs language switcher

1 more question, i want localization the game for my language, is that possible on that tool? This tool change the subtitles successfully?
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-11-25T15:41:10+00:00
- Post Title: Re: Batman audio/subs language switcher

No, this tool can't change subtitles, only switch them between languages.
## Post #26
- Username: nobodyN6NZ9CRS
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 19, 2015 5:29 pm
- Post datetime: 2015-12-19T09:40:14+00:00
- Post Title: Re: Batman audio/subs language switcher

Arkham knight supports russian language. How I can switch to it? There is no russian in your list..
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-19T10:25:32+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from nobodyN6NZ9CRS
>
> Arkham knight supports russian language. How I can switch to it? There is no russian in your list..

Because there's no russian AUDIO in the game, and this tool switches audio banks.
## Post #28
- Username: nobodyN6NZ9CRS
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 19, 2015 5:29 pm
- Post datetime: 2015-12-19T11:28:35+00:00
- Post Title: Re: Batman audio/subs language switcher

So I want to switch audio from INT to German.
I have run 2.bat with params 1 2 but voices are still in English, I have reverted back upk files and tried with params 2 1, but results are same: english voices are not changed to german.

Update:
English voices are only in the intros, in game dialogues are on german.
Can I change voices language in intors as well?
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-19T12:23:50+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from nobodyN6NZ9CRS
>
> Can I change voices language in intors as well?

You need a video editor for that. People say movies are in some common format.
## Post #30
- Username: nobodyN6NZ9CRS
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 19, 2015 5:29 pm
- Post datetime: 2015-12-19T12:42:11+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from daemon1
>
> nobodyN6NZ9CRS wrote:Can I change voices language in intors as well?

You need a video editor for that. People say movies are in some common format.

Thank a lot mate. The tool is awesome, I barely lost my hope to find an audio switcher for this game.
## Post #31
- Username: bigbob1984
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 08, 2018 2:12 am
- Post datetime: 2018-04-07T19:06:10+00:00
- Post Title: Re: Batman audio/subs language switcher

> Reply from daemon1
>
> Experimental tool to switch audio/subs language independently. Means you can play with English audio + Portuguese subs, or Portuguese audio + English subs, or any other combination.

This will work with Batman Arkham: Knight, Origins, City. This also may work with other games based on wwise.

Warning! This is not supported by the game, so it requires to unpack & change a lot of game files, use on your own risk!

For example, if you wish to play Portuguese subs + English audio:

0. set Portuguese language in game
1. use 1.bat in the game folder to unpack all game packages (requires Gildor's decompress)
2. change numbers "1 1" in 2.bat to "1 8" (switch languages 1 and 8 )
3. run 2.bat in "unpacked" folder to patch unpacked files
4. replace the files (backup originals if needed)
5. rename English(US) and Portuguese(Brazil) folders, so the game will look for audio in Portuguese folder and it will find English audio there.
6. rename all the files inside from INT_1.WAD to PTB_1.WAD and so on.


Is it possible for you yo do a video guide?
## Post #32
- Username: VoronXVI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 18, 2018 5:12 am
- Post datetime: 2018-04-29T10:47:18+00:00
- Post Title: Re: Batman audio/subs language switcher

Hi!
This can be used for Batman Arkham Asylum?
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-04-29T11:15:01+00:00
- Post Title: Re: Batman audio/subs language switcher

no
