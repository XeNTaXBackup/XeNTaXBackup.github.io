## Post #1
- Username: ExQualityZ
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2017 2:47 am
- Post datetime: 2020-10-26T16:31:23+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Game is ready to preload right now, i guess someone could look into the dat archives?
## Post #2
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-10-26T16:36:09+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

The archives are still in roughly the same format that WD2 had, but the compression method has changed. Is anyone willing to look into it, so that we're able to unpack / repack the archives?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-26T16:40:21+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

I don't have a game and can't check it, but probably files must be compressed by Oodle
## Post #4
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-10-26T16:44:20+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Sample archive files: [https://im-a-dolphin.de/wd/wdl_common.zip](https://im-a-dolphin.de/wd/wdl_common.zip)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-26T17:43:47+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

In fact it's a old engine with version 13 is used, the previous one was 11. I changed the version for Legion in my old Explorer and it works fine.



I think Sir Kane can fix their toolkit for Legion.
## Post #6
- Username: ExQualityZ
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 12, 2017 2:47 am
- Post datetime: 2020-10-26T17:53:28+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Damn you should release that explorer, didn't know something like that even exists and it looks like a very handy tool
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-26T18:09:47+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

I did not make this tool for extracting or packing files, but only for convenient viewing of root directories and correct parsing of offset, compressed size and uncompressed size values. Usually all my tools are just console ones. In this case, I see no reason to do what is already there, it's just that Sir Kane needs to make some changes in his toolkit for WD2 and it will be works fine for unpack and pack it back. 

Also i don’t know yet what about data compression. Probably newest compression used > OOdle??? 

If i understand correctly, they did not include the executable file with the libraries in the preload, right?
## Post #8
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-10-26T19:17:09+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

> If i understand correctly, they did not include the executable file with the libraries in the preload, right?

yup

```

26.10.2020  18:29    <DIR>          data_win64
26.10.2020  18:23    <DIR>          Support
26.10.2020  18:29    <DIR>          uplay_download
26.10.2020  18:14         1.452.093 uplay_install.manifest
26.10.2020  18:29             1.922 uplay_install.state
               3 File(s)      1.454.015 bytes

 Directory of c:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Watch Dogs Legion\data_win64

26.10.2020  18:15     1.744.396.600 common.dat
26.10.2020  18:15           697.916 common.fat
26.10.2020  18:15           103.032 commonengine.dat
26.10.2020  18:15               936 commonengine.fat
26.10.2020  18:15     1.467.329.855 patch.dat
26.10.2020  18:15           644.816 patch.fat
26.10.2020  18:22        21.727.597 patch_english.dat
26.10.2020  18:22             5.236 patch_english.fat
26.10.2020  18:16     2.204.038.964 shadersobj.dat
26.10.2020  18:16         3.391.996 shadersobj.fat
26.10.2020  18:16             1.445 skuconfig.dat
26.10.2020  18:16       303.314.237 sound.dat
26.10.2020  18:16             3.656 sound.fat
26.10.2020  18:29                 0 sound_english.dat
26.10.2020  18:22                36 sound_english.fat
26.10.2020  18:18    11.331.358.957 videos.dat
26.10.2020  18:18             5.296 videos.fat
26.10.2020  18:25     3.704.538.840 videos_ultra.dat
26.10.2020  18:25               896 videos_ultra.fat
26.10.2020  18:23    <DIR>          worlds
              19 File(s) 20.781.560.311 bytes

 Directory of c:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Watch Dogs Legion\data_win64\worlds\london

26.10.2020  18:20     7.487.001.912 london.dat
26.10.2020  18:20         3.118.292 london.fat
26.10.2020  18:20       275.630.627 london_cache.dat
26.10.2020  18:20           609.212 london_cache.fat
26.10.2020  18:22       285.218.491 london_english.dat
26.10.2020  18:22         2.813.396 london_english.fat
26.10.2020  18:21     5.167.560.762 london_hires.dat
26.10.2020  18:21           965.116 london_hires.fat
26.10.2020  18:21       757.340.092 london_preload.dat
26.10.2020  18:21         1.881.716 london_preload.fat
26.10.2020  18:22     5.244.309.547 london_sound.dat
26.10.2020  18:22           126.536 london_sound.fat
26.10.2020  18:23     4.427.483.186 london_sound_english.dat
26.10.2020  18:23         2.407.076 london_sound_english.fat
26.10.2020  18:29    12.351.233.799 london_ultra.dat
26.10.2020  18:29           277.656 london_ultra.fat
              16 File(s) 36.007.977.416 bytes

```
## Post #9
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-26T19:21:34+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Well, okay. I'll check OOdle compression later.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-27T14:59:13+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Okay, here patched in two bytes version of WD2Extractor for Legion.

[Mirror 1](https://www92.zippyshare.com/v/WLbExOQ7/file.html)
[Mirror 2](https://dropmefiles.com/nyfTg)
[Mirror 3](https://www.dropbox.com/s/6p6t65v8r224pkd/WD2Extract_Legion.rar?dl=0)

Have fun
## Post #11
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-10-27T15:50:26+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Thank you, I really appreciate your work!
## Post #12
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-10-27T22:15:14+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Great job Ekey! Thank you! 
Could you share some info how you did it? What kind of compression is it, etc? 

Edit:

Just noticed " here patched in two bytes"  

btw. What do you use to view xbg files? the tool I used for WD2 (plugin for UU3D) doesn't work
## Post #13
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2020-10-27T23:20:26+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

Here's version 1.0 of WdlExtract: 

 WdlExtract.7z
(17.83 KiB) Downloaded 483 times


Doesn't come with a FileList.txt.
## Post #14
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2020-10-28T10:48:46+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

How to open and pack hello?

[https://www.dosya.tc/server32/x11e6w/ma ... h.loc.html](https://www.dosya.tc/server32/x11e6w/main_english.loc.html)
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-28T10:50:06+00:00
- Post Title: Watch Dogs: Legion .dat .fat archives

> Reply from Sir Kane ↑Wed Oct 28, 2020 7:20 am at Wed Oct 28, 2020 7:20 am
>
> 
Here's version 1.0 of WdlExtract: WdlExtract.7z
Doesn't come with a FileList.txt.

Windows Defender detect it as Trojan:Script/Wacatac.B!ml
## Post #16
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2020-10-28T17:43:35+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from Ekey ↑Wed Oct 28, 2020 6:50 pm at Wed Oct 28, 2020 6:50 pm
>
> 
Sir Kane wrote: ↑Wed Oct 28, 2020 7:20 am
Here's version 1.0 of WdlExtract: WdlExtract.7z
Doesn't come with a FileList.txt.


Windows Defender detect it as Trojan:Script/Wacatac.B!ml

Did you:
Update your definitions?
Make sure it wasn't something on your machine?
Upload to virustotal or a similar service from another machine?

I'mma have to guess that's a no to all of them.
## Post #17
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-10-28T21:04:01+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

False positive!  Two days ago windows defender detected a trojan in a script that had 20 lines and which I wrote a few days earlier
## Post #18
- Username: shevtsov200
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 29, 2020 7:43 pm
- Post datetime: 2020-10-29T11:46:49+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hi, could anyone of you pros tell [people here](https://forums.ubisoft.com/showthread.php/2284955-Cannot-change-language/page6) how to replace horrible localization with original text and sound please?
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-29T13:20:05+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

My list. Current state 364053

[Mirror 1](https://www29.zippyshare.com/v/eBxykmzT/file.html)
[Mirror 2](https://dropmefiles.com/Ao6jo)
[Mirror 3](https://www.dropbox.com/s/l6v9qrwt10oc2p7/filelist_u2.rar?dl=0)

```
commonengine.fat -> Resolved: 18 / Unknown: 27
patch.fat -> Resolved: 2716 / Unknown: 29523
patch_brazilian.fat -> Resolved: 1569 / Unknown: 67932
patch_english.fat -> Resolved: 77 / Unknown: 183
patch_french.fat -> Resolved: 1155 / Unknown: 67452
patch_german.fat -> Resolved: 3299 / Unknown: 141734
patch_italian.fat -> Resolved: 1079 / Unknown: 67510
patch_japanese.fat -> Resolved: 2406 / Unknown: 68883
patch_russian.fat -> Resolved: 2147 / Unknown: 66442
patch_spanish.fat -> Resolved: 877 / Unknown: 67367
shadersobj.fat -> Resolved: 117 / Unknown: 169481
sound.fat -> Resolved: 19 / Unknown: 162
videos.fat -> Resolved: 246 / Unknown: 17
videos_ultra.fat -> Resolved: 41 / Unknown: 2
london.fat -> Resolved: 110342 / Unknown: 45570
london_brazilian.fat -> Resolved: 74102 / Unknown: 66566
london_cache.fat -> Resolved: 15790 / Unknown: 14668
london_english.fat -> Resolved: 74102 / Unknown: 66566
london_french.fat -> Resolved: 74102 / Unknown: 66566
london_german.fat -> Resolved: 74102 / Unknown: 66566
london_hires.fat -> Resolved: 45527 / Unknown: 2727
london_italian.fat -> Resolved: 74102 / Unknown: 66566
london_japanese.fat -> Resolved: 74102 / Unknown: 66566
london_preload.fat -> Resolved: 44783 / Unknown: 49301
london_russian.fat -> Resolved: 74102 / Unknown: 66566
london_sound.fat -> Resolved: 4300 / Unknown: 2025
london_sound_brazilian.fat -> Resolved: 3180 / Unknown: 118955
london_sound_english.fat -> Resolved: 4690 / Unknown: 115662
london_sound_french.fat -> Resolved: 3328 / Unknown: 118736
london_sound_german.fat -> Resolved: 3296 / Unknown: 117805
london_sound_italian.fat -> Resolved: 3380 / Unknown: 117031
london_sound_japanese.fat -> Resolved: 3303 / Unknown: 116367
london_sound_russian.fat -> Resolved: 4376 / Unknown: 116828
london_sound_spanish.fat -> Resolved: 43 / Unknown: 121406
london_spanish.fat -> Resolved: 74102 / Unknown: 66566
london_ultra.fat -> Resolved: 13503 / Unknown: 378
```
## Post #20
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-10-29T14:46:55+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from Sir Kane ↑Wed Oct 28, 2020 7:20 am at Wed Oct 28, 2020 7:20 am
>
> 
Here's version 1.0 of WdlExtract: WdlExtract.7z
Doesn't come with a FileList.txt.

need wdlpack.exe
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-10-29T14:55:22+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Who can check if WdlExtract supports the second FAT type? Example files like london.fat, london_cache.fat
## Post #22
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-10-29T16:28:06+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Sir Kane's extract tool : work
your extract tool : non work
## Post #23
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-10-29T16:37:24+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from Ekey ↑Thu Oct 29, 2020 10:55 pm at Thu Oct 29, 2020 10:55 pm
>
> 
Who can check if WdlExtract supports the second FAT type? Example files like london.fat, london_cache.fat

sir kane's extract tool supports london.fat
but your extract tool non-support
## Post #24
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2020-10-30T00:30:04+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Some more soundbinaries for the filelist:soundbinary\234358370.bnk
soundbinary\1191819589.bnk
soundbinary\1393999501.bnk
soundbinary\1808109270.bnk
soundbinary\2015342277.bnk
soundbinary\2200683920.bnk
soundbinary\2318651520.bnk
soundbinary\2373441447.bnk
soundbinary\2538756460.bnk
soundbinary\3611979020.bnk
soundbinary\3653172684.bnk
soundbinary\3765763177.bnk
soundbinary\3779997610.bnk
soundbinary\3924338653.bnk
soundbinary\4087276499.bnk
soundbinary\4090580323.bnk
soundbinary\4290770421.bnk
## Post #25
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-11-02T07:32:56+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from Ekey ↑Thu Oct 29, 2020 10:55 pm at Thu Oct 29, 2020 10:55 pm
>
> 
Who can check if WdlExtract supports the second FAT type? Example files like london.fat, london_cache.fat

can u make a Wdlpack tool?
## Post #26
- Username: ChlorideCull
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 04, 2020 10:49 pm
- Post datetime: 2020-11-04T19:03:28+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Toss engine\actionmaps\debugactionmap.xml into the file list too.

edit: and the following, for Stadia and PS5

engine\settings\yeti\playerawards.xml
engine\settings\prospero\playerawards.xml
engine\settings\prospero\playerpresence.xml
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-11-07T12:59:53+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Updated list. Current state 756467

[Mirror 1](https://www119.zippyshare.com/v/jHDdERA6/file.html)
[Mirror 2](https://dropmefiles.com/hMasE)
[Mirror 3](https://www.dropbox.com/s/bfp0b5d0qzunk2u/filelist_u3.rar?dl=0)

```
commonengine.fat -> Total Files: 45 ==> Resolved: 45 / Unknown: 0
patch.fat -> Total Files: 32239 ==> Resolved: 3916 / Unknown: 28323
patch_brazilian.fat -> Total Files: 69501 ==> Resolved: 51549 / Unknown: 17952
patch_english.fat -> Total Files: 260 ==> Resolved: 140 / Unknown: 120
patch_french.fat -> Total Files: 68607 ==> Resolved: 51020 / Unknown: 17587
patch_german.fat -> Total Files: 145033 ==> Resolved: 57762 / Unknown: 87271
patch_italian.fat -> Total Files: 68589 ==> Resolved: 51153 / Unknown: 17436
patch_japanese.fat -> Total Files: 71289 ==> Resolved: 52541 / Unknown: 18748
patch_russian.fat -> Total Files: 68589 ==> Resolved: 52075 / Unknown: 16514
patch_spanish.fat -> Total Files: 68244 ==> Resolved: 50967 / Unknown: 17277
shadersobj.fat -> Total Files: 169598 ==> Resolved: 109091 / Unknown: 60507
sound.fat -> Total Files: 181 ==> Resolved: 116 / Unknown: 65
videos.fat -> Total Files: 263 ==> Resolved: 262 / Unknown: 1
videos_ultra.fat -> Total Files: 43 ==> Resolved: 43 / Unknown: 0
london.fat -> Total Files: 155912 ==> Resolved: 143469 / Unknown: 12443
london_brazilian.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_cache.fat -> Total Files: 30458 ==> Resolved: 29970 / Unknown: 488
london_english.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_french.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_german.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_hires.fat -> Total Files: 48254 ==> Resolved: 48233 / Unknown: 21
london_italian.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_japanese.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_preload.fat -> Total Files: 94084 ==> Resolved: 82978 / Unknown: 11106
london_russian.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_sound.fat -> Total Files: 6325 ==> Resolved: 5968 / Unknown: 357
london_sound_brazilian.fat -> Total Files: 122135 ==> Resolved: 8823 / Unknown: 113312
london_sound_english.fat -> Total Files: 120352 ==> Resolved: 99961 / Unknown: 20391
london_sound_french.fat -> Total Files: 122064 ==> Resolved: 9054 / Unknown: 113010
london_sound_german.fat -> Total Files: 121101 ==> Resolved: 8986 / Unknown: 112115
london_sound_italian.fat -> Total Files: 120411 ==> Resolved: 9160 / Unknown: 111251
london_sound_japanese.fat -> Total Files: 119670 ==> Resolved: 8919 / Unknown: 110751
london_sound_russian.fat -> Total Files: 121204 ==> Resolved: 10202 / Unknown: 111002
london_sound_spanish.fat -> Total Files: 121449 ==> Resolved: 9084 / Unknown: 112365
london_spanish.fat -> Total Files: 140668 ==> Resolved: 124497 / Unknown: 16171
london_ultra.fat -> Total Files: 13881 ==> Resolved: 13879 / Unknown: 2
```
## Post #28
- Username: SunburntRock89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 08, 2020 3:27 am
- Post datetime: 2020-11-07T20:00:35+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

So, what can be done with these files?
## Post #29
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2020-11-09T01:51:57+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from SunburntRock89 ↑Sun Nov 08, 2020 4:00 am at Sun Nov 08, 2020 4:00 am
>
> 
So, what can be done with these files?

Having asked that question tells us you either you don't know what you're doing or you're just to lazy to read around and get informed.
## Post #30
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-11-09T03:46:46+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from sunbeam906 ↑Mon Nov 09, 2020 9:51 am at Mon Nov 09, 2020 9:51 am
>
> 
SunburntRock89 wrote: ↑Sun Nov 08, 2020 4:00 am
So, what can be done with these files?


Having asked that question tells us you either you don't know what you're doing or you're just to lazy to read around and get informed.

Are you working on noclip？
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-11-09T12:48:25+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Updated list (Sound files). Current state 1446844

[Mirror 1](https://www118.zippyshare.com/v/TQNuuGcB/file.html)
[Mirror 2](https://dropmefiles.com/Dixkj)
[Mirror 3](https://www.dropbox.com/s/zekxtrnccknchps/filelist_u4.rar?dl=0)

```
commonengine.fat -> 45 of 45 (100%)
patch.fat -> 3916 of 32239 (12%)
patch_brazilian.fat -> 53213 of 69501 (76%)
patch_english.fat -> 145 of 260 (55%)
patch_french.fat -> 52307 of 68607 (76%)
patch_german.fat -> 124627 of 145033 (85%)
patch_italian.fat -> 52543 of 68589 (76%)
patch_japanese.fat -> 54915 of 71289 (77%)
patch_russian.fat -> 52810 of 68589 (76%)
patch_spanish.fat -> 52122 of 68244 (76%)
shadersobj.fat -> 109091 of 169598 (64%)
sound.fat -> 116 of 181 (64%)
videos.fat -> 262 of 263 (99%)
videos_ultra.fat -> 43 of 43 (100%)
london.fat -> 143469 of 155912 (92%)
london_brazilian.fat -> 124497 of 140668 (88%)
london_cache.fat -> 29970 of 30458 (98%)
london_english.fat -> 124497 of 140668 (88%)
london_french.fat -> 124497 of 140668 (88%)
london_german.fat -> 124497 of 140668 (88%)
london_hires.fat -> 48233 of 48254 (99%)
london_italian.fat -> 124497 of 140668 (88%)
london_japanese.fat -> 124497 of 140668 (88%)
london_preload.fat -> 82978 of 94084 (88%)
london_russian.fat -> 124497 of 140668 (88%)
london_sound.fat -> 5968 of 6325 (94%)
london_sound_brazilian.fat -> 107915 of 122135 (88%)
london_sound_english.fat -> 104839 of 120352 (87%)
london_sound_french.fat -> 107972 of 122064 (88%)
london_sound_german.fat -> 107120 of 121101 (88%)
london_sound_italian.fat -> 106453 of 120411 (88%)
london_sound_japanese.fat -> 105641 of 119670 (88%)
london_sound_russian.fat -> 107338 of 121204 (88%)
london_sound_spanish.fat -> 107259 of 121449 (88%)
london_spanish.fat -> 124497 of 140668 (88%)
london_ultra.fat -> 13879 of 13881 (99%)
```
## Post #32
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-11-13T20:13:21+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Updated list. Current state 1456854

[Mirror 1](https://www6.zippyshare.com/v/mzphIBir/file.html)
[Mirror 2](https://dropmefiles.com/e0hsC)
[Mirror 3](https://www.dropbox.com/s/p4dj1k80l7rjhi9/filelist_u5.rar?dl=0)

```
commonengine.fat -> 45 of 45 (100%)
patch.fat -> 3919 of 32239 (12%)
patch_brazilian.fat -> 53223 of 69501 (76%)
patch_english.fat -> 153 of 260 (58%)
patch_french.fat -> 52317 of 68607 (76%)
patch_german.fat -> 124637 of 145033 (85%)
patch_italian.fat -> 52553 of 68589 (76%)
patch_japanese.fat -> 54925 of 71289 (77%)
patch_russian.fat -> 52820 of 68589 (77%)
patch_spanish.fat -> 52132 of 68244 (76%)
shadersobj.fat -> 109175 of 169598 (64%)
sound.fat -> 116 of 181 (64%)
videos.fat -> 263 of 263 (100%)
videos_ultra.fat -> 43 of 43 (100%)
london.fat -> 152608 of 155912 (97%)
london_brazilian.fat -> 124507 of 140668 (88%)
london_cache.fat -> 30317 of 30458 (99%)
london_english.fat -> 124507 of 140668 (88%)
london_french.fat -> 124507 of 140668 (88%)
london_german.fat -> 124507 of 140668 (88%)
london_hires.fat -> 48241 of 48254 (99%)
london_italian.fat -> 124507 of 140668 (88%)
london_japanese.fat -> 124507 of 140668 (88%)
london_preload.fat -> 83218 of 94084 (88%)
london_russian.fat -> 124507 of 140668 (88%)
london_sound.fat -> 5968 of 6325 (94%)
london_sound_brazilian.fat -> 107915 of 122135 (88%)
london_sound_english.fat -> 104839 of 120352 (87%)
london_sound_french.fat -> 107972 of 122064 (88%)
london_sound_german.fat -> 107120 of 121101 (88%)
london_sound_italian.fat -> 106453 of 120411 (88%)
london_sound_japanese.fat -> 105641 of 119670 (88%)
london_sound_russian.fat -> 107338 of 121204 (88%)
london_sound_spanish.fat -> 107259 of 121449 (88%)
london_spanish.fat -> 124507 of 140668 (88%)
london_ultra.fat -> 13879 of 13881 (99%)
```


Thanks to [SunBeam](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=70303)
## Post #33
- Username: AliGMods
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 16, 2020 6:41 pm
- Post datetime: 2020-11-16T11:07:12+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hello, I've tried your tools to extract files from WD: Legion and unfortunately they don't work for me. Could you please write me the procedure. My procedure was as follows: I moved the common.dat and common.fat files to the folder from your tool. I downloaded the current filelist.txt and put it in the same folder. I moved the common.dat file to WD2Extract.exe and the file did not unzip.
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-11-16T12:12:34+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

[viewtopic.php?p=168208#p168208](https://forum.xentax.com/viewtopic.php?p=168208#p168208)
## Post #35
- Username: deylone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2020 11:20 pm
- Post datetime: 2020-11-17T07:42:44+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Has anyone succeeded in repacking a dat files ?

If I use WD2Repack to repack the patch.dat folder stucture for instance I get a black screen when starting the game.

It looks like the format used by WD2Pack is not compatible with WDL. 

If this is confirmed it would be greatly appreciated if anyone could update WD2Pack
## Post #36
- Username: AliGMods
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 16, 2020 6:41 pm
- Post datetime: 2020-11-19T12:35:37+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hello extracting from FAT / DAT folder works fine. Conversion from LOC to TXT also works well. Unfortunately, I did not find a program to convert from TXT to LOC. @deylon Can you please provide me a tool to convert from TXT to LOC and WD2Pack the programmer I'm in contact with would look at it. Thank you
## Post #37
- Username: deylone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2020 11:20 pm
- Post datetime: 2020-11-19T17:27:57+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from AliGMods ↑Thu Nov 19, 2020 8:35 pm at Thu Nov 19, 2020 8:35 pm
>
> 
Hello extracting from FAT / DAT folder works fine. Conversion from LOC to TXT also works well. Unfortunately, I did not find a program to convert from TXT to LOC. @deylon Can you please provide me a tool to convert from TXT to LOC and WD2Pack the programmer I'm in contact with would look at it. Thank you

Sorry I don't know how to do that. I have just been tweaking the graphics config files in the common.dat. They are easy to edit since they are basic xml / txt files.

However I am stuck while trying to use the repacked dat file.

you can find the fulll package for WD2 here:

[https://www88.zippyshare.com/v/HZ4T8htq/file.html](https://www88.zippyshare.com/v/HZ4T8htq/file.html)
## Post #38
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2020-11-22T08:09:40+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

How can you see the actual models? I only get .pso and .vso files etc. Can someone point me in the right direction?
## Post #39
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2020-11-25T23:30:40+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Please we need WDLRepack.exe
## Post #40
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-11-26T05:44:22+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from Xecutioner ↑Thu Nov 26, 2020 7:30 am at Thu Nov 26, 2020 7:30 am
>
> 
Please we need WDLRepack.exe

In fact, it already exists
## Post #41
- Username: sinnerclown
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Aug 22, 2020 5:49 am
- Post datetime: 2020-11-26T18:27:48+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

So how ?
## Post #42
- Username: Xecutioner
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Oct 12, 2016 6:51 pm
- Post datetime: 2020-11-26T20:04:40+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from atomicool ↑Thu Nov 26, 2020 1:44 pm at Thu Nov 26, 2020 1:44 pm
>
> 
Xecutioner wrote: ↑Thu Nov 26, 2020 7:30 am
Please we need WDLRepack.exe


In fact, it already exists

FAKE!
## Post #43
- Username: ecmgecko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 27, 2020 5:02 am
- Post datetime: 2020-11-26T21:47:43+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

WDLPack would be great.

Thx
## Post #44
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-11-28T19:49:59+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

The WDL Repacker of your dreams: [https://github.com/rootCBR/PackLegion](https://github.com/rootCBR/PackLegion)
## Post #45
- Username: AliGMods
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 16, 2020 6:41 pm
- Post datetime: 2020-12-01T14:17:00+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hello could anyone please do an export from txt to loc. Thank you
## Post #46
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2020-12-02T17:40:57+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

The repacker works beautifully! Thank you!

Now I was wondering if someone could give me some help with texture modding!
I noticed the game’s high textures for body parts are DXT1 without mipmaps, and modding them work fine! (Unfortunately you can only see them if you zoom in very close to the mesh, because that’s the only time the game loads them)
On the other hand, weirdly, the game uses medium quality textures to show on the mesh at distance, and these medium textures have mipmaps.
All good up to here, they are also DXT1 and you would think they can be saved as such with auto generated mipmaps and it would work fine, but it doesn’t.
When I try to use modded medium skin textures it looks all off, I mean the texture loads in game but kinda blurry or out of place.
If only I knew how to properly save them (I did notice the modded dds texture is 1 kb off on all medium textures when I save them) or if I could at least force the game to only read the “high” textures and stop loading the medium one - thought I would see if someone here has already been through the challenge and know a fix?
I never modded WD2 so im not sure if it’s something known for the community.

Any help would be appreciated! Ps: the textures, high and medium I mentioned above are in: graphics/characters/body/body_parts/white00 (or black00 or arab00)/
## Post #47
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2020-12-03T06:58:53+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

I think the files export very well. This is really cool. Thank you to all.

But I have a question. How can I import xbg files? I saw that some substances are called export. But there is no tool for this. My example is Blender import script.
Do you have any idea about this?  How can I get the models?
## Post #48
- Username: deylone
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2020 11:20 pm
- Post datetime: 2020-12-03T09:18:28+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Many thanks for the packer. I have managed to use the recombine option to modify config files as desired. I didn't try anything else so I won't be of much help on questions related to xbg or textures.
## Post #49
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-12-03T19:31:18+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

@maryangel: You can indeed force the game to load only one specific texture without its medium, high or ultra versions. You simply have to remove the affix from the file name (and keep the XBT header of the original higher quality texture), so your modified "body_white00_f_c_ultra.xbt" (or medium/high) becomes "body_white00_f_c.xbt".

Im curious though, the files you mentioned are only really interesting if you want to modify human body textures...
## Post #50
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2020-12-03T20:06:07+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from CobraGamer ↑Fri Dec 04, 2020 3:31 am at Fri Dec 04, 2020 3:31 am
>
> 
@maryangel: You can indeed force the game to load only one specific texture without its medium, high or ultra versions. You simply have to remove the affix from the file name (and keep the XBT header of the original higher quality texture), so your modified "body_white00_f_c_ultra.xbt" (or medium/high) becomes "body_white00_f_c.xbt".

Im curious though, the files you mentioned are only really interesting if you want to modify human body textures... 

Wow Cobra, thank you so much! Worked like charm!  
Will be adding some cool tattoos to my team today lol
## Post #51
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-12-05T10:58:20+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from maryrangel ↑Fri Dec 04, 2020 4:06 am at Fri Dec 04, 2020 4:06 am
>
> 
CobraGamer wrote: ↑Fri Dec 04, 2020 3:31 am
@maryangel: You can indeed force the game to load only one specific texture without its medium, high or ultra versions. You simply have to remove the affix from the file name (and keep the XBT header of the original higher quality texture), so your modified "body_white00_f_c_ultra.xbt" (or medium/high) becomes "body_white00_f_c.xbt".

Im curious though, the files you mentioned are only really interesting if you want to modify human body textures...
 

Wow Cobra, thank you so much! Worked like charm!  
Will be adding some cool tattoos to my team today lol

I don't think you will succeed, because this problem has existed since WD2. The point is that the MED file is specific. Currently, there is no tool to convert it, and I am looking for a solution

Look at the file header with the lowest texture, It must read both med and high files



01.png (69.76 KiB) Viewed 415 times
## Post #52
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2020-12-06T13:09:14+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from atomicool ↑Sat Dec 05, 2020 6:58 pm at Sat Dec 05, 2020 6:58 pm
>
> 
maryrangel wrote: ↑Fri Dec 04, 2020 4:06 am
CobraGamer wrote: ↑Fri Dec 04, 2020 3:31 am
@maryangel: You can indeed force the game to load only one specific texture without its medium, high or ultra versions. You simply have to remove the affix from the file name (and keep the XBT header of the original higher quality texture), so your modified "body_white00_f_c_ultra.xbt" (or medium/high) becomes "body_white00_f_c.xbt".

Im curious though, the files you mentioned are only really interesting if you want to modify human body textures...
 

Wow Cobra, thank you so much! Worked like charm!  
Will be adding some cool tattoos to my team today lol


I don't think you will succeed, because this problem has existed since WD2. The point is that the MED file is specific. Currently, there is no tool to convert it, and I am looking for a solution

Look at the file header with the lowest texture, It must read both med and high files
01.png

Hey there! Thanks for the reply! Renaming the highest texture like Cobragamer said in his post did the work! But if you come up with a converter let us know!

Ps: what dds format for normals you all find has the best compatibility in game? and what plugin is best? There are some minor issues with intel bc5, and Nvidia 3dc

********
UPDATE:

If anyone else is having trouble with the dds for the normals, download the newer photoshop plugin at Nvidia’s website and save as bc5
## Post #53
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-12-06T15:17:07+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

@atomicool: That's the trick with the method I described. By removing those references, you can force the game to read just that one texture.
## Post #54
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2020-12-09T20:48:26+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Speaking of textures, I don't know if anyone knows the deal with those .xbt files that shows "ZOLA" when you open those with the hex editor?


The only place I discovered where .dds files are discussed, along with "ZOLA", is another topic here at xentax about Watch Dogs 2:
[viewtopic.php?t=15567&start=165](https://forum.xentax.com/viewtopic.php?t=15567&start=165)

Anyhow, what I found out is that most of those files I've encountered, correspond well with BC7 DDS.
Take the logo at the back of the hoodie at the picture below for example:

london_ultra\graphics\characters\wd3\motifs\logos\brand_fydel_multi_01_ultra.xbt

When I copy the data of said .xbt file into a blank BC7 DDS file of the same format (512x512px without mipmaps in this case)...


...then it will open just fine into photoshop.




It is probably not the most efficient way to do it, but it works fine for me.

For testing purposes, I've changed the logo into an "X" before reversing the process...


...and it seems to work fine ingame.


During the reverse process I've saved the dds as BC7 8bpp Fine (sRGB, DX11+) with the intel plugin and removed "ultra" from the xbt's filename as CobraGamer suggests.
## Post #55
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2020-12-09T21:56:57+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Nobody seems to know what exactly this ZOLA format is, might be some kind of proprietary format. One thing is for sure though, we don't have tools to convert those yet.
## Post #56
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-12-11T05:27:40+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Thu Dec 10, 2020 4:48 am at Thu Dec 10, 2020 4:48 am
>
> 
Speaking of textures, I don't know if anyone knows the deal with those .xbt files that shows "ZOLA" when you open those with the hex editor?


The only place I discovered where .dds files are discussed, along with "ZOLA", is another topic here at xentax about Watch Dogs 2:
viewtopic.php?t=15567&start=165

Anyhow, what I found out is that most of those files I've encountered, correspond well with BC7 DDS.
Take the logo at the back of the hoodie at the picture below for example:

london_ultra\graphics\characters\wd3\motifs\logos\brand_fydel_multi_01_ultra.xbt

When I copy the data of said .xbt file into a blank BC7 DDS file of the same format (512x512px without mipmaps in this case)...


...then it will open just fine into photoshop.




It is probably not the most efficient way to do it, but it works fine for me.

For testing purposes, I've changed the logo into an "X" before reversing the process...


...and it seems to work fine ingame.


During the reverse process I've saved the dds as BC7 8bpp Fine (sRGB, DX11+) with the intel plugin and removed "ultra" from the xbt's filename as CobraGamer suggests.

this ZOLA is so weird,can u open it?


 decal_mural_village_underground_04_albedo_high.7z
(99.98 KiB) Downloaded 19 times
## Post #57
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2020-12-11T14:02:09+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from atomicool ↑Fri Dec 11, 2020 1:27 pm at Fri Dec 11, 2020 1:27 pm
>
> 
this ZOLA is so weird,can u open it?
I took a quick look at your file. It seems that it also has an ultra version so I've started with that one.
When I look at the filesize then it might have rectangular dimensions with several MIP maps, my guess is 2048x1024 or 1024x2048 pixels.
That is if this .xbt contains a BC7 DDS that is. It might be a another type of DDS as well.

If it does contain MIP maps somehow, then it will complicate the matter, because I'll have to find out how many MIP maps are used before I can open it.

If you can provide me with an ingame screenshot of the mural where you think the .xbt belongs to, that might help.
## Post #58
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2020-12-11T19:33:22+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from atomicool ↑Fri Dec 11, 2020 1:27 pm at Fri Dec 11, 2020 1:27 pm
>
> 
this ZOLA is so weird,can u open it?

Okay this one was trickier, but I found it!

• decal_mural_village_underground_04_albedo.xbt --> 7BC DDS, 64x32px, 7 MIP maps;
• decal_mural_village_underground_04_albedo_med.xbt --> 7BC DDS, 256x128px, 2 MIP maps;
• decal_mural_village_underground_04_albedo_high.xbt --> 7BC DDS, 512x256px, no MIP maps;
• decal_mural_village_underground_04_albedo_ultra.xbt --> 7BC DDS, 2048x1024px, 2 MIP maps.

You can find the .dds files via the link below.

[https://www.dropbox.com/s/y57ny5kkbai8n ... ds.7z?dl=0](https://www.dropbox.com/s/y57ny5kkbai8n6k/decal_mural_village_underground_04_albedo.dds.7z?dl=0)
## Post #59
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-12-12T03:24:57+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Sat Dec 12, 2020 3:33 am at Sat Dec 12, 2020 3:33 am
>
> 
atomicool wrote: ↑Fri Dec 11, 2020 1:27 pm
this ZOLA is so weird,can u open it?


Okay this one was trickier, but I found it!

• decal_mural_village_underground_04_albedo.xbt --> 7BC DDS, 64x32px, 7 MIP maps;
• decal_mural_village_underground_04_albedo_med.xbt --> 7BC DDS, 256x128px, 2 MIP maps;
• decal_mural_village_underground_04_albedo_high.xbt --> 7BC DDS, 512x256px, no MIP maps;
• decal_mural_village_underground_04_albedo_ultra.xbt --> 7BC DDS, 2048x1024px, 2 MIP maps.

You can find the .dds files via the link below.

https://www.dropbox.com/s/y57ny5kkbai8n ... ds.7z?dl=0

cool!how does this work?because it looks a little bit different from your example above
## Post #60
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2020-12-13T14:15:22+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> cool!how does this work?because it looks a little bit different from your example above

I'll see that I create some time to explain in in a .pdf or such. Because there's a little more to it than what I've posted earlier.
## Post #61
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2020-12-13T14:48:16+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Sun Dec 13, 2020 10:15 pm at Sun Dec 13, 2020 10:15 pm
>
> 

cool!how does this work?because it looks a little bit different from your example above


I'll see that I create some time to explain in in a .pdf or such. Because there's a little more to it than what I've posted earlier.

Looking forward to it! it seems that this Zola problem will be solved by you!
## Post #62
- Username: BartOss
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 15, 2020 4:39 pm
- Post datetime: 2020-12-16T16:57:53+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hey guys, can someone explain how to extract the london_sound.dat file? To get audio from the game. Because I've used any scripts in this topic, and everyting what I got: the scripts doing nothing or asking to press any button to exit... Any help would be appreciated! 

Okay, I'm dumb. Thanks all who supported this thread and forum
## Post #63
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-17T22:29:05+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from maryrangel ↑Thu Dec 03, 2020 1:40 am at Thu Dec 03, 2020 1:40 am
>
> 
The repacker works beautifully! Thank you!

Now I was wondering if someone could give me some help with texture modding!
I noticed the game’s high textures for body parts are DXT1 without mipmaps, and modding them work fine! (Unfortunately you can only see them if you zoom in very close to the mesh, because that’s the only time the game loads them)
On the other hand, weirdly, the game uses medium quality textures to show on the mesh at distance, and these medium textures have mipmaps.
All good up to here, they are also DXT1 and you would think they can be saved as such with auto generated mipmaps and it would work fine, but it doesn’t.
When I try to use modded medium skin textures it looks all off, I mean the texture loads in game but kinda blurry or out of place.
If only I knew how to properly save them (I did notice the modded dds texture is 1 kb off on all medium textures when I save them) or if I could at least force the game to only read the “high” textures and stop loading the medium one - thought I would see if someone here has already been through the challenge and know a fix?
I never modded WD2 so im not sure if it’s something known for the community.

Any help would be appreciated! Ps: the textures, high and medium I mentioned above are in: graphics/characters/body/body_parts/white00 (or black00 or arab00)/

can you show me how to use repacker i finished edit of texture but can not repack
## Post #64
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-17T22:30:15+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from deylone ↑Thu Dec 03, 2020 5:18 pm at Thu Dec 03, 2020 5:18 pm
>
> 
Many thanks for the packer. I have managed to use the recombine option to modify config files as desired. I didn't try anything else so I won't be of much help on questions related to xbg or textures.

can you show me how to use repacker i finished edit of texture but can not repack
## Post #65
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-17T22:32:08+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Thu Dec 10, 2020 4:48 am at Thu Dec 10, 2020 4:48 am
>
> 
Speaking of textures, I don't know if anyone knows the deal with those .xbt files that shows "ZOLA" when you open those with the hex editor?


The only place I discovered where .dds files are discussed, along with "ZOLA", is another topic here at xentax about Watch Dogs 2:
viewtopic.php?t=15567&start=165

Anyhow, what I found out is that most of those files I've encountered, correspond well with BC7 DDS.
Take the logo at the back of the hoodie at the picture below for example:

london_ultra\graphics\characters\wd3\motifs\logos\brand_fydel_multi_01_ultra.xbt

When I copy the data of said .xbt file into a blank BC7 DDS file of the same format (512x512px without mipmaps in this case)...


...then it will open just fine into photoshop.




It is probably not the most efficient way to do it, but it works fine for me.

For testing purposes, I've changed the logo into an "X" before reversing the process...


...and it seems to work fine ingame.


During the reverse process I've saved the dds as BC7 8bpp Fine (sRGB, DX11+) with the intel plugin and removed "ultra" from the xbt's filename as CobraGamer suggests.

can you show me how to use repacker i finished edit of texture but can not repack
## Post #66
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-17T22:32:58+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

can you show me how to use repacker i finished edit of texture but can not repack
## Post #67
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-18T12:22:39+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Thu Dec 10, 2020 4:48 am at Thu Dec 10, 2020 4:48 am
>
> 
Speaking of textures, I don't know if anyone knows the deal with those .xbt files that shows "ZOLA" when you open those with the hex editor?


The only place I discovered where .dds files are discussed, along with "ZOLA", is another topic here at xentax about Watch Dogs 2:
viewtopic.php?t=15567&start=165

Anyhow, what I found out is that most of those files I've encountered, correspond well with BC7 DDS.
Take the logo at the back of the hoodie at the picture below for example:

london_ultra\graphics\characters\wd3\motifs\logos\brand_fydel_multi_01_ultra.xbt

When I copy the data of said .xbt file into a blank BC7 DDS file of the same format (512x512px without mipmaps in this case)...


...then it will open just fine into photoshop.




It is probably not the most efficient way to do it, but it works fine for me.

For testing purposes, I've changed the logo into an "X" before reversing the process...


...and it seems to work fine ingame.


During the reverse process I've saved the dds as BC7 8bpp Fine (sRGB, DX11+) with the intel plugin and removed "ultra" from the xbt's filename as CobraGamer suggests.

hi do you replace old xbt with new one ?
## Post #68
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2021-01-18T20:56:26+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from tonilai2012 ↑Mon Jan 18, 2021 8:22 pm at Mon Jan 18, 2021 8:22 pm
>
> 
hi do you replace old xbt with new one ?
First I make a backup of the original vanilla xtb file (recommended). Then I "convert" the modded dds file back into xtb by copying the dds's data with a hex editor and paste it into the original xtb, overwriting the vanilla data. Basicly the same way how I explained my method of "coverting" xtb to dds but reversed.

> Reply from tonilai2012 ↑Mon Jan 18, 2021 6:32 am at Mon Jan 18, 2021 6:32 am
>
> 
can you show me how to use repacker i finished edit of texture but can not repack
The approach I take to use the modded files ingame is by merging the modded files into patch.dat/.fat with the repacker.

1) Move or copy your modded xtb file into a map (for example "map1"). The xtb needs to be stored into the same submaps like it was originally stored into the dat archive (for example "graphics\characters\wd3\....\<<your xtb file>>)
2) Move or copy patch.dat and patch.fat into another map (for example "map2").
3) Open notepad and type the following command: PackLegion.exe map1 patch.fat map2\patch.fat
Then save that file as "repack.bat"
4) Move or copy "map1", "map2" and "repack.bat" into the same map where "PackLegion.exe" is stored and double click at "repack.bat".
5) A modded "patch.dat" and "patch.fat" will appear into the same map as "PackLegion.exe".

It's also recommended to create a backup of patch.dat/.fat before storing the modded ones into the installation map (C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\games\Watch Dogs Legion\data_win64\...).
## Post #69
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-20T23:23:34+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

thanks for help will give a try
## Post #70
- Username: tonilai2012
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 28, 2012 9:47 pm
- Post datetime: 2021-01-22T21:28:27+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

sorry but when i try to do it shows Exception.ToString,does map means folder path?
## Post #71
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2021-01-27T23:38:51+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from tonilai2012 ↑Sat Jan 23, 2021 5:28 am at Sat Jan 23, 2021 5:28 am
>
> 
sorry but when i try to do it shows Exception.ToString,does map means folder path?
I've added "WDL_repacker.zip" as an attachment. This zip file contains a setup that you can unpack and use for merging your modded files with "patch.fat" and "patch.dat". I've also provided it with a readme file so you can see step by step what you'll have to do to make it work.

I couldn't add "PackLegion.exe" to the zip file because it isn't my program and I haven't asked permission at the creator to distribute it myself.
So you'll have to copy "PackLegion.exe" into the setup yourself.

Good luck!

PS: Just to be clear, the attachment into this post is only a ready made setup for easier use of one the functions of the repacker. The actual repacker still has to be copied into this setup before you can use it. A link to the actual repacking program is provided at the following post into this topic:
viewtopic.php?f=10&t=22903&start=30#p169121
I've also removed the attachment and uploaded it again with another filename, to prevent misunderstandings.
[setup_for_WDL_repacker.zip](https://xentaxbackup.github.io/file/19452_setup_for_WDL_repacker.zip)
## Post #72
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2021-02-02T20:44:02+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Sun Dec 13, 2020 10:15 pm at Sun Dec 13, 2020 10:15 pm
>
> 

cool!how does this work?because it looks a little bit different from your example above


I'll see that I create some time to explain in in a .pdf or such. Because there's a little more to it than what I've posted earlier.
Okay, It took me a while to prepare, but at following link you'll find some sort of manual in which I show how to convert ZOLA .xbt files to .dds and back to .xbt with the help of a hex editor:
[https://www.dropbox.com/s/ck8mubmxhc5bg ... s.pdf?dl=0](https://www.dropbox.com/s/ck8mubmxhc5bgjc/how%20convert%20watch%20dogs%20legion%27s%20zola%20xbt%20to%20dds.pdf?dl=0)

A more efficient method is described in there then the one I've provided earlier at this topic. The manual also covers conversion of .xbt and .dds files with mip maps.
## Post #73
- Username: superdemus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Dec 02, 2014 7:19 pm
- Post datetime: 2021-02-04T00:58:18+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Thu Jan 28, 2021 7:38 am at Thu Jan 28, 2021 7:38 am
>
> 
tonilai2012 wrote: ↑Sat Jan 23, 2021 5:28 am
sorry but when i try to do it shows Exception.ToString,does map means folder path?
I've added "WDL_repacker.zip" as an attachment. This zip file contains a setup that you can unpack and use for merging your modded files with "patch.fat" and "patch.dat". I've also provided it with a readme file so you can see step by step what you'll have to do to make it work.

I couldn't add "PackLegion.exe" to the zip file because it isn't my program and I haven't asked permission at the creator to distribute it myself.
So you'll have to copy "PackLegion.exe" into the setup yourself.

Good luck!
It looks like, since recent updates, that "patch.dat" reached a filesize of almost 5Gb and the repacker seems to have trouble with merging modded files into it. So I've prepared an alternate setup that will make use of "patch_english.dat" (which for now has a filesize of only 374Mb) instead. Until now it works fine for me.

PS: Just to be clear, the attachment into this post is only a ready made setup for easier use of one the functions of the repacker. The actual repacker still has to be copied into this setup before you can use it. A link to the actual repacking program is provided at the following post into this topic: viewtopic.php?f=10&t=22903&start=30#p169121
[alternate_setup_for_WDL_repacker.zip](https://xentaxbackup.github.io/file/19463_alternate_setup_for_WDL_repacker.zip)
## Post #74
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2021-02-04T04:19:13+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from superdemus ↑Thu Feb 04, 2021 8:58 am at Thu Feb 04, 2021 8:58 am
>
> 
superdemus wrote: ↑Thu Jan 28, 2021 7:38 am
tonilai2012 wrote: ↑Sat Jan 23, 2021 5:28 am
sorry but when i try to do it shows Exception.ToString,does map means folder path?
I've added "WDL_repacker.zip" as an attachment. This zip file contains a setup that you can unpack and use for merging your modded files with "patch.fat" and "patch.dat". I've also provided it with a readme file so you can see step by step what you'll have to do to make it work.

I couldn't add "PackLegion.exe" to the zip file because it isn't my program and I haven't asked permission at the creator to distribute it myself.
So you'll have to copy "PackLegion.exe" into the setup yourself.

Good luck!
It looks like, since recent updates, that "patch.dat" reached a filesize of almost 5Gb and the repacker seems to have trouble with merging modded files into it. So I've prepared an alternate setup that will make use of "patch_english.dat" (which for now has a filesize of only 374Mb) instead. Until now it works fine for me.

PS: Just to be clear, the attachment into this post is only a ready made setup for easier use of one the functions of the repacker. The actual repacker still has to be copied into this setup before you can use it. A link to the actual repacking program is provided at the following post into this topic: viewtopic.php?f=10&t=22903&start=30#p169121
Most of them can be packaged into patch_english.dat,but some have to be in patch.dat.
Of course, all textures can be packaged into patch_english.dat,It's very convenient.
## Post #75
- Username: Dantian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 05, 2021 3:52 pm
- Post datetime: 2021-05-05T08:25:02+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hi everyone, i'm a modding noob but interested in altering WDL textures.

I've read through this thread, but still a little confused on the exact process. Do I need to extract/convert the Patch.dat file before starting in order to isolate the specific files I want to focus on? And how do I do that?

Otherwise, can I alter/extract files directly through a Hex editor? 

Thanks in advance for any guidance you can offer - and I apologize for my dumb questions and lack of knowledge.
## Post #76
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-05-06T11:28:49+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Can someone plz explain how to unpack this??   all i get is this and 1,000's of blank folders. How come it keeps saying "decompression failed" ?

[](https://ibb.co/S6kwdV9)
## Post #77
- Username: 0l0l0ft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 06, 2021 5:39 am
- Post datetime: 2021-08-14T20:33:59+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

importer to support Watch Dogs Legion??
## Post #78
- Username: SongAndDance
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 14, 2017 11:56 pm
- Post datetime: 2021-08-15T23:16:44+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Haway folks. Has anybody had any luck converting oasisstrings.rml to a readable format? 

I've tried with Gibbed's amazing Disrupt tools, but it doesn't appear to work with that specific file. 

Thanks in advance.
## Post #79
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2021-08-28T19:12:21+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

oasisstrings.rml and other files from Legion can be converted using the newest version of Gibbed's Disrupt tools.

I'm afraid I can't give an ETA for updates of PackLegion or ManageLegion. I'll probably get around to it soon-ish.
## Post #80
- Username: CobraGamer
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Apr 16, 2016 2:30 pm
- Post datetime: 2021-09-05T16:49:05+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

ManageLegion v1.02 with support for large archives is now available: [https://github.com/rootCBR/ManageLegion](https://github.com/rootCBR/ManageLegion)
## Post #81
- Username: leonhardt95
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 29, 2021 4:31 am
- Post datetime: 2021-09-05T18:30:26+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

thx cobragamer for your updates on your work you are awsome
## Post #82
- Username: ELextend
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 15, 2019 5:38 am
- Post datetime: 2021-12-21T07:34:43+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Keep getting "decompression failed" on many files.
Regardless of wich fat file I try to unpack.
I need specific files, libs mostly, but almost all of those I need are failed and not showing, althoe they are listed in filelist.

Tried latest version from github, but this dont work at all for me:

```
===== UnpackLegion v1.123-rel =====
Loading file list...
Extracting files...
System.NotSupportedException: Unsupported compression scheme
   at UnpackLegion.Program.<Work>g__Export|1_1(FatEntry entry, Object filePath,
Stream stream, <>c__DisplayClass1_0& )
   at UnpackLegion.Program.Work()
   at UnpackLegion.Program.Main(String[] args)
Press any key to close...
```


Can I get any help, please?
## Post #83
- Username: jayoh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 25, 2022 3:26 am
- Post datetime: 2022-04-28T15:11:12+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hi guys. Thanks for all your incredible work and tools. I was monitoring XeNTaX forums for years and they always were a great help.
However it seems I stumbled upon a problem which I can't figure out myself.

I am trying to extract sound files from patch_english file (using UnpackLegion). I get lots of 1KB *.bnk/*.wem files which I can't convert to *.ogg. They just seem empty to me. What could be the problem?

An attempt to convert these small files with Wwise-Unpacker prompts a "A duplicate file name exists, or the file cannot be found" error in console and results in a no output whatsoever.

I've tried several times and the result is always the same.

Any help is appreciated.
## Post #84
- Username: jayoh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 25, 2022 3:26 am
- Post datetime: 2022-05-01T08:53:28+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

> Reply from jayoh ↑Thu Apr 28, 2022 11:11 pm at Thu Apr 28, 2022 11:11 pm
>
> 
Hi guys. Thanks for all your incredible work and tools. I was monitoring XeNTaX forums for years and they always were a great help.
However it seems I stumbled upon a problem which I can't figure out myself.

I am trying to extract sound files from patch_english file (using UnpackLegion). I get lots of 1KB *.bnk/*.wem files which I can't convert to *.ogg. They just seem empty to me. What could be the problem?

An attempt to convert these small files with Wwise-Unpacker prompts a "A duplicate file name exists, or the file cannot be found" error in console and results in a no output whatsoever.

I've tried several times and the result is always the same.

Any help is appreciated.

Ok, I figured it out. I still don't know what are those 1KB files are, but most of the sound files from patch_english archive goes to _unknown folder without any extension and could be converted to *ogg (except another bunch of 1KB files).
## Post #85
- Username: avialaynen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 28, 2022 2:27 am
- Post datetime: 2022-06-27T18:55:30+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

Hi. I read the topic and still can't find it: how can I unpack .dat files?
## Post #86
- Username: kosemen76
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 05, 2019 6:05 am
- Post datetime: 2023-03-14T18:56:25+00:00
- Post Title: Re: Watch Dogs: Legion .dat .fat archives

[https://dosya.co/7me3hnogzya4/wath_dogs.rar.html](https://dosya.co/7me3hnogzya4/wath_dogs.rar.html)
I couldn't use PS3 file tools, can you help me?
