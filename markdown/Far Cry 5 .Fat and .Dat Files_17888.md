## Post #1
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-03-27T23:24:14+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

FC5 just came out, but it seems to use a different version of the fat and dat format than Watch Dogs (the only (kind of) Dunia Engine game I've modded). I was hoping somebody would be up to reverse engineering them, as I have no clue how (-:

Thanks,
TrumpetPro
## Post #2
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T15:40:07+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from TrumpetPro
>
> FC5 just came out, but it seems to use a different version of the fat and dat format than Watch Dogs (the only (kind of) Dunia Engine game I've modded). I was hoping somebody would be up to reverse engineering them, as I have no clue how (-:

Thanks,
TrumpetPro

I recently dig through the archives and found some information from the new header format of models and file names that are packed into the .dat archive.
  The .xbg header is HSEMG, but unfortunately the importers of the previous headlight parts can not import the .xbg file.
[https://drive.google.com/open?id=1WIM6g ... fDc4ZixxpY](https://drive.google.com/open?id=1WIM6gC09LD11Y6a7YQVZfNfDc4ZixxpY) Here is a model from FC5, got from igepack.dat
From one archive it is possible to extract a picture of the map editor by hex by hex, so far everything has been able to find out about this.
Sorry for my clumsy English =)
[3.png](https://xentaxbackup.github.io/file/14105_3.png)
## Post #3
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-28T15:48:31+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

The new file format ?
## Post #4
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T15:49:58+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> The new file format ?
XBG file format
[hex_img.JPG](https://xentaxbackup.github.io/file/14107_hex_img.JPG)
## Post #5
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-28T15:53:14+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> HamMerRon wrote:The new file format ?
I can not say exactly which file format, but I'm sure that it's the same as in the other version of FC...

So, as in FC Primal you need a database of files in xml
## Post #6
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T15:56:51+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:The new file format ?
I can not say exactly which file format, but I'm sure that it's the same as in the other version of FC...

So, as in FC Primal you need a database of files in xml

Unfortunately, I do not know the skill in hex, but I understand some of it, I was convinced that the unpacker FC Primal unpacks the archives of FC5, but at some stage unpacks it crashes, the contents of the files show, but there is no structure in the hex). Game downloaded via torrent
## Post #7
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T17:25:46+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:The new file format ?
I can not say exactly which file format, but I'm sure that it's the same as in the other version of FC...

So, as in FC Primal you need a database of files in xml
Can I get a list of files in xml for the dune engine from fc5
Using only hex?
## Post #8
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-28T17:41:52+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

So far I understand this
## Post #9
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T18:06:30+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> So far I understand this
I decompiled IGE.WPF.Core64.dll and it has pictures from FC 3 and FC2))
[hex_img2.JPG](https://xentaxbackup.github.io/file/14108_hex_img2.JPG)
## Post #10
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-28T18:21:12+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> HamMerRon wrote:So far I understand this
I decompiled IGE.WPF.Core64.dll and it has pictures from FC 3 and FC2))
Cool, if I'm not mistaken this is the dll file of the arcade mode
## Post #11
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T18:31:52+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:So far I understand this
I decompiled IGE.WPF.Core64.dll and it has pictures from FC 3 and FC2))
Cool, if I'm not mistaken this is the dll file of the arcade mode
In the Visual Studio 2017 compilation is not possible, only as for educational purposes.
source IGE.WPF.Core64.dll: [https://drive.google.com/open?id=15OnWU ... VwB0IQ5GiS](https://drive.google.com/open?id=15OnWUQX6xdV9meyIjzcLZkVwB0IQ5GiS)
## Post #12
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-28T18:41:12+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

Now it remains to find a way to get the file names for the xml database
## Post #13
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T18:47:55+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Now it remains to find a way to get the file names for the xml database
The names of the database can be found through hex, but for now I was able to find (хbt/bin), the names of the models themselves (.xbg) are hard to find for me, because some lines are not valid letters, but they can be appended, since most of them are repeated, an example (_textures \ folder\*.xbg/xbt).
[hex_img1.JPG](https://xentaxbackup.github.io/file/14109_hex_img1.JPG)
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2018-03-28T19:37:54+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

Will be watching this thread for progress!

Thanks alot guys.
## Post #15
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-28T23:13:38+00:00
- Post Title: Far Cry 5 .Fat and .Dat Files

Rewrote a small list of data (*.fcb) files.
The archive itself weighs 10.6 GB
[fcp_dunia_filelist_for_fc5_list.zip](https://xentaxbackup.github.io/file/14120_fcp_dunia_filelist_for_fc5_list.zip)
## Post #16
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T08:28:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Rewrote a small list of data (*.fcb) files.
The archive itself weighs 10.6 GB
xbg files are not easy to find
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T08:53:33+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I can try to make logger for filenames but i do not have a game. If someone can share account for me (UPlay or Steam (Famaly sharing) I will be grateful
## Post #18
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T08:58:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> I can try to make logger for filenames but i do not have a game. If someone can share account for me (UPlay or Steam (Famaly sharing) I will be grateful
[https://drive.google.com/open?id=1EfCuD ... tgr_rgJWJG](https://drive.google.com/open?id=1EfCuDg9M238ki_XGG-D-EUtgr_rgJWJG) please
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T08:59:34+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Anyway for launch i need account
## Post #20
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T09:02:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Anyway for launch i need account
[https://www.plati.market/itm/far-cry-5- ... ee/2451815](https://www.plati.market/itm/far-cry-5-uplay-garantija-region-free/2451815)
## Post #21
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T09:08:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

To do something for free, do I have to pay? Bad idea. I need an account for a maximum of 15-30 min
## Post #22
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T09:12:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> To do something for free, do I have to pay? Bad idea. I need an account for a maximum of 15-30 min
I have an account, I'll discard it later, as soon as I download)
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T15:21:02+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Here is hook. Thx to Haoose for tests. Extract to bin folder, play. After you can see FC5.log with filenames.
[FC5Hook_0.01_r1.rar](https://xentaxbackup.github.io/file/14129_FC5Hook_0.01_r1.rar)
## Post #24
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T16:14:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Here is hook. Thx to Haoose for tests. Extract to bin folder, play. After you can see FC5.log with filenames.
Can I get a list of files in the log through the map editor?
## Post #25
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T16:58:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Here is hook. Thx to Haoose for tests. Extract to bin folder, play. After you can see FC5.log with filenames.
Your dinput8.dll produces an error when starting the game
Unrecoverable application error.
[err.jpg](https://xentaxbackup.github.io/file/14131_err.jpg)
## Post #26
- Username: classlion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 30, 2018 1:06 am
- Post datetime: 2018-03-29T17:11:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hi. Maybe someone know, how can i extract sound files?
## Post #27
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T17:16:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from classlion
>
> Hi. Maybe someone know, how can i extract sound files?
So far this is not possible.
## Post #28
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T17:24:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ganic3000, try to run on behalf of the admin
## Post #29
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T17:36:47+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000, try to run on behalf of the admin
The same error occurred when starting on behalf of the administration.
## Post #30
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T17:44:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> HamMerRon wrote:Ganic3000, try to run on behalf of the admin
The same error occurred when starting on behalf of the administration.
It seems that FC5 is very sensitive to user intervention
## Post #31
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T17:45:59+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:Ganic3000, try to run on behalf of the admin
The same error occurred when starting on behalf of the administration.
It seems that FC5 is very sensitive to user intervention
I did not look there, the list of files in another folder was))
## Post #32
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T17:52:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Have you thrown the file there?))
## Post #33
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T17:57:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
## Post #34
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T18:06:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> HamMerRon wrote:Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
cool)
## Post #35
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T18:30:32+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
cool)
I got a lot of identical lines)), the unpacker crashes because of this).
## Post #36
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T18:34:54+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:HamMerRon wrote:Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
cool)
[0hex_img.JPG](https://xentaxbackup.github.io/file/14132_0hex_img.JPG)
## Post #37
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T18:48:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

[https://drive.google.com/open?id=178z5x ... tdBq_kHZUU](https://drive.google.com/open?id=178z5xhOARQ3FwC2wiEp91DtdBq_kHZUU)
## Post #38
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T18:56:39+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> https://drive.google.com/open?id=178z5x ... tdBq_kHZUU
repack the file
[error.jpg](https://xentaxbackup.github.io/file/14134_error.jpg)
## Post #39
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T18:59:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:https://drive.google.com/open?id=178z5x ... tdBq_kHZUU
repack the file
[https://drive.google.com/open?id=1pujtm ... FRSXBUCTjz](https://drive.google.com/open?id=1pujtm_uA12JlcJitgQUeomFRSXBUCTjz)
## Post #40
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T19:36:35+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I managed to pull out the audio files of several pieces and a video clip.
Audio files are partially incorrect and I get only noise.
[0hex_img.JPG](https://xentaxbackup.github.io/file/14135_0hex_img.JPG)
## Post #41
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T19:43:58+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I realized that without the new exe decoder unpacker, the archives can not be extracted correctly.
## Post #42
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-29T19:47:21+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> I realized that without the new exe decoder unpacker, the archives can not be extracted correctly.

And what about the models
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T19:47:59+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Ekey wrote:Here is hook. Thx to Haoose for tests. Extract to bin folder, play. After you can see FC5.log with filenames.
Your dinput8.dll produces an error when starting the game
Unrecoverable application error.
As i said already > I do not have a game to test it completely.

> Reply from Ganic3000
>
> HamMerRon wrote:Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
You need remove duplicates. In this case, there are only 32,353 unique names.

Btw: Hook tested with bypassed EAC - [here](http://fearlessrevolution.com/viewtopic.php?f=4&t=6334)
## Post #44
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T19:50:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Ganic3000 wrote:I realized that without the new exe decoder unpacker, the archives can not be extracted correctly.

And what about the models
Models can not be pulled out without a decoder, in hex you can find only names, partially zabinarenye letters.
## Post #45
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T19:50:51+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

How will I delete them, there are a lot of them?))
## Post #46
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T20:02:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Ganic3000 wrote:Ekey wrote:Here is hook. Thx to Haoose for tests. Extract to bin folder, play. After you can see FC5.log with filenames.
Your dinput8.dll produces an error when starting the game
Unrecoverable application error.
As i said already > I do not have a game to test it completely.
Ganic3000 wrote:HamMerRon wrote:Have you thrown the file there?))
Since the game itself did not run from this dll, I tried to start the map editor, and I understand that this list was obtained through the map editor.
I got 189.818 rows in the log file.
You need remove duplicates. In this case, there are only 32,353 unique names.

Btw: Hook tested with bypassed EAC - here

What exactly does this bypass give?
## Post #47
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T20:35:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

The game has audio files in (.bnk\.wem) which, I believe, were packaged through (Wwise). 
[0hex_img.JPG](https://xentaxbackup.github.io/file/14137_0hex_img.JPG)
## Post #48
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-03-29T22:01:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Your dinput8.dll produces an error when starting the game
Unrecoverable application error.

Use bypass EAC

> Reply from Ganic3000
>
> Can I get a list of files in the log through the map editor?
I don't know.

> Reply from Ganic3000
>
> What exactly does this bypass give?
You will not receive this message
## Post #49
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T22:06:15+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Ganic3000 wrote:Can I get a list of files in the log through the map editor?
I don't know.

So far, only this was able to get from the list of files, except for models.
Duplicates tried to remove.
log file list fc5 [https://drive.google.com/open?id=1_ERIU ... iIHvELSOBL](https://drive.google.com/open?id=1_ERIU8PtaCuBxUWd-aK7hMiIHvELSOBL)
## Post #50
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-29T22:19:28+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Ganic3000 wrote:Your dinput8.dll produces an error when starting the game
Unrecoverable application error.

Use bypass EAC
Ganic3000 wrote:Can I get a list of files in the log through the map editor?
I don't know.
Ganic3000 wrote:What exactly does this bypass give?
You will not receive this message

This does not help, the error still appears, but the game continues to run and the log file is replenished.
## Post #51
- Username: mlleemiles
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2018-03-29T23:09:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

54611 filenames here
[FileNames-54611.rar](https://xentaxbackup.github.io/file/14138_FileNames-54611.rar)
## Post #52
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-30T14:13:03+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> 

As i said already > I do not have a game to test it completely.

If I give you a game account, you can create unpack.exe? Just unpack primal cannot correctly file at some time of the accident.
## Post #53
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-30T16:26:51+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Partially you can extract png-images from the map editor archive through the dragon unpacker.
Audio files can also be pulled out, but they are not correctly played.
You can also extract video files (.bik).
[https://drive.google.com/open?id=1WKAr1 ... DovF2yKult](https://drive.google.com/open?id=1WKAr1VVa7ngGGrYgfDXn10DovF2yKult)
## Post #54
- Username: HamMerRon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 01, 2017 2:07 am
- Post datetime: 2018-03-30T16:37:35+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hope to see models soon
## Post #55
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-30T16:51:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from HamMerRon
>
> Hope to see models soon
Models can be seen through the model researcher.
Only knowledge of hex is needed to convert, at least, into a (obj) file.
## Post #56
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2018-03-30T19:35:00+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I got a lot of identical lines)), the unpacker crashes because of this).[/quote]

where is the unpacker?
## Post #57
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-30T20:21:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from iambosh
>
> I got a lot of identical lines)), the unpacker crashes because of this).

where is the unpacker?

Describe in detail the problem of unpacking.
## Post #58
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2018-03-30T23:16:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> iambosh wrote:I got a lot of identical lines)), the unpacker crashes because of this).

where is the unpacker?

Describe in detail the problem of unpacking.

Honestly im not sure what unpacker to use. The dunia tools dont work on the majorty of the fat files. I have the hook installed but I have no clue what to do with the information it provides.
## Post #59
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-03-30T23:20:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Created a Discord server for modding the Far Cry series.
[https://www.reddit.com/r/farcry/comment ... g_discord/](https://www.reddit.com/r/farcry/comments/88eiir/far_cry_series_modding_discord/)
## Post #60
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-03-31T16:07:31+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from iambosh
>
> Ganic3000 wrote:iambosh wrote:I got a lot of identical lines)), the unpacker crashes because of this).

where is the unpacker?

Describe in detail the problem of unpacking.

Honestly im not sure what unpacker to use. The dunia tools dont work on the majorty of the fat files. I have the hook installed but I have no clue what to do with the information it provides.
I think somebody posted the unpacker earlier. The hook creates a filelist that tells the unpacker names of files. Without the filelist, it will still unpack a few thousand files, but they will have random names so we don't know what does what and things.
## Post #61
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-03-31T16:25:47+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from TrumpetPro
>
> 
Honestly im not sure what unpacker to use. The dunia tools dont work on the majorty of the fat files. I have the hook installed but 
I think somebody posted the unpacker earlier. The hook creates a filelist that tells the unpacker names of files. Without the filelist, it will still unpack a few thousand files, but they will have random names so we don't know what does what and things.

I can get filenames from the game, but without the right unpacker under FC5 it's useless to try to unpack the archives.
I can not yet get the names of the models (.
## Post #62
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-02T17:15:03+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

been looking to get all the audio music files. i hope theirs a way to extract them :/
## Post #63
- Username: Collie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 03, 2018 3:22 pm
- Post datetime: 2018-04-03T08:30:13+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Partially you can extract png-images from the map editor archive through the dragon unpacker.
Audio files can also be pulled out, but they are not correctly played.
You can also extract video files (.bik).
https://drive.google.com/open?id=1WKAr1 ... DovF2yKult

Did you test the video files you were able to extract? I can't pull anything useful with Dragon Unpacker. I'm wanting to get my hands on the source video files of the loading screens for the different regions.
## Post #64
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-03T12:47:09+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

[Here](http://forum.xentax.com/viewtopic.php?p=139333#p139333) unpacker. Some files have different compression and are not supported for now
## Post #65
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-03T13:12:49+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

nice! thank you! where can I follow for updates on this unpacker?
## Post #66
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-03T13:15:58+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

In the this topic
## Post #67
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-03T13:19:05+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

cool so I need the .fat files to read the .dat files? to bad HTTP and HTML are my majors. I wish I got into this language as well. I just want all the music files out of here though I want to compile them all. I did that with far cry 4.
## Post #68
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2018-04-03T18:01:53+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hmm the program crashed as it was loading the files. Used it on far cry 5.dat/fat
## Post #69
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-03T18:04:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

What the archive ?
## Post #70
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2018-04-03T18:25:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ahh nvm, i just moved it out of program files and it worked. 

archive was farcry5.fat/dat

Also wem files are still compressed. Hopoefullyt hat can be figured out. 

Thanks for the tool.
## Post #71
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-04-03T22:14:31+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> What the archive ?
Files .bik has an archive header, so it does not work, check this error.
I added the to archive from fc3 the video for analysis.
[preload.7z](https://xentaxbackup.github.io/file/14163_preload.7z)
## Post #72
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-03T23:11:15+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Files .bik has an archive header, so it does not work, check this error.
I added the to archive from fc3 the video for analysis.
One video works fine



And as i said > Some files have different compression and are not supported for now. I made a new version of unpacker and i will share it later after completly tests.
## Post #73
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-03T23:20:28+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hello; SunBeam from FRF here  Can confirm the unpacker crashes at some point, after passing ~160.000 records in data_final\pc\worlds\farcry5.dat. My interest here are the Lua files, which can easily be decompiled (LuaQ) after the actual LuaQ block's been extracted out of the LUAC wrapper
## Post #74
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-03T23:22:52+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> Hello; SunBeam from FRF here  Can confirm the unpacker crashes at some point, after passing ~100.000 records in data_final\pc\worlds\farcry5.fat. My interest here are the Lua files, which can easily be decompiled (LuaQ) after the actual LuaQ block's been extracted out of the LUAC wrapper
Yeah, it's already fixed. Read my previous post
## Post #75
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-03T23:41:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

..also, invalid files presumably extracted:



Note that the Lua files in common.dat are extracted correctly. Same goes with those in patch.dat, they were extracted properly and can be decompiled:



So I doubt there's a different compression algo in farcry5.dat. Might have to do with the iterator/read cursor/index.

BR,
Sun
## Post #76
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-04T00:25:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Updated [here](http://forum.xentax.com/viewtopic.php?p=139382#p139382)

```
    FC5.Unpacker <m_FATFile> <m_Directory>

    m_FATFile - Source of FAT file
    m_Directory - Destination directory

[Examples]
    FC5.Unpacker D:\FC5\data_final\pc\common.fat D:\Unpacked\common
```
## Post #77
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-04T00:50:46+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Confirming full extraction of farcry5.dat; and faster than previous version 



And the Lua files were extracted correctly; can now decompile them.

BR,
Sun
## Post #78
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-04T03:31:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

the new version my virus scanner is deleting it I turned my virus scanner real time protection off and I unzip it and it wont run like last version :/
## Post #79
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-04T06:14:02+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

^ It is now a command-line tool. And AVs are only for little kids. Just disable/set tool as an exception and use the mentioned syntax.
## Post #80
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-04T06:28:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> ^ It is now a command-line tool. And AVs are only for little kids. Just disable/set tool as an exception and use the mentioned syntax.

 Says the ultra noob xD... Saying they are for little kids ? Maybe novice learners? No one said what I prefer. Command line tool or not, fine and I know what to do, I was merely asking a question. And giving feedback.
## Post #81
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-04T08:26:48+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

It's hardly ONE question with all the punctuation missing. I'm this guy: [http://fearlessrevolution.com/viewtopic.php?f=4&t=6334](http://fearlessrevolution.com/viewtopic.php?f=4&t=6334). And anti-viruses are for ultra-noobs; don't have one installed.

@Ekey: I found several files in the _Unknown folder, Lua files, which can be mapped to actual names (e.g.: 1DC53A544E9EF2D3 == giveplayerammo_v2.lua, which should be in a certain location in the unpacked path). Is there any way to map 1DC53A544E9EF2D3 to this .lua name? I can determine the script name from the LUAC header. Or would it work by simply adding its supposed path to the list in 'Projects'? Asking beforehand, so I know what to do.

Example:



BR,
Sun
## Post #82
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-04-04T08:28:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Ganic3000 wrote:Files .bik has an archive header, so it does not work, check this error.
I added the to archive from fc3 the video for analysis.
One video works fine



And as i said > Some files have different compression and are not supported for now. I made a new version of unpacker and i will share it later after completly tests.

You probably did not understand me, this video from the unpacked game FC3 and the file with the extension .bik from the unpacked game FC5.
## Post #83
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-04T10:11:11+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Yeah, I think I have to add all the missing Lua file names in FileNames.list so they're processed on unpack
## Post #84
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-04T10:16:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> @Ekey: I found several files in the _Unknown folder, Lua files, which can be mapped to actual names (e.g.: 1DC53A544E9EF2D3 == giveplayerammo_v2.lua, which should be in a certain location in the unpacked path). Is there any way to map 1DC53A544E9EF2D3 to this .lua name? I can determine the script name from the LUAC header. Or would it work by simply adding its supposed path to the list in 'Projects'? Asking beforehand, so I know what to do.

BR,
Sun

Correct path for this file is > domino\system\player\giveplayerammo_v2.lua

> Reply from sunbeam906
>
> Yeah, I think I have to add all the missing Lua file names in FileNames.list so they're processed on unpack

Yep 

> Reply from invasion101
>
> the new version my virus scanner is deleting it I turned my virus scanner real time protection off and I unzip it and it wont run like last version :/
False positives. i will disable and recompile after main work
## Post #85
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-04-04T15:40:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I see good progress here. Good job h4x.

Do you think you can make simple XBT to DDS convertor?
I use this syntax in 010 HEX Editor to convert them to DDS.

```
int tbx_headersize;
string FileName;
DeleteBytes(0,tbx_headersize);
FileName=GetFileName();
FileSave(FileName+".dds");
FileClose();
```

But I can't use variable "tbx_headersize" at DeleteBytes, only values. It's pretty limited. And my """programing skills""" sucks.

@SunBeam can you provide updated FileList when you have done it?

Thank you both guys!
## Post #86
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-05T08:23:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

@GRiNDERKILLER: Will do. Coding a tool that cleans that shit up (RadASM) and launches unluac.jar to get them decompiled to plain-text
## Post #87
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-05T11:04:37+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Updated [here](https://www.sendspace.com/file/t6urwd)

* Disabled (:bfuscation
* Unknown files now are placed in individual folders:

```
__Unknown\BNK\
__Unknown\FCB\
__Unknown\LUA\
```


and etc.

* Base of names updated. Removed unused names also added some new names.
## Post #88
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-05T11:39:38+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

^ Ooops, too late  Almost all Lua files now have their names corrected. It's just a matter or removing the LUAC container to decompile by LuaQ (0x51 = 5.1) header.

147E36A8A9F93A6D.lua
data_tmp\pc\_tmp\domino\user\gym_danydomino\activity\domino_actiovity_test.main.lua

799D43DB6DE696B5.lua
domino/user/gym_danydomino/activity/domino_actiovity_test.domino

These remain.

@Ekey: I noticed something interesting in Lua when looking for quirks I can use in a Lua console. There are file references to physical files that don't exist. Or maybe I don't get it. EnableUnlimitedAmmo(1) is a command that can be used. Apparently, there's also a script being referenced that I cannot find among the Lua files. Either there's something going on or they (Ubi) simply didn't add it in the release build.

Any idea?
## Post #89
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-05T11:58:06+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

if you have names that are not in the database, just share them, i will add in collection
## Post #90
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-05T14:35:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> ^ Ooops, too late  Almost all Lua files now have their names corrected. It's just a matter or removing the LUAC container to decompile by LuaQ (0x51 = 5.1) header.

147E36A8A9F93A6D.lua
data_tmp\pc\_tmp\domino\user\gym_danydomino\activity\domino_actiovity_test.main.lua

799D43DB6DE696B5.lua
domino/user/gym_danydomino/activity/domino_actiovity_test.domino

These remain.

@Ekey: I noticed something interesting in Lua when looking for quirks I can use in a Lua console. There are file references to physical files that don't exist. Or maybe I don't get it. EnableUnlimitedAmmo(1) is a command that can be used. Apparently, there's also a script being referenced that I cannot find among the Lua files. Either there's something going on or they (Ubi) simply didn't add it in the release build.

Any idea?

From my knowledge of modding previous FCs, you either find lines like this "EnableUnlimitedAmmo(1)" in their system scripts or find them using a function hook (You probably won't get the parameters). Not all functions are referenced in system scripts.
## Post #91
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-05T15:15:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mlleemiles
>
> From my knowledge of modding previous FCs, you either find lines like this "EnableUnlimitedAmmo(1)" in their system scripts or find them using a function hook (You probably won't get the parameters). Not all functions are referenced in system scripts.
I used that as a reference. Am not trying to find Lua functions' parameters here, am trying to find out why referenced .lua scripts are missing  There is one script called "EnableUnlimitedAmmo_v2.lua" in some of the decompiled outputs.
## Post #92
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-05T15:26:03+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> mlleemiles wrote:From my knowledge of modding previous FCs, you either find lines like this "EnableUnlimitedAmmo(1)" in their system scripts or find them using a function hook (You probably won't get the parameters). Not all functions are referenced in system scripts.
I used that as a reference. Am not trying to find Lua functions' parameters here, am trying to find out why referenced .lua scripts are missing  There is one script called "EnableUnlimitedAmmo_v2.lua" in some of the decompiled outputs.

Can you post the Create box of the script you are talking about?
## Post #93
- Username: MysteriousJojo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 04, 2018 2:34 pm
- Post datetime: 2018-04-05T18:43:06+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> Updated here

* Disabled (:bfuscation
* Unknown files now are placed in individual folders:
Code: Select all__Unknown\BIK\
__Unknown\BNK\
__Unknown\FCB\
__Unknown\LUA\

and etc.

* Base of names updated. Removed unused names also added some new names.

This unpacker works only with .fat extension files,right? Because when i tried to unpack farcry5.dat the unpacker just crashed and said that  "the process cannot access the file because it is being used by another process".
## Post #94
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-05T21:52:55+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from MysteriousJojo
>
> This unpacker works only with .fat extension files,right? Because when i tried to unpack farcry5.dat the unpacker just crashed and said that  "the process cannot access the file because it is being used by another process".
You need choose FAT files, not DAT. FAT is File Allocation Table, DAT is package.
## Post #95
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-05T22:12:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Progress report:



Scenario 1 -- removing LUAC container and dumping clean script file (left, original; right, container removed):





Scenario 2 -- removing LUAC container, dumping script file and decompiling it (left, original; right, container removed -- left, container removed; right, decompiled):







Will post after some more testing.

Cheers,
Sun
## Post #96
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2018-04-06T00:09:24+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

The only fat file i can unpack is 

farcry5.fat
installpkg.fat
farcry_english.fat


I really want to unpack common.fat and patch.fat to get to the engine render settings
## Post #97
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-06T00:32:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

What the problem? I'm checked unpacker on all archives and works perfect.
## Post #98
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-06T01:37:12+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I’m interested in only the music files. Where would they be within the packages exactly?
## Post #99
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2018-04-06T02:26:02+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> What the problem? I'm checked unpacker on all archives and works perfect.

It for some reason wanted common.dat in "D:\common.dat" as opposed to the same dir as common.fat. same for patch
## Post #100
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-06T11:12:59+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

^ Carefully.. again.. carefully make sure what you type is what the tool expects
## Post #101
- Username: veav
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 10, 2018 9:50 pm
- Post datetime: 2018-04-06T11:51:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

sunbeam, any chance in hell this same approach can be made to work on the oasis string bin files?  It looks like someone had a way to decompress them for FC3 and FC4, but the dropbox they posted no longer exists.
## Post #102
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-06T16:35:48+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

No idea, might take a look.

Decided not to post the version I have now for the decompiler as it works with individual files being dragged over the GUI. I'll make it so it detects what you drag over, file or folder, so that it is then able to also process an entire folder of Lua files  There's like 4680 Lua files in farcry5.dat.
## Post #103
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-06T20:32:24+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

beautiful! good job! cant wait! ^
## Post #104
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2018-04-06T22:39:03+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> ^ Carefully.. again.. carefully make sure what you type is what the tool expects

it worked fine with farcry5.fat but for some reason the unpacker wants "common.dat" and "patch.dat" in "D:\" even tho the fat files are in the game directory with the unpacker files. They unpacked fine tho. Just weird.
## Post #105
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-07T08:25:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

It's not weird at all. Make sure you navigate to tool folder first and don't run it from wherever you are when you open CMD.
## Post #106
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-07T10:26:23+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from iambosh
>
> it worked fine with farcry5.fat but for some reason the unpacker wants "common.dat" and "patch.dat" in "D:\" even tho the fat files are in the game directory with the unpacker files. They unpacked fine tho. Just weird.
Path "D:\" is just example. Choose yours paths to these files.
## Post #107
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-04-07T11:02:31+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Example path for .bat:

```
FC5.Unpacker.exe C:\FC\Unpacked\shadersobj.fat C:\FC\Unpacked\shadersobj
pause
```
## Post #108
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-07T11:28:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

sent pm ^^
## Post #109
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-04-07T12:03:12+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

would someone be kind enough to grab me the "revelator" the big ass armored truck from John seeds map? I may not be able to do much with it but I'd still love to have for future work. Thanks for your time.
## Post #110
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-04-07T14:36:05+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hello guys, I'm trying to prolong the time for enemies being in wounded state (I would also like to give them more health, so they dont die with one shot when down in wounded state).
Can someone here point me in the right direction?
## Post #111
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-08T01:56:52+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Here's the cleaner/decompiler: [https://goo.gl/CZFS56](https://goo.gl/CZFS56). Just drag and drop either a single or multiple files over the GUI for the magix to happen (you will need JRE installed for the decompiler to work).

Also, here's the cleaned/decompiled Lua files from farcry5.dat: [https://goo.gl/gf9B7c](https://goo.gl/gf9B7c).

> Reply from mlleemiles
>
> Can you post the Create box of the script you are talking about?
So.. what I was saying is the following:

- open all .lua files in Notepad++
- search for UnlimitedAmmo_v2

Result: cboxRes:RegisterBox("Domino/System/Coop/AllPlayers/UnlimitedAmmo_v2.lua");

^ Well, that file is not available in the mentioned path.

Another example -> "cboxRes:RegisterBox("Domino/System/ConsoleCommand_v3.lua")". I cannot find that "ConsoleCommand_v3.lua" in the extracted files. Either Ubi didn't ship it or it's hidden in some way 

Ekey, any idea? If you force that path - domino\system\consolecommand_v3.lua - in the definitions file, would the extractor pick-up that 'missing' script? 

BR,
Sun

P.S.: Just checked FileNames.list. The entries are already in there, but the .lua scripts are not found/extracted 

line 35821: domino\system\consolecommand_v3.lua
line 35825: domino\system\coop\allplayers\unlimitedammo_v2.lua
## Post #112
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-08T07:38:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Example path for .bat:
Code: Select all@echo off
FC5.Unpacker.exe C:\FC\Unpacked\shadersobj.fat C:\FC\Unpacked\shadersobj
pause

sent you a pm ganic3000.
## Post #113
- Username: MysteriousJojo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 04, 2018 2:34 pm
- Post datetime: 2018-04-08T08:14:09+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I'm a little curious about DAT unpacker.I mean how it would look and when it will be available for downloading.Will it be like Disrupt extractor for WATCH_DOGS or CLI like FAT unpacker?
## Post #114
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-08T08:23:15+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from MysteriousJojo
>
> I'm a little curious about DAT unpacker.I mean how it would look and when it will be available for downloading.Will it be like Disrupt extractor for WATCH_DOGS or CLI like FAT unpacker?

It is available for download already, check the bottom of 6th page..
## Post #115
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-08T08:27:59+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> Here's the cleaner/decompiler: https://goo.gl/CZFS56. Just drag and drop either a single or multiple files over the GUI for the magix to happen (you will need JRE installed for the decompiler to work).

Also, here's the cleaned/decompiled Lua files from farcry5.dat: https://goo.gl/gf9B7c.
mlleemiles wrote:Can you post the Create box of the script you are talking about?
So.. what I was saying is the following:

- open all .lua files in Notepad++
- search for UnlimitedAmmo_v2

Result: cboxRes:RegisterBox("Domino/System/Coop/AllPlayers/UnlimitedAmmo_v2.lua");

^ Well, that file is not available in the mentioned path.

Another example -> "cboxRes:RegisterBox("Domino/System/ConsoleCommand_v3.lua")". I cannot find that "ConsoleCommand_v3.lua" in the extracted files. Either Ubi didn't ship it or it's hidden in some way 

Ekey, any idea? If you force that path - domino\system\consolecommand_v3.lua - in the definitions file, would the extractor pick-up that 'missing' script? 

BR,
Sun

P.S.: Just checked FileNames.list. The entries are already in there, but the .lua scripts are not found/extracted 

line 35821: domino\system\consolecommand_v3.lua
line 35825: domino\system\coop\allplayers\unlimitedammo_v2.lua

I happen to have these 2 extracted. See attached file.

Also, can you release a command line tool? Walking through each folder and dragging all the files aren't very fun to do 
[system.zip](https://xentaxbackup.github.io/file/14181_system.zip)
## Post #116
- Username: MysteriousJojo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 04, 2018 2:34 pm
- Post datetime: 2018-04-08T08:49:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mlleemiles
>
> MysteriousJojo wrote:I'm a little curious about DAT unpacker.I mean how it would look and when it will be available for downloading.Will it be like Disrupt extractor for WATCH_DOGS or CLI like FAT unpacker?

It is available for download already, check the bottom of 6th page..

It's not working with DAT extension.When i try to unpack FAT everything is OK but when it comes to DAT it just crashes and says "FC5.Unpacker stopped working."
## Post #117
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-08T09:19:26+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from MysteriousJojo
>
> mlleemiles wrote:MysteriousJojo wrote:I'm a little curious about DAT unpacker.I mean how it would look and when it will be available for downloading.Will it be like Disrupt extractor for WATCH_DOGS or CLI like FAT unpacker?

It is available for download already, check the bottom of 6th page..

It's not working with DAT extension.When i try to unpack FAT everything is OK but when it comes to DAT it just crashes and says "FC5.Unpacker stopped working."
Dude.. Have you been reading this thread at all?

> You need choose FAT files, not DAT. FAT is File Allocation Table, DAT is package.
FAT is a file index for DAT, to unpack DAT you need a FAT.
## Post #118
- Username: MysteriousJojo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 04, 2018 2:34 pm
- Post datetime: 2018-04-08T09:39:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Okay, it worked. I though that it will be work like Gibbed Dunia2 Tools but i was wrong.
## Post #119
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-08T20:13:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mlleemiles
>
> I happen to have these 2 extracted. See attached file.

Also, can you release a command line tool? Walking through each folder and dragging all the files aren't very fun to do
Yeah, I know. I've done the hard part myself  I'll see if I can tweak it to walk a root directory through sub-directories.

As far as the missing files: Ekey, why does the tool extract these for some people and not for everyone? A bug somewhere? Path size maybe?
## Post #120
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-08T23:09:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> As far as the missing files: Ekey, why does the tool extract these for some people and not for everyone? A bug somewhere? Path size maybe?
Because people do not read what i write, that's why they use it incorrectly
## Post #121
- Username: invasion101
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Oct 13, 2010 1:46 am
- Post datetime: 2018-04-09T00:47:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ganic3000 sent you a pm again!  and ekey your doing a great job love the program it works for me
## Post #122
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-09T20:10:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey
>
> sunbeam906 wrote:As far as the missing files: Ekey, why does the tool extract these for some people and not for everyone? A bug somewhere? Path size maybe?
Because people do not read what i write, that's why they use it incorrectly
No.. I mean.. I don't get some .lua files extracted, while for others, they are extracted. See the below links where I am explaining how I don't have 2 .lua files someone already said they have them O_O.

See these:

[viewtopic.php?p=139507#p139507](http://forum.xentax.com/viewtopic.php?p=139507#p139507)
[viewtopic.php?p=139519#p139519](http://forum.xentax.com/viewtopic.php?p=139519#p139519)

@mlleemiles: I don't know how you got those 2 extra .lua files, as I ran the extractor on another OS on farcry5.dat and I still don't get those files extracted. Maybe you used the previous version of the extractor? Or you 'borrowed' the files from FC4. Given I tested on 2 different computers the those LUA files aren't produced on extract, I can only think of that - you got them from FC4?

BR,
Sun
## Post #123
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-09T20:48:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

@mlleemiles: Can you please check if you have ALL of these extracted to disk? (see attached file) I've dumped a list from all the Lua files I could get their references in.

For example, here's what I could gather about Domino/System/Activity/:

```
"Domino/System/Activity/ActivityConvoyListener.lua"
"Domino/System/Activity/ActivityEnd.lua"
"Domino/System/Activity/ActivityEndGame.lua"
"Domino/System/Activity/ActivityInitialized.lua"
"Domino/System/Activity/ActivityMiscInfoModifier_v2.lua"
"Domino/System/Activity/ActivityNotifyStatus.lua"
"Domino/System/Activity/ActivityObjectiveMarkerModifier_v3.lua"
"Domino/System/Activity/ActivityObjectiveTimerListener.lua"
"Domino/System/Activity/ActivityObjectiveTimerModifier.lua"
"Domino/System/Activity/ActivityPhoneCallListener.lua"
"Domino/System/Activity/ActivityRetry.lua"
"Domino/System/Activity/ActivityStoppableWhenAcknowledgedModifier.lua"
"Domino/System/Activity/AddActivityObjectiveConvoyHealthBar.lua"
"Domino/System/Activity/AddActivityObjectiveEntityHealthBar.lua"
"Domino/System/Activity/AddActivityObjectiveProgress_v2.lua"
"Domino/System/Activity/AddActivityObjective_v2.lua"
"Domino/System/Activity/EndActivityObjective_v2.lua"
"Domino/System/Activity/GetActivityFact.lua"
"Domino/System/Activity/GetActivityState.lua"
"Domino/System/Activity/GetActivityState_v2.lua"
"Domino/System/Activity/SetActivityFact.lua"
"Domino/System/Activity/SetActivityObjectiveProgress_v2.lua"
```

And here's what Ekey's extractor managed to dump on my end:



Something tells me the extractor fails at some point and doesn't output any errors.

We can then move to other folders 

BR,
Sun
[all_system_refs.zip](https://xentaxbackup.github.io/file/14189_all_system_refs.zip)
## Post #124
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-09T23:11:32+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Never mind, there's a bunch of files I got from installpkg.fat/.dat  So it's all good
## Post #125
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-09T23:25:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> 
Because people do not read what i write, that's why they use it incorrectly  
No.. I mean.. I don't get some .lua files extracted, while for others, they are extracted. See the below links where I am explaining how I don't have 2 .lua files someone already said they have them O_O.

See these:

viewtopic.php?p=139507#p139507
viewtopic.php?p=139519#p139519
There is no such thing. If the file exists in the archive then it is extracted 100%. The files you are looking for are in another archive 

```
+ 682BF692CD41BABF Domino\System\Activity\ActivityConvoyListener.lua -> (installpkg.fat)
+ 8F7E4B7F4A6ECE06 Domino\System\Activity\ActivityEnd.lua -> (installpkg.fat)
+ 1444BD5B09A8C1EF Domino\System\Activity\ActivityEndGame.lua -> (farcry5.fat)
+ 4747227A3256ACAF Domino\System\Activity\ActivityInitialized.lua -> (installpkg.fat)
+ DDC7DB6CFCB14CC4 Domino\System\Activity\ActivityMiscInfoModifier_v2.lua -> (installpkg.fat)
+ 711B2D098EEBD44B Domino\System\Activity\ActivityNotifyStatus.lua -> (installpkg.fat)
+ ACA80A6D0396763B Domino\System\Activity\ActivityObjectiveMarkerModifier_v3.lua -> (installpkg.fat)
+ 2688109A1874F33C Domino\System\Activity\ActivityObjectiveTimerListener.lua -> (installpkg.fat)
+ 93B39C055D74F72E Domino\System\Activity\ActivityObjectiveTimerModifier.lua -> (installpkg.fat)
+ AFAC16A1B0C701B7 Domino\System\Activity\ActivityPhoneCallListener.lua -> (farcry5.fat)
+ 825855F607731161 Domino\System\Activity\ActivityRetry.lua -> (installpkg.fat)
+ 5A0DBBE5B1984FDD Domino\System\Activity\ActivityStoppableWhenAcknowledgedModifier.lua -> (farcry5.fat)
+ 018C7A7C5A14DD69 Domino\System\Activity\AddActivityObjectiveConvoyHealthBar.lua -> (farcry5.fat)
+ FD87C5D77A14C0C6 Domino\System\Activity\AddActivityObjectiveEntityHealthBar.lua -> (installpkg.fat)
+ 7075631CBDB279EB Domino\System\Activity\AddActivityObjectiveProgress_v2.lua -> (installpkg.fat)
+ BC08EF7BE5EEC20C Domino\System\Activity\AddActivityObjective_v2.lua -> (installpkg.fat)
+ BC024B91A1EEC20C Domino\System\Activity\EndActivityObjective_v2.lua -> (installpkg.fat)
+ C0F59F90DA23D8E5 Domino\System\Activity\GetActivityFact.lua -> (installpkg.fat)
+ 8F1C22C0938A20A4 Domino\System\Activity\GetActivityState.lua -> (farcry5.fat)
+ 8D20C96AE4276023 Domino\System\Activity\GetActivityState_v2.lua -> (installpkg.fat)
+ C0F5854A1A23D8E5 Domino\System\Activity\SetActivityFact.lua -> (installpkg.fat)
+ 6AC57AE193D279EB Domino\System\Activity\SetActivityObjectiveProgress_v2.lua -> (installpkg.fat)

```
## Post #126
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-10T03:14:46+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

^ Yeah, did figure it out on my own  Will pimp the decompiler to parkour dirs/subdirs of Lua files
## Post #127
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2018-04-10T03:22:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Can anybody tell me where the localization file and font are located where?
## Post #128
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-04-14T13:36:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I received many messages about the request to make the packer, but I unfortunately have no time now and I'm busy with my main job. I am not greedy and will share source's of unpacker, maybe someone make packer.

Have a nice day 
[FC5.Unpacker.Src.rar](https://xentaxbackup.github.io/file/14206_FC5.Unpacker.Src.rar)
## Post #129
- Username: sunbeam906
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 04, 2018 7:17 am
- Post datetime: 2018-04-15T14:41:24+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Similarly here, managed to finish the cleaner/extractor.

It makes use of some old source-code I had lying around + snippets from various places on the internet. The only thing I can say I'd take credit for is the time spent to combine these and apply my own logic to the process. Tool can now recursively scan a folder's root and sub-folders for ".lua" files and then feed them to the ProcessFile function.

I've managed to extract all Lua files (or so I think; let me know if I missed any other .dat archives).

- listing the archive names I've extracted data from, set as folder names here-in:



- if you drag and drop a single .lua file over the GUI, this happens:



- if I want the remnants gone (activityendgame.luadec, activityendgame.unluac) and activityendgame.clean renamed to activityendgame.lua, then tick the bottom checkbox:



- lastly, if you want the tool to recursively do the above for all .lua files found in a folder/sub-folder/sub-folder... then go up one level and drag over the entire folder; you can do this with the root as well (my root is FC5_Lua; so if I dragged that, all found .lua files would be processed; yes, it takes a while):







Credits:

1. Ekey for the ability to extract Far Cry 5 files from the .dats using .fats.

2. Hans Wessels for the unluac Java decompiler ([https://github.com/HansWessels/unluac](https://github.com/HansWessels/unluac))

3. Ovidiu Cucu for his last post in this thread: [https://stackoverflow.com/questions/456 ... d-findnext](https://stackoverflow.com/questions/45608205/recursively-find-files-with-a-certain-extension-using-findfirstfile-and-findnext)

BIG NOTE: You need Java RE installed for the decompiler to work! Don't say I didn't tell you so! (Link: [http://www.oracle.com/technetwork/java/ ... 33155.html](http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) - - at the time of the post, Java SE Runtime Environment 8u162)

Report any bugs and enjoy 
[FC5_Decompiler.zip](https://xentaxbackup.github.io/file/14216_FC5_Decompiler.zip)
## Post #130
- Username: SolidSnake916
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 02, 2011 4:49 pm
- Post datetime: 2018-04-16T16:21:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I been using the unpacker, but finding all the Music, and Radio Songs is proving very hard. Has anyone else found most of the Cult Music? As some are mixed a special way and not released on the OSTs. Also the background music when some of the Leaders are talking is really good. But i when i extracted the .Fat files i get alot of duplicates. i was converting the .wem to .ogg and testing them out, alot of the .bnk dont extract. Wondering if im using prehistoric tools lol. Someone who is an audio wiz please help
## Post #131
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2018-04-16T19:02:11+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Thank you all for working on it!
Now we can remove all things that are so bad and annoying.
## Post #132
- Username: BigTinz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 16, 2018 5:53 pm
- Post datetime: 2018-04-17T19:24:21+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

How are people accessing unreleased guns like the beretta? 

I was under the impression there was no functional repacker for these files. I used Gibbed's Primal Dunia tools and the repack didn't work...
## Post #133
- Username: classlion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 30, 2018 1:06 am
- Post datetime: 2018-04-18T20:18:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hay, guys! Maybe i can halp you.
Use oggdecV1.9.7 like in Far Cry 4 and Watch Dods.

Maybe its sbao format. Plaese, say to me, if it be succesfull.
[oggdecV1.9.7.zip](https://xentaxbackup.github.io/file/14236_oggdecV1.9.7.zip)
## Post #134
- Username: classlion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 30, 2018 1:06 am
- Post datetime: 2018-04-18T20:22:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

As always most of the good stuff is hidden in the gamefiles. Extraction is pretty straight forward, the only downside is the mass of files to dig through. All you need are dunia2 and "oggdecV1.9.7" 

Then locate your "sound.dat" and "sound.fat" in the "data_win32" folder your Farcry 4 folder, copy them both into the dunia tools folder and just drag/drop "sound.dat" on the "Gibbed.Dunia2.Unpack.exe". Extraction takes a while so don't close the window, it will dissapear when it's done. Some files are recognized as "wav", some files are "unknown", but you can still decode them with oggdec. However there are lots of empty files in between the unknown files.

Please, say to me about result.
## Post #135
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2018-04-18T20:35:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from sunbeam906
>
> Similarly here, managed to finish the cleaner/extractor.
Great job Sun, as always 

Keeps crashing here. (Trying dragging single file: \common.dat\domino\system\coop\lualibraries\lualibcoop.lua)
Could you link me the source code in a PM so I could debug?
Thanks!
## Post #136
- Username: Dead Sirious
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 20, 2018 12:50 am
- Post datetime: 2018-04-19T18:00:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I need your help to extract Boomer's model and textures. I can port the model to games like Fallout 4 / New Vegas / Fallout 3 to replace Dogmeat after and share for free use
## Post #137
- Username: Staedtler
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 11:45 pm
- Post datetime: 2018-04-19T18:28:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

So how do I open them? I tried 'Gibbed.Dunia2.Unpack.exe', but it didn't seem to work. Any help, please?
## Post #138
- Username: Staedtler
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 11:45 pm
- Post datetime: 2018-04-19T18:55:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> TrumpetPro wrote:FC5 just came out, but it seems to use a different version of the fat and dat format than Watch Dogs (the only (kind of) Dunia Engine game I've modded). I was hoping somebody would be up to reverse engineering them, as I have no clue how (-:

Thanks,
TrumpetPro

I recently dig through the archives and found some information from the new header format of models and file names that are packed into the .dat archive.
  The .xbg header is HSEMG, but unfortunately the importers of the previous headlight parts can not import the .xbg file.
https://drive.google.com/open?id=1WIM6g ... fDc4ZixxpY Here is a model from FC5, got from igepack.dat
From one archive it is possible to extract a picture of the map editor by hex by hex, so far everything has been able to find out about this.
Sorry for my clumsy English =)

So how do I open this .dat?
## Post #139
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-04-19T20:21:32+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Staedtler
>
> Ganic3000 wrote:TrumpetPro wrote:FC5 just came out, but it seems to use a different version of the fat and dat format than Watch Dogs (the only (kind of) Dunia Engine game I've modded). I was hoping somebody would be up to reverse engineering them, as I have no clue how (-:

Thanks,
TrumpetPro

I recently dig through the archives and found some information from the new header format of models and file names that are packed into the .dat archive.
  The .xbg header is HSEMG, but unfortunately the importers of the previous headlight parts can not import the .xbg file.
https://drive.google.com/open?id=1WIM6g ... fDc4ZixxpY Here is a model from FC5, got from igepack.dat
From one archive it is possible to extract a picture of the map editor by hex by hex, so far everything has been able to find out about this.
Sorry for my clumsy English =)

So how do I open this .dat?

Updated [here](http://forum.xentax.com/viewtopic.php?p=139382#p139382)

```

    m_FATFile - Source of FAT file
    m_Directory - Destination directory

[Examples]
    FC5.Unpacker D:\FC5\data_final\pc\common.fat D:\Unpacked\common
```
## Post #140
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2018-04-19T22:22:12+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Has anyone found the main game script files? Wanting to remove the whole marked/hunted. SO i can roam around freely.
## Post #141
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-04-20T05:24:09+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Csimbi
>
> sunbeam906 wrote:Similarly here, managed to finish the cleaner/extractor.
Great job Sun, as always 

Keeps crashing here. (Trying dragging single file: \common.dat\domino\system\coop\lualibraries\lualibcoop.lua)
Could you link me the source code in a PM so I could debug?
Thanks!

Remove the LUAC header + file size bytes (first 8 bytes) in binary and use unluac.
## Post #142
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2018-04-20T06:48:26+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

@mlleemiles
Thanks! I thought Sun taken care of such.
## Post #143
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-04-20T17:04:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Dead Sirious
>
> I need your help to extract Boomer's model and textures. I can port the model to games like Fallout 4 / New Vegas / Fallout 3 to replace Dogmeat after and share for free use
You can grab it here. I ripped him with NR but textures are proper converted DX10 DDS. NR does textures too dark.

```
https://forum.facepunch.com/f/fbx/bsmor/Far-Cry-5-and-4-technically-Models/3/#postcvdudz
```
## Post #144
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-04-20T18:33:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Dead Sirious
>
> I need your help to extract Boomer's model and textures. I can port the model to games like Fallout 4 / New Vegas / Fallout 3 to replace Dogmeat after and share for free use

can you also port models into games like gta 5?
## Post #145
- Username: mwesten1
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jul 09, 2016 3:27 am
- Post datetime: 2018-04-20T22:44:00+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Did anyone tried to rip far cry 5 character model that resembles the main character from movie "Drive"?

[
[maxresdefault (1).jpg](https://xentaxbackup.github.io/file/14247_maxresdefault (1).jpg)
## Post #146
- Username: BigTinz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 16, 2018 5:53 pm
- Post datetime: 2018-04-21T03:24:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

So, how many functional tools do we have right now?

The unpacker works great, but I haven't found a way to convert .fcb.ark back from xml after editing and any patch.dat/fat is MASSIVE when repacked with Gibbed's Primal tools.
## Post #147
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-04-21T20:34:31+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from BigTinz
>
> So, how many functional tools do we have right now?

The unpacker works great, but I haven't found a way to convert .fcb.ark back from xml after editing and any patch.dat/fat is MASSIVE when repacked with Gibbed's Primal tools.

The list in the file does not match the list in the archive FC5.
## Post #148
- Username: Cassilias
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 22, 2018 7:05 am
- Post datetime: 2018-04-22T13:50:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Can someone please help me with extracting the audio files?

I've used FC5DatUnpacker to extract farcry5.dat and from what i know the sound are in soundbinary folder and some in __unknown folder (because there are .bnk files there too?)
I tried to convert the .wem and .bnk from soundbinary folder with various converters from web but no go. ww2ogg gives an error about missing RIFFs, and all the .bnk extractors i tried seem to do nothing.
I am a total noob at sound ripping so any help is appreciated.

- SOLVED !!!
## Post #149
- Username: exygen12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 18, 2017 12:42 am
- Post datetime: 2018-04-22T15:58:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Can anybody do something about oasisstrings? Old tools not working. Thanks.

Here is the file:
[Download Here](https://drive.google.com/uc?export=download&id=1TqkonGZIHfsErDUnOnyln_mrA2Hy_n0x)
## Post #150
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-04-25T06:50:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Alright guys so how can i compile and decompile game lua files, i need to edit some of them!? Thank you!
## Post #151
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2018-04-25T20:22:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Maximmum
>
> Alright guys so how can i compile and decompile game lua files, i need to edit some of them!? Thank you!
Would also appreciate a mini guide for this too. =)
## Post #152
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-05-02T10:47:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Is there a way to do model swap? And how can i do it? For e.x. i want to replace my female player character's head with Faith's head, how can i do that
## Post #153
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-02T12:16:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Maximmum
>
> Is there a way to do model swap? And how can i do it? For e.x. i want to replace my female player character's head with Faith's head, how can i do that

At the moment it can not be done, the properties of the models are different.
## Post #154
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-05-02T21:26:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

why is it taking long for people to release models, is there not the right tools out yet or is the game genuinely hard to rip from?
?
## Post #155
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-05-03T05:31:36+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hey guys,

would it be possible to update the current state of possible modding in the opening post?
I am continuously reading this thread and waiting for the moment when I can finally modify some config files (damage multiplier for body parts, etc.), but I have totally lost track of how far you guys are.
I read that you can already extract the files from the archives, but can you repack them, so we can actually modify the game?

BR
tschiesas
## Post #156
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-03T08:19:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from tschiesas
>
> Hey guys,

would it be possible to update the current state of possible modding in the opening post?
I am continuously reading this thread and waiting for the moment when I can finally modify some config files (damage multiplier for body parts, etc.), but I have totally lost track of how far you guys are.
I read that you can already extract the files from the archives, but can you repack them, so we can actually modify the game?

BR
tschiesas

You can repackage the from the old version FC, only the game will not have such readings in the archive, the structure of the code is different.(
## Post #157
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-05-03T14:35:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> tschiesas wrote:Hey guys,

would it be possible to update the current state of possible modding in the opening post?
I am continuously reading this thread and waiting for the moment when I can finally modify some config files (damage multiplier for body parts, etc.), but I have totally lost track of how far you guys are.
I read that you can already extract the files from the archives, but can you repack them, so we can actually modify the game?

BR
tschiesas

You can repackage the from the old version FC, only the game will not have such readings in the archive, the structure of the code is different.(
So what you are saying is that I need to wait until the structure of the code is known to properly begin modding.
I get that, thats why I suggested putting the current status of events into the opening post
## Post #158
- Username: BigTinz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 16, 2018 5:53 pm
- Post datetime: 2018-05-04T21:54:28+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I agree. I think that would be nice.

I have a bad feeling that nothing is going to change any time soon. Gibbed is silent on updating his tools, and it already seems kind of dead here...
## Post #159
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-05-04T23:51:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from BigTinz
>
> I agree. I think that would be nice.

I have a bad feeling that nothing is going to change any time soon. Gibbed is silent on updating his tools, and it already seems kind of dead here...

yeah i dont think people give a shit about ripping models from this game, if so, would of been done already by now, bet
## Post #160
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-05-06T09:05:35+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from connorukboy
>
> BigTinz wrote:I agree. I think that would be nice.

I have a bad feeling that nothing is going to change any time soon. Gibbed is silent on updating his tools, and it already seems kind of dead here...

yeah i dont think people give a shit about ripping models from this game, if so, would of been done already by now, bet

Our only chance of ripping models is Ninja Ripper, but it doesn't rip the Rig(skeleton) sadly
## Post #161
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-05-06T12:53:06+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I dont really care about ripping models, I would like to modify body part damage, etc. in the configs (like in FC2).
## Post #162
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-06T17:08:51+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Maximmum
>
> connorukboy wrote:BigTinz wrote:I agree. I think that would be nice.

I have a bad feeling that nothing is going to change any time soon. Gibbed is silent on updating his tools, and it already seems kind of dead here...

yeah i dont think people give a shit about ripping models from this game, if so, would of been done already by now, bet

Our only chance of ripping models is Ninja Ripper, but it doesn't rip the Rig(skeleton) sadly

All that I could get instead of the model, it's just a skeleton.
[unUbt1MO26o.jpg](https://xentaxbackup.github.io/file/14329_unUbt1MO26o.jpg)
## Post #163
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-06T17:11:24+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Car skeleton FC5.
[CCrJmIwUbI8.jpg](https://xentaxbackup.github.io/file/14330_CCrJmIwUbI8.jpg)
## Post #164
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-05-06T17:32:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

i was very surprised when i heard people using ninja ripper to get models from this game, i used it but the model is so fucked, takes a lot of time to fix and get it looking decent. some people are going ahead with actually fixing uv maps and all that but taking long to post which is fine, but tbh this game has quickly lost peoples interests lol
## Post #165
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-05-07T07:47:14+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> connorukboy wrote:BigTinz wrote:I agree. I think that would be nice.

I have a bad feeling that nothing is going to change any time soon. Gibbed is silent on updating his tools, and it already seems kind of dead here...

yeah i dont think people give a shit about ripping models from this game, if so, would of been done already by now, bet

Our only chance of ripping models is Ninja Ripper, but it doesn't rip the Rig(skeleton) sadly

All that I could get instead of the model, it's just a skeleton.[/quote]


How did you exported the skeleton? What were you using?
## Post #166
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-07T08:23:41+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Maximmum
>
> Ganic3000 wrote:

All that I could get instead of the model, it's just a skeleton.

How did you exported the skeleton? What were you using?
Blender 2.70 import xbg primal.
## Post #167
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-05-07T16:59:26+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> Maximmum wrote:Ganic3000 wrote:

All that I could get instead of the model, it's just a skeleton.

How did you exported the skeleton? What were you using?
Blender 2.70 import xbg primal.
Ok, thx, gonna try and see if it'll import Faith's skeleton)
## Post #168
- Username: danielkarloskar1
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Aug 13, 2016 6:10 am
- Post datetime: 2018-05-07T21:04:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from tschiesas
>
> I dont really care about ripping models, I would like to modify body part damage, etc. in the configs (like in FC2).
Same. Wanted to find the hunted/marked part and disable it. No luck in scripts files so far.
## Post #169
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-05-10T17:21:05+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Updated FileNames.list from game files. Basically I joined all unpacked files into the one file and dumped all strings from it.
So some of filenames can be dummy.
Updated Program.cs file with more file extensions unpacked in the __Unknown folder.
Added compiled version of updated unpacker.

```
https://files.fm/u/ajehb9vg
```

All thanks goes to ekey!
## Post #170
- Username: Maximmum
- Rank: advanced
- Number of posts: 60
- Joined date: Wed May 04, 2016 10:06 pm
- Post datetime: 2018-05-11T11:15:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from GRiNDERKILLER
>
> Updated FileNames.list from game files. Basically I joined all unpacked files into the one file and dumped all strings from it.
So some of filenames can be dummy.
Updated Program.cs file with more file extensions unpacked in the __Unknown folder.
Added compiled version of updated unpacker.
Code: Select allhttps://files.fm/u/ajehb9vg
All thanks goes to ekey!
I wonder when are we gonna get a Repacker? Cuz' to be able to Unpack only is not that great!
## Post #171
- Username: classlion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 30, 2018 1:06 am
- Post datetime: 2018-05-14T17:51:36+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from GRiNDERKILLER
>
> Updated FileNames.list from game files. Basically I joined all unpacked files into the one file and dumped all strings from it.
So some of filenames can be dummy.
Updated Program.cs file with more file extensions unpacked in the __Unknown folder.
Added compiled version of updated unpacker.
Code: Select allhttps://files.fm/u/ajehb9vg
All thanks goes to ekey!

Somebody, help me run this program. I never run this type of program. Maybe someone have guide or explaine me, please!
## Post #172
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2018-05-14T20:34:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from classlion
>
> GRiNDERKILLER wrote:Updated FileNames.list from game files. Basically I joined all unpacked files into the one file and dumped all strings from it.
So some of filenames can be dummy.
Updated Program.cs file with more file extensions unpacked in the __Unknown folder.
Added compiled version of updated unpacker.
Code: Select allhttps://files.fm/u/ajehb9vg
All thanks goes to ekey!

Somebody, help me run this program. I never run this type of program. Maybe someone have guide or explaine me, please!

guide video:
[https://www.youtube.com/watch?v=5Mc8U4PZ5Yk](https://www.youtube.com/watch?v=5Mc8U4PZ5Yk)
## Post #173
- Username: classlion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Mar 30, 2018 1:06 am
- Post datetime: 2018-05-15T16:49:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000
>
> classlion wrote:GRiNDERKILLER wrote:Updated FileNames.list from game files. Basically I joined all unpacked files into the one file and dumped all strings from it.
So some of filenames can be dummy.
Updated Program.cs file with more file extensions unpacked in the __Unknown folder.
Added compiled version of updated unpacker.
Code: Select allhttps://files.fm/u/ajehb9vg
All thanks goes to ekey!

Somebody, help me run this program. I never run this type of program. Maybe someone have guide or explaine me, please!

guide video:
https://www.youtube.com/watch?v=5Mc8U4PZ5Yk

Благодарю. Thank You!
## Post #174
- Username: mrwhalerus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 20, 2018 3:42 am
- Post datetime: 2018-05-19T19:43:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Unhandled Exception: System.IO.IOException: The process cannot access the file 'D:\SteamLibrary\steamapps\common\FarCry5\data_final\pc\common.dat' because it is being used by another process.
   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at FC5.Unpacker.Program.iUnpackFile(String m_FatFile, String m_DstFolder)
   at FC5.Unpacker.Program.Main(String[] args)
It checked and no processes have an handle
## Post #175
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-06-05T11:03:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I was searching for injured behavior and one file gave a clue to a file in a folder path which does not fully exist in the current unpacked version (I suppose it is in the _UNKNOWN folder).
Are there going to be any updates for the unpacker? ...and maybe a repacker?
Some guy on the far cry 5 nexus already created a mod editing the .fat file: [https://www.nexusmods.com/farcry5/mods/23](https://www.nexusmods.com/farcry5/mods/23)
Maybe he can help?
## Post #176
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-06-05T13:15:05+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Could anyone provide character's .xbg model samples from Far Cry 5? Thanks!
## Post #177
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-06-05T16:17:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mrwhalerus
>
> Unhandled Exception: System.IO.IOException: The process cannot access the file 'D:\SteamLibrary\steamapps\common\FarCry5\data_final\pc\common.dat' because it is being used by another process.
   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at FC5.Unpacker.Program.iUnpackFile(String m_FatFile, String m_DstFolder)
   at FC5.Unpacker.Program.Main(String[] args)
It checked and no processes have an handle
You can not extract the files while the game is running.
## Post #178
- Username: Alexxxxxxx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 02, 2017 6:44 am
- Post datetime: 2018-06-20T03:39:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hello! Who can update the unpacker for the version of the game 1.07
I used the unpacker version 0.4.35444 for unpacking patch.fat/dat  
Here's what in the end

```
Unhandled Exception: System.UnauthorizedAccessException: Access is denied along the way "D:\Ubisoft\UbisoftGameLauncher\games\Far Cry 5\data_final\pc\patch.fat".
   в System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   в System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, In
t32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions op
tions, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean
 useLongPath, Boolean checkHost)
   в System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, F
ileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean b
FromProxy)
   в System.IO.FileStream..ctor(String path, FileMode mode)
   в FC5.Unpacker.Program.iUnpackBigFile(String m_FatFile, String m_DstFolder)
```
## Post #179
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-25T21:51:18+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Alexxxxxxx
>
> Hello! Who can update the unpacker for the version of the game 1.07
I used the unpacker version 0.4.35444 for unpacking patch.fat/dat  
Here's what in the end
Code: Select allProject File Loaded: 1571221
Unhandled Exception: System.UnauthorizedAccessException: Access is denied along the way "D:\Ubisoft\UbisoftGameLauncher\games\Far Cry 5\data_final\pc\patch.fat".
   в System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   в System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, In
t32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions op
tions, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean
 useLongPath, Boolean checkHost)
   в System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, F
ileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean b
FromProxy)
   в System.IO.FileStream..ctor(String path, FileMode mode)
   в FC5.Unpacker.Program.iUnpackBigFile(String m_FatFile, String m_DstFolder)

I literally just used the same version on 1.07 yesterday, worked 100% fine.

BTW since nobody has done a model importer, I started working on one for blender, similar to what I did for Primal etc.  Should have something in a couple days.
## Post #180
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-27T05:02:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Little bit of progress. I can load some static meshes, with UVs.  They really messed with the format as compared to FarCry4/Primal, the block structure is relatively similar, but they removed some blocks and added some new ones, and they changed how sub-meshes/sub-materials are stored, and changed how they handle the vertex block, which is frankly a nightmare. I want to do it nice, but I may end up taking the easy way out and just make every material a separate mesh (so like, things will be a ton of parts). But have to see what can be done.

As for Rigging, I haven't even looked at those types of meshes yet, so At this point, It's wait and see as to whether I can import weights and bones. Will report back in a few days.
## Post #181
- Username: Alexxxxxxx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 02, 2017 6:44 am
- Post datetime: 2018-06-27T11:43:34+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
>  I literally just used the same version on 1.07 yesterday, worked 100% fine.
Sorry. I already figured out what was the problem
I now have another problem. I unpacked the files (patch.dat/fat), made changes for the editor and packed. And in the end, it is launched once, and the second is no longer. Although on the old version these changes worked
Tell me please what kind of packaging program do you use?
## Post #182
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-27T15:52:58+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Alexxxxxxx
>
> volfin wrote: I literally just used the same version on 1.07 yesterday, worked 100% fine.
Sorry. I already figured out what was the problem
I now have another problem. I unpacked the files (patch.dat/fat), made changes for the editor and packed. And in the end, it is launched once, and the second is no longer. Although on the old version these changes worked
Tell me please what kind of packaging program do you use?

I haven't tried repacking anything. I just unpacked it to work on a model importer. when I was catching up on the thread (yes all 12 pages) I was pretty sure the consensus was repacking wasn't possible.
## Post #183
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-27T22:33:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Small update, it does look like the skeleton portion didn't change at all, which I figured since some in the thread mentioned they got the skeleton with the primal importer. This makes me more hopeful that full rigging will be possible, I just need to figure out how weights are stored, hopefully that didn't change much either.  

I am seeing something odd I don't quite understand yet:



I may have to recheck my code, it only seems to happen for the first triangle on a new run.
## Post #184
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-06-29T04:56:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Another update. I think I have multiple materials sorted out and applying correctly, as well as multi-mesh import. I have also found the weights and indices for rigged meshes, the only thing I have left is to get those plugged into the right meshes in the right order (this new mess they made is making all of this rather difficult).  But overall things are proceeding well. I can also parse the materials files and auto-convert the textures associated with each mesh. 

However, Unlike Primal, I can't have blender load them, because they are DX10 format DDS files, which Blender does not support. So likely I'll write the converted textures to the same folder as the model, so you can find them easily and do your own manipulation/conversion on them.

You probably won't see me post again until it's actually done.

P.S. I also sorted out that stray triangle issue.
## Post #185
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-01T22:57:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ok, so V1.0 of the importer is released. But there's a lot of issues still, which I will go over. However, it will import about 80% of things, and I've hit a wall so I figure I will release it at this stage.

The importer is for Blender 2.70 and above, and if you need to know how to install, see my previous tutorial here: 
[viewtopic.php?p=103131#p103131](http://forum.xentax.com/viewtopic.php?p=103131#p103131)

What the importer can do:
 - Import all static meshes.
 - Import all rigged meshes.
 - Import Weapons.
 - Import some car accessories.

What the importer can't do:
 - Import base vehicles (explained below)
 - Import full characters (explained below)
 - Import full maps (don't even ask about this)


First Off: you need to unpack all the data, it's scattered around. So this means unpacking the following FAT/DAT files into the *same* directory:
common.fat
worlds/installpkg.fat
worlds/farcry5.fat
patch.fat

You need to do it in this order so the patch overwrites the base data. I can't tell you what you'll get if you do it in some other order, probably old/out ofdate files.

Then it's simply a matter of loading an XBG and profit.

I know most want the characters, so I'll show you a little about that:

Far Cry 5 uses a 'parts' based system, so there's no real characters, everything is made up of a collection of generic reusable parts, and unique characters just have their own set of unique parts called a 'suit'.  which is applied to a generic body.

So for "Faith" for instance, her 'suit' is here:  "\graphics\_common\characters\fc5\wardrobe\suit\suit_avatar_faith_aver_f.xbg"

It looks like this:



As you see the body and head are missing, and this is why I say "can't import full characters." because those are one of the generic parts, with a body/face morph applied (Body: graphics\_common\characters\fc5\wardrobe\body\_items\lieu\body_lieu003_faith_5f4_aver_f.item.bwsk")  (Face: graphics\_common\characters\fc5\wardrobe\head\_facebuilder\head_lieu003_faith_aver_f.dpdx")

I have no way of doing this, writing a whole mesh morph system is way outside the realm of an importer. Maybe someone else can do this.

You can import the generic bodies/ Heads but they will not fit the clothes correctly because of the lack of morphing.


Now, about vehicles. Why can't they be imported?  Well they probably can, EXCEPT for the fact their vertex storage format is a mystery.  There is a Two Byte flag that determines the format of the Vertex Block bit 2 set = normal vertex storage for nearly 80% of everything. This is what everything uses.  but bit 2 is NOT set for vehicles, instead bit 32768 is set. And that told me something changed. And sure enough, the data won't decode in any way I tried, Not floats, not half floats, not integers divided by a factor.  Not even UVs will decode.  You can try importing a vehicle, and it will complete successfully, but this is what you'll see:



So I know i have the vertex block right, and the stride right, and I know the vertex data is still X,Y,Z,W and each is 2 bytes like the normal data, but it's not decodable by any method *I* know. So if anyone can figure out how it's stored, I can add support. But I've hit the wall on figuring it out. 

 An example file is graphics\vehicles\land\heavy\veh_heavy_truck\veh_heavy_truck.xbg  
I can tell you the simplest block of vertex data in that file starts at 0x13BB0, is 0x146 blocks long, and each block is 16 bytes long.  

Each block is:
short x;
short y;
short z;
short w;
short uv1-u;
short uv1-v;
byte color-r;
byte color-g;
byte color-b;
byte color-a;

However, i just can't decode it.

Vehicle accessories, such as truck beds and tanks (like \graphics\vehicles\land\heavy\veh_heavy_truck\att_heavy_truck_tanker_fuel_tank.xbg ) are stored normally and decode fine:



(while on this subject, they often combine repaired and damaged parts as one mesh, you just select by material to separate, like the last two materials here.

Oh and finally about textures.  The importer will try to find the Xbt files and convert them to DDS asd save them in the same directory as the original XBG.  but it's imperfect, and Like Primal/4 these XBT files are not the top MIP, they are small (usually 256 x 256).  So you'll need to find the large MIP by using a dedicated texture converter, nothing new about that. But just a reminder.

Also the Normal maps are saved in a funky channel order:



You should paste the red channel into a file and use it as specular/AO (I'm not positive but I think it's specular/metallic), and move the Alpha channel to the red channel to make it a 'regular' normal map.  (and as mentioned before they are using DX10 format for the DDS files, so use an appropriate converter.

So without further ado, here you go. As always if you find problems (outside the limitations mentioned here), let me know and preferably with the name of a file as an example of the problem.

Enjoy.

Edit: latest here: [viewtopic.php?p=141959#p141959](http://forum.xentax.com/viewtopic.php?p=141959#p141959)
## Post #186
- Username: Knmpm111
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 27, 2018 1:21 am
- Post datetime: 2018-07-02T09:51:52+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> 
Far Cry 5 uses a 'parts' based system, so there's no real characters, everything is made up of a collection of generic reusable parts, and unique characters just have their own set of unique parts called a 'suit'.  which is applied to a generic body.

So for "Faith" for instance, her 'suit' is here:  "\graphics\_common\characters\fc5\wardrobe\suit\suit_avatar_faith_aver_f.xbg"

As you see the body and head are missing, and this is why I say "can't import full characters." because those are one of the generic parts, with a body/face morph applied (Body: graphics\_common\characters\fc5\wardrobe\body\_items\lieu\body_lieu003_faith_5f4_aver_f.item.bwsk")  (Face: graphics\_common\characters\fc5\wardrobe\head\_facebuilder\head_lieu003_faith_aver_f.dpdx")

You can import the generic bodies/ Heads but they will not fit the clothes correctly because of the lack of morphing.
So it's not that big deal - just need to fit generic parts (suit and head) to generic body of the character and then join selected meshes. Am I right?
## Post #187
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-02T16:35:41+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Knmpm111
>
> volfin wrote:
Far Cry 5 uses a 'parts' based system, so there's no real characters, everything is made up of a collection of generic reusable parts, and unique characters just have their own set of unique parts called a 'suit'.  which is applied to a generic body.

So for "Faith" for instance, her 'suit' is here:  "\graphics\_common\characters\fc5\wardrobe\suit\suit_avatar_faith_aver_f.xbg"

As you see the body and head are missing, and this is why I say "can't import full characters." because those are one of the generic parts, with a body/face morph applied (Body: graphics\_common\characters\fc5\wardrobe\body\_items\lieu\body_lieu003_faith_5f4_aver_f.item.bwsk")  (Face: graphics\_common\characters\fc5\wardrobe\head\_facebuilder\head_lieu003_faith_aver_f.dpdx")

You can import the generic bodies/ Heads but they will not fit the clothes correctly because of the lack of morphing.

So it's not that big deal - just need to fit generic parts (suit and head) to generic body of the character and then join selected meshes. Am I right?

as far as I can tell.
## Post #188
- Username: Eda61
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 08, 2017 4:05 pm
- Post datetime: 2018-07-02T18:01:56+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I could not import any models using "io_scene_FarCry5."

I tried to do what you showed us. I imported this file. ( "Faith" for instance, her 'suit' is here: "\graphics\_common\characters\fc5\wardrobe\suit\suit_avatar_faith_aver_f.xbg") but it does not look like what you show  (I use Blender 2.79 and tried it in version 2.66)


> Reply from volfin
>
> So for "Faith" for instance, her 'suit' is here:  "\graphics\_common\characters\fc5\wardrobe\suit\suit_avatar_faith_aver_f.xbg"

It looks like this:

did not import the other models you showed. I always face an error.  What is the problem?
[Suit hatası.jpg](https://xentaxbackup.github.io/file/14541_Suit hatası.jpg)
## Post #189
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-02T20:34:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

oops, my fault, I left in some debug stuff that only works on my PC.    Here's a fixed version.

Edit: latest here: [viewtopic.php?p=141959#p141959](http://forum.xentax.com/viewtopic.php?p=141959#p141959)
## Post #190
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-03T07:18:49+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
>  - Import full maps (don't even ask about this)
I did test exports of "the crew" maps, and i think far cry must be very close, if not identical to it, so its very possible. However I dont see why anybody may need maps for such game.
## Post #191
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-03T18:38:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from daemon1
>
> volfin wrote: - Import full maps (don't even ask about this)
I did test exports of "the crew" maps, and i think far cry must be very close, if not identical to it, so its very possible. However I dont see why anybody may need maps for such game.

yes I just put that as a half joke, because someone always asks for this and I always tell them I'm not going to do it because it's too much work. So figured i'd try to head them off before they asked. Anyone else is more than welcome to go for it.
## Post #192
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-07-04T15:16:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I tried different versions of the unpacker, different FileNames.list.
i use FC5.Unpacker v0.0.4.35444, FileNames.list - 77mb (contains the names SUITS)
but when unpacking complite "graphics\_common\characters\fc5\wardrobe\suit\" is empty, not one file .xbg
## Post #193
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-04T17:41:53+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Crazy31139
>
> I tried different versions of the unpacker, different FileNames.list.
i use FC5.Unpacker v0.0.4.35444, FileNames.list - 77mb (contains the names SUITS)
but when unpacking complite "graphics\_common\characters\fc5\wardrobe\suit\" is empty, not one file .xbg

That's the unpacker i used, actually. read the original post i made when i released the importer. It explains how you have to combine *all 4* unpacks. because certain files are only in certain Fat/Dat.
## Post #194
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-07-05T09:24:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

You probably just have some mistake in your code. All vehicle geometry i checked are fully correct shorts. I even specifically checked this one:

> Reply from volfin
>
> graphics\vehicles\land\heavy\veh_heavy_truck\veh_heavy_truck.xbg  
.... starts at 0x13BB0, is 0x146 blocks long, and each block is 16 bytes long.

Here it is:
## Post #195
- Username: aaaabccccsdcsd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 05, 2018 7:36 pm
- Post datetime: 2018-07-05T12:00:13+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hi guys. I read all topic and in last posts you mention FC5 Unpacker version 0.0.4.35444, but I saw for download only 0.0.3.3658 version, so where to get the newer one? Thanks.
## Post #196
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-05T16:14:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from daemon1
>
> You probably just have some mistake in your code. All vehicle geometry i checked are fully correct shorts. I even specifically checked this one:
volfin wrote:graphics\vehicles\land\heavy\veh_heavy_truck\veh_heavy_truck.xbg  
.... starts at 0x13BB0, is 0x146 blocks long, and each block is 16 bytes long.  


Here it is:

Can you give more details about how you converted the shorts to floats? Because all the ways I tried didn't work.
## Post #197
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-05T16:17:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from aaaabccccsdcsd
>
> Hi guys. I read all topic and in last posts you mention FC5 Unpacker version 0.0.4.35444, but I saw for download only 0.0.3.3658 version, so where to get the newer one? Thanks.

Is this post on page 12:

[viewtopic.php?p=140443#p140443](http://forum.xentax.com/viewtopic.php?p=140443#p140443)
## Post #198
- Username: aaaabccccsdcsd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 05, 2018 7:36 pm
- Post datetime: 2018-07-05T17:23:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> aaaabccccsdcsd wrote:Hi guys. I read all topic and in last posts you mention FC5 Unpacker version 0.0.4.35444, but I saw for download only 0.0.3.3658 version, so where to get the newer one? Thanks.

Is this post on page 12:

viewtopic.php?p=140443#p140443

Thanks!
## Post #199
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-07-05T20:40:38+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I saw somebody ask about repacking .fat and .day files. Make sure you're on the Discord, it's been common knowledge you can use the FC Primal tools to repack there for a long while.

[https://discord.gg/XgBpEkS](https://discord.gg/XgBpEkS)
## Post #200
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-06T03:15:37+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ok, here's the latest version.  Support finally fixed for vehicles. Thanks to Daemon1 for helping me to see what was wrong.







Note that even though these have skeletons, they don't seem to have any weighting i can find in these files. Also even though they are split up into many materials, the exploded/pristine versions seem merged for wheels and windshields on some, I don't see why exactly. So some manual cleanup may be necessary.


Enjoy.

Edit: latest here: [viewtopic.php?p=141959#p141959](http://forum.xentax.com/viewtopic.php?p=141959#p141959)
## Post #201
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2018-07-06T11:29:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Having some trouble with weapon import. Some weapons f.e. bow and crossbow import and work just fine. However others, like ak74m don't have any weights and accessories are placed at origin point:



Third group, like 1887, just fail to import:
## Post #202
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-06T15:40:22+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from YourImaginaryFriend
>
> Having some trouble with weapon import. Some weapons f.e. bow and crossbow import and work just fine. However others, like ak74m don't have any weights and accessories are placed at origin point:


Third group, like 1887, just fail to import:

Yeah I figured this may come up on some objects, it's a failure to parse the material files. There's a *lot* of variations. I'll see if I can add support for these.
 not sure about the akm but i will take a look as well.
## Post #203
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-06T16:45:49+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ok about the ak47m, that's normal. Only the base rifle has weighting, for the trigger etc.  Part of the skeleton 'bones' are simply to define 'attach points' and are labeled as such: 



The accessories simply get positioned by the game engine according to these points, they have no weights or skeleton.


Will be back shortly with a fix for the material import on the other.

EDIT: actually, are you sure it was the 1887 that crashes? All files there loaded for me fine with no errors. It would probably help to not only have the name of the file but the full error log, including all of my debug msgs.
## Post #204
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-07T18:35:38+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Just a heads up to everyone, anyone else posting or IMing me about 'I don't see the suits" will be ignored, because it means you didn't read and follow my extremely clear instructions.
## Post #205
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2018-07-07T21:07:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Just a quick question
What has weights and what doesn't

Beacuse as i read trough the post it seems that
Guns and characters has but not Vehicles or am i wrong?
## Post #206
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-07T21:33:00+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Faithfullfaun
>
> Just a quick question
What has weights and what doesn't

Beacuse as i read trough the post it seems that
Guns and characters has but not Vehicles or am i wrong?

yes I have a theory about vehicles i'm going to be looking into today.
## Post #207
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2018-07-08T00:48:24+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Fixed my problem with some weapons not importing into blender by moving them to different folder. Not sure how it was related but it all works now
## Post #208
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-08T00:51:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from YourImaginaryFriend
>
> Fixed my problem with some weapons not importing into blender by moving them to different folder. Not sure how it was related but it all works now

Cool. it's possible if you had a very long path, it was hitting the 256 character limit. They have some really long file and folder names in this stuff.


On another note, I think I've almost figured out how they store weights for vehicles, it's table based it seems:



Just trying to make it work in an automated fashion.
## Post #209
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-08T01:51:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Ok, I got weights for vehicles working.   It seems since they are primarily mechanical in nature, they use a table to define start face and number of faces for each relevant bone, and assume weight is always 1.0. ( I was wondering what that new block was for) Strange they only use it for vehicles and not weapons. but anyway, now you can open the doors and hood, and spin the tires and crap   


Also that solved the mystery of why the damaged parts weren't materials or separate objects, they are attached to bones for some reason... I guess so they can be moved in and out of place. (note the damage levels on windshield and tires)




Also as an added bonus, you can now optionally check the "Import all LODs" checkbox on the file pick screen, to have it load in all LOD models, properly named (and yep they have their materials and weights too)




Enjoy.
[io_scene_FarCry5.zip](https://xentaxbackup.github.io/file/14575_io_scene_FarCry5.zip)
## Post #210
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-07-08T04:08:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

would you be able to upload a character like joseph seed
## Post #211
- Username: Alexxxxxxx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Feb 02, 2017 6:44 am
- Post datetime: 2018-07-08T13:07:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hi guys! Prompt, and whether there is a converter XBT in DDS
As I understand, converters from other parts of Far Cry do not work
## Post #212
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-08T15:25:52+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from connorukboy
>
> would you be able to upload a character like joseph seed

nope sorry. I just make the tools.
## Post #213
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-07-08T17:11:59+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> connorukboy wrote:would you be able to upload a character like joseph seed 

nope sorry. I just make the tools.

well tbh with your tools can someone now have the ability to upload characters ?
## Post #214
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-08T18:14:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from connorukboy
>
> volfin wrote:connorukboy wrote:would you be able to upload a character like joseph seed 

nope sorry. I just make the tools.  

well tbh with your tools can someone now have the ability to upload characters ?

I"m sure ppl will in the usual places.
## Post #215
- Username: brucektrain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 08, 2015 6:43 pm
- Post datetime: 2018-07-09T11:10:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

What Unpacked Folder or .dat/.fat where's all the cars (Vehicles) is stored? and Anybody knows there's updated of Blender importer (XBG) *since it's not importing seperate objects or deformed mesh* or Lastest Unpacker. Also How Can I convert Textures? I need it make Separate Mesh so i can work on Door Animations, Gauges Animations to Work for Assetto Corsa.
## Post #216
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-09T15:51:26+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from brucektrain
>
> What Unpacked Folder or .dat/.fat where's all the cars (Vehicles) is stored? and Anybody knows there's updated of Blender importer (XBG) *since it's not importing seperate objects or deformed mesh* or Lastest Unpacker. Also How Can I convert Textures? I need it make Separate Mesh so i can work on Door Animations, Gauges Animations to Work for Assetto Corsa.

Start here and read the thread: [viewtopic.php?p=141756#p141756](http://forum.xentax.com/viewtopic.php?p=141756#p141756)

I assume you're talking about the old importer for Far Cry 4, Primal, because mine is up to date, I just fricking wrote it.  And I seriously doubt anyone will ever do 'deformed mesh'. 

vehicles are under 'graphics/vehicles'

As for textures, they didn't change from Far Cry 3/ Far Cry 4 / Far Cry Primal. so you need the tool from that which can unpack the texture.LOD files. (i don't recall where to find it, honestly)
## Post #217
- Username: brucektrain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 08, 2015 6:43 pm
- Post datetime: 2018-07-10T05:26:06+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> brucektrain wrote:What Unpacked Folder or .dat/.fat where's all the cars (Vehicles) is stored? and Anybody knows there's updated of Blender importer (XBG) *since it's not importing seperate objects or deformed mesh* or Lastest Unpacker. Also How Can I convert Textures? I need it make Separate Mesh so i can work on Door Animations, Gauges Animations to Work for Assetto Corsa. 

Start here and read the thread: viewtopic.php?p=141756#p141756

I assume you're talking about the old importer for Far Cry 4, Primal, because mine is up to date, I just fricking wrote it.  And I seriously doubt anyone will ever do 'deformed mesh'. 

vehicles are under 'graphics/vehicles'

As for textures, they didn't change from Far Cry 3/ Far Cry 4 / Far Cry Primal. so you need the tool from that which can unpack the texture.LOD files. (i don't recall where to find it, honestly)

When Imported to Blender. And Converted DDS textures shows Complete Black Blank.
## Post #218
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-07-10T15:48:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from brucektrain
>
> volfin wrote:brucektrain wrote:What Unpacked Folder or .dat/.fat where's all the cars (Vehicles) is stored? and Anybody knows there's updated of Blender importer (XBG) *since it's not importing seperate objects or deformed mesh* or Lastest Unpacker. Also How Can I convert Textures? I need it make Separate Mesh so i can work on Door Animations, Gauges Animations to Work for Assetto Corsa. 

Start here and read the thread: viewtopic.php?p=141756#p141756

I assume you're talking about the old importer for Far Cry 4, Primal, because mine is up to date, I just fricking wrote it.  And I seriously doubt anyone will ever do 'deformed mesh'. 

vehicles are under 'graphics/vehicles'

As for textures, they didn't change from Far Cry 3/ Far Cry 4 / Far Cry Primal. so you need the tool from that which can unpack the texture.LOD files. (i don't recall where to find it, honestly)

When Imported to Blender. And Converted DDS textures shows Complete Black Blank.

Yes as mentioned in the instructions post I directed you to, the DDS files are in DX10 format which blender does not support. you need to convert them using some other application that supports DX10 format first.
## Post #219
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-08-01T01:37:38+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Just a reminder that a Far Cry 5-specific packer in unnecessary, as the Far Cry Primal one works.
## Post #220
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-08-01T01:42:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from daemon1
>
> volfin wrote: - Import full maps (don't even ask about this)
I did test exports of "the crew" maps, and i think far cry must be very close, if not identical to it, so its very possible. However I dont see why anybody may need maps for such game.
I don't care much about Far Cry 5 maps, but older games like Watch Dogs had some nice interiors I would love to get my hands on. [https://forums.guru3d.com/threads/watch ... 6/page-136](https://forums.guru3d.com/threads/watch_dogs-general-moding.395946/page-136) Even more similar to The Crew's engine than Far Cry 5, even though it has a different name. It's the Far Cry 3 engine with minor modifications.
## Post #221
- Username: Tythagoras
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 07, 2018 4:07 am
- Post datetime: 2018-08-07T00:55:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

GRiNDERKILLER's file share of the ekey's unpack tool from page 12 seems to have expired.  Could someone upload that again somewhere?

Also, has anyone explored getting the .ark.fcb files in entityarchetypeslibrary to convert to something one can edit?  I can't seem to get anything useful out of the existing editors, I think they need string tables for FC5, but I don't know where to look for those.

Will FC5 even let me mod the damage the weapons do, once it gets re-packed and all?
## Post #222
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2018-08-07T02:05:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Tythagoras
>
> Also, has anyone explored getting the .ark.fcb files in entityarchetypeslibrary to convert to something one can edit?  I can't seem to get anything useful out of the existing editors, I think they need string tables for FC5, but I don't know where to look for those.

Funny you mention that, I'm actually working on my tool called FCBastard as we speak! I'm currently in the middle of a huge rewrite, but any changes I commit can be found at the [GitHub repository](https://github.com/Fireboyd78/DisruptEd). You'll notice I called it "DisruptEd" thinking it was for the Watch_Dogs games, but I plan on renaming it eventually (since it supports all Dunia-based games!)

Now, as for the reason I came here, I'm simply requesting that whoever wrote the Far Cry 5 DAT Unpacker (I'm using V0.2.2-r9) to please make it so we can VIEW the .fat files WITHOUT extracting 500GB of data...the FC5.Lib.Dll is also literally just an unpacker (what a shock!) with absolutely no use outside of the accompanying unpacker itself. I'm sick of using 5 different tools for games that all use the same exact engine! Gibbed.Tools.Dunia, Gibbed.Tools.Dunia2, Gibbed.Tools.Disrupt...WHEN WILL THE MADNESS END?!

We need to get together and create what I'd refer to as FATMan, the all-in-one Dunia archive unpacker! I'll help if I need to, but holy shit is this driving me insane using different tools of differing qualities (some of which have the most annoying bugs on the planet)!
## Post #223
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-07T03:46:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from CarLuver69
>
> Tythagoras wrote:Now, as for the reason I came here, I'm simply requesting that whoever wrote the Far Cry 5 DAT Unpacker (I'm using V0.2.2-r9) to please make it so we can VIEW the .fat files WITHOUT extracting 500GB of data...

He released the source code here: [viewtopic.php?p=139736#p139736](http://forum.xentax.com/viewtopic.php?p=139736#p139736)
have at it
## Post #224
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2018-08-08T05:07:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from CarLuver69
>
> I'm sick of using 5 different tools for games that all use the same exact engine! Gibbed.Tools.Dunia, Gibbed.Tools.Dunia2, Gibbed.Tools.Disrupt...WHEN WILL THE MADNESS END?!I chose to do that because the engine versions are distinct enough to have some differences. If I were to revisit it I would consider a single set of tools, but I would still be making game-specific tools for each of those since they have different variations on data formats when it comes to game-specific data (beyond archive format).

Edit: Also, you mention bugs. If this is bugs in my code I'd be happy to hear about them.
## Post #225
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2018-08-09T09:05:49+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> CarLuver69 wrote:Tythagoras wrote:Now, as for the reason I came here, I'm simply requesting that whoever wrote the Far Cry 5 DAT Unpacker (I'm using V0.2.2-r9) to please make it so we can VIEW the .fat files WITHOUT extracting 500GB of data...

He released the source code here: viewtopic.php?p=139736#p139736
have at it
Hmm, that doesn't look like the one I was referring to -- but hey, that's better than nothing! Thanks!

> Reply from Rick
>
> Also, you mention bugs. If this is bugs in my code I'd be happy to hear about them.
I was mostly referring to the "FC5 Unpacker" I have, it fails to extract some archives properly which results in tons of "corrupted" files. But I think Ekey's unpacker looks more promising, so I'll give that a shot and see if it's any better.

As for bugs in your tools, I believe it's some unknown files not being flagged correctly (XML for example), therefore missing an extension and easily missed when snooping around.

[Latest beta of FCBastard!](https://cdn.discordapp.com/attachments/433420047097135104/477030936874319902/FCBastard1.9.818-dev_20180809-0124.7z)

```
haven't implemented support for watch_dogs entitylibrary stuff yet though, sorry
now supports .rml and FCB2/FCB3 files properly
I should mention however that the write cache is currently broken, so .fcb files won't take advantage of cached data offsets (it'll write the same data in multiple places instead of referencing one place), so it may cause crashes if the file sizes differ too much
```
## Post #226
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2018-08-09T19:16:51+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from CarLuver69
>
> 
I was mostly referring to the "FC5 Unpacker" I have, it fails to extract some archives properly which results in tons of "corrupted" files. But I think Ekey's unpacker looks more promising, so I'll give that a shot and see if it's any better.
Fun fact: FC5 Unpacker is Ekey's unpacker. And it does job pretty well if you have right filenames.
BTW you probably used the old one with GUI which has a bug with decompression or something.
## Post #227
- Username: Knmpm111
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 27, 2018 1:21 am
- Post datetime: 2018-08-17T09:44:52+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

More info about porting characters for you guys.

The "\wardrobe\suit" folder does not contain villains outfits for "villains". It contains outfits for player available in the game to wear.



So... those who do not have any files in "\wardrobe\suit" after unpacking DAT files have the game outdated. These "suits" came with one of the updates and are not linked to the actual villains.

The actual villains have their "parts" in their respective folders ("\wardrobe\head", "\wardrobe\top", "\wardrobe\hair" etc.) (example for hair: "\graphics\_common\characters\fc5\wardrobe\hair\lieu").
If you are looking for John Seed - search "lieu001" and "lieu01" (he is "lieutenant" number "1", Jacob is "2", Faith is "3", Joseph is "4"), find '.xbg' parts, import them with volfin's importer, import the body and textures ('.bwsk', '.dpdx' and '.xbt' files - I don't have any idea how to operate with generic parts, most of you guys here will probably know).


EDIT: Ekey's latest version of unpacker on page 17
## Post #228
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-08-20T23:42:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

[quote="Knmpm111"]More info about porting characters for you guys.

The "\wardrobe\suit" folder does not contain villains outfits for "villains". It contains outfits for player available in the game to wear.



So... those who do not have any files in "\wardrobe\suit" after unpacking DAT files have the game outdated. These "suits" came with one of the updates and are not linked to the actual villains.

The actual villains have their "parts" in their respective folders ("\wardrobe\head", "\wardrobe\top", "\wardrobe\hair" etc.) (example for hair: "\graphics\_common\characters\fc5\wardrobe\hair\lieu").
If you are looking for John Seed - search "lieu001" and "lieu01" (he is "lieutenant" number "1", Jacob is "2", Faith is "3", Joseph is "4"), find '.xbg' parts, import them with volfin's importer, import the body and textures ('.bwsk', '.dpdx' and '.xbt' files - I don't have any idea how to operate with generic parts, most of you guys here will probably know).


Ekey's latest version of unpacker here (temporarily shared by volfin under this link):
[https://drive.google.com/file/d/1dK9i5g ... sp=sharing](https://drive.google.com/file/d/1dK9i5gDUd_l1MmeY0bKZ1wD8Qt2h0Bxq/view?usp=sharing)[/quote

how do i get this unpacker to work, what do i have to do?
## Post #229
- Username: Knmpm111
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 27, 2018 1:21 am
- Post datetime: 2018-08-21T13:36:45+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from connorukboy
>
> how do i get this unpacker to work, what do i have to do?

Create .bat file and paste this:

@echo off
FC5.Unpacker D:\fc5files\common.fat D:\fc5files
pause

Change path to your .fat files, change .fat names (in order) and set unpack destination folder.
Remember to extract it in exact order volfin showed on page 13.
## Post #230
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-08-21T17:22:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Knmpm111
>
> connorukboy wrote:how do i get this unpacker to work, what do i have to do?

Create .bat file and paste this:

@echo off
FC5.Unpacker D:\fc5files\common.fat D:\fc5files
pause

Change path to your .fat files, change .fat names (in order) and set unpack destination folder.
Remember to extract it in exact order volfin showed on page 13.

anyone who can rip Joseph seed full model, i will paypal 10 dollars
## Post #231
- Username: llazyneiph
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 16, 2018 7:06 pm
- Post datetime: 2018-08-22T11:38:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Took me all day but I finally got all the files unpacked and stuff.
Thought I would share a few pics of the models because I love them!


(I know his hair is the wrong colour lol)




Only textured Jacob for now since he's my favorite, but I need to find out how to convert the rest of the .xbt files to .dds 
Anyone got any suggestions?
I've tried Dunia Tools, Gibbed Tools, and Kodi.Texture to no avail

If I've missed something on the thread about converting these, would be very grateful if someone could point it out for me! 
(I'm a total n00b at this, so I really appreciate any help!)

edit: same goes for the bwsk files, if anyone knows anything about them, would be much appreciated!
## Post #232
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-08-22T15:40:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from llazyneiph
>
> Took me all day but I finally got all the files unpacked and stuff.
Thought I would share a few pics of the models because I love them!

Only textured Jacob for now since he's my favorite, but I need to find out how to convert the rest of the .xbt files to .dds 
Anyone got any suggestions?
I've tried Dunia Tools, Gibbed Tools, and Kodi.Texture to no avail

If I've missed something on the thread about converting these, would be very grateful if someone could point it out for me! 
(I'm a total n00b at this, so I really appreciate any help!)

edit: same goes for the bwsk files, if anyone knows anything about them, would be much appreciated!

As I mentioned the textures are the same as previous far cry games.  In fact, the format is the same as far Cry 2, Far Cry 3, Far Cry 4, and Far Cry Primal. So there's already tons of tools to convert them. I am simply too lazy to do the searching for you 

Converting is even something you can do yourself, it's just cutting off the first 36 bytes of the file.

Cut off everything up to the letters DDS, and poof, it's a DDS file.


EDIT: I checked my library of tools on my hard drive, and I found the texture tool I use. you used to be able to DL it here:
[https://robertrouhani.wordpress.com/201 ... y-2-stuff/](https://robertrouhani.wordpress.com/2010/08/04/far-cry-2-stuff/)

But since his link is broken, I'll attach a copy here. It Batch converts.
[Robmaister.rar](https://xentaxbackup.github.io/file/14771_Robmaister.rar)
## Post #233
- Username: llazyneiph
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 16, 2018 7:06 pm
- Post datetime: 2018-08-22T15:57:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> llazyneiph wrote:Took me all day but I finally got all the files unpacked and stuff.
Thought I would share a few pics of the models because I love them!

Only textured Jacob for now since he's my favorite, but I need to find out how to convert the rest of the .xbt files to .dds 
Anyone got any suggestions?
I've tried Dunia Tools, Gibbed Tools, and Kodi.Texture to no avail

If I've missed something on the thread about converting these, would be very grateful if someone could point it out for me! 
(I'm a total n00b at this, so I really appreciate any help!)

edit: same goes for the bwsk files, if anyone knows anything about them, would be much appreciated!

As I mentioned the textures are the same as previous far cry games.  In fact, the format is the same as far Cry 2, Far Cry 3, Far Cry 4, and Far Cry Primal. So there's already tons of tools to convert them. I am simply too lazy to do the searching for you 


Converting is even something you can do yourself, it's just cutting off the first 36 bytes of the file.

Cut off everything up to the letters DDS, and poof, it's a DDS file.


EDIT: I checked my library of tools on my hard drive, and I found the texture tool I use. you can DL it here:
https://robertrouhani.wordpress.com/201 ... y-2-stuff/

Batch converts.

Ahhh thats so funny, literally as you posted this I figured out my own way!

Basically I converted the .xbt using 'xbt2dds', then that gave me a DX10 dds (i think, like I said, i'm a n00b!), and after some research I realised you can't open those in photoshop yet, so I had to open it in Noesis and convert it to a .png... Bit of a roundabout way to go but I got it done in the end   
I will try the program you linked though, since it'll probably be easier lmao

thanks for replying and for everything on this thread!  

edit: just checked out your link, and just wanted to give a heads up that the link on the page says 'site can't be reached'
## Post #234
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-08-22T21:00:19+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from llazyneiph
>
> volfin wrote:llazyneiph wrote:Took me all day but I finally got all the files unpacked and stuff.
Thought I would share a few pics of the models because I love them!

Only textured Jacob for now since he's my favorite, but I need to find out how to convert the rest of the .xbt files to .dds 
Anyone got any suggestions?
I've tried Dunia Tools, Gibbed Tools, and Kodi.Texture to no avail

If I've missed something on the thread about converting these, would be very grateful if someone could point it out for me! 
(I'm a total n00b at this, so I really appreciate any help!)

edit: same goes for the bwsk files, if anyone knows anything about them, would be much appreciated!

As I mentioned the textures are the same as previous far cry games.  In fact, the format is the same as far Cry 2, Far Cry 3, Far Cry 4, and Far Cry Primal. So there's already tons of tools to convert them. I am simply too lazy to do the searching for you 


Converting is even something you can do yourself, it's just cutting off the first 36 bytes of the file.

Cut off everything up to the letters DDS, and poof, it's a DDS file.


EDIT: I checked my library of tools on my hard drive, and I found the texture tool I use. you can DL it here:
https://robertrouhani.wordpress.com/201 ... y-2-stuff/

Batch converts.

Ahhh thats so funny, literally as you posted this I figured out my own way!

Basically I converted the .xbt using 'xbt2dds', then that gave me a DX10 dds (i think, like I said, i'm a n00b!), and after some research I realised you can't open those in photoshop yet, so I had to open it in Noesis and convert it to a .png... Bit of a roundabout way to go but I got it done in the end   
I will try the program you linked though, since it'll probably be easier lmao

thanks for replying and for everything on this thread!  

edit: just checked out your link, and just wanted to give a heads up that the link on the page says 'site can't be reached'


would you be able to share the joseph model as obj with textures if you manage to do that pls?
## Post #235
- Username: MAESTRE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 02, 2017 11:34 am
- Post datetime: 2018-08-24T07:42:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> llazyneiph wrote:Took me all day but I finally got all the files unpacked and stuff.
Thought I would share a few pics of the models because I love them!

Only textured Jacob for now since he's my favorite, but I need to find out how to convert the rest of the .xbt files to .dds 
Anyone got any suggestions?
I've tried Dunia Tools, Gibbed Tools, and Kodi.Texture to no avail

If I've missed something on the thread about converting these, would be very grateful if someone could point it out for me! 
(I'm a total n00b at this, so I really appreciate any help!)

edit: same goes for the bwsk files, if anyone knows anything about them, would be much appreciated!

As I mentioned the textures are the same as previous far cry games.  In fact, the format is the same as far Cry 2, Far Cry 3, Far Cry 4, and Far Cry Primal. So there's already tons of tools to convert them. I am simply too lazy to do the searching for you 

Converting is even something you can do yourself, it's just cutting off the first 36 bytes of the file.

Cut off everything up to the letters DDS, and poof, it's a DDS file.


EDIT: I checked my library of tools on my hard drive, and I found the texture tool I use. you used to be able to DL it here:
https://robertrouhani.wordpress.com/201 ... y-2-stuff/

But since his link is broken, I'll attach a copy here. It Batch converts.

Hi, I'm new on this Far Cry's ripping world. I'm getting a problem with your python script (the importer script). I know that is something that I'm missing or a mistake I'm doing because everybody are able to import character's mesh to their Blender.


First of all, If I just click on install from file, it doesn't add anything to my Blender.
So I just installed it on /AppData/Roaming Blender's script folder, XNALara is stored there so I don't think there's an error here.


Once I do that, I'm able to enable your script. But the problem is when I want to import some character's mesh, it just crashes my Blender, not even an error log.


I don't even own Far Cry 5 lol, but a friend is helping me out, he gave me the files so I don't really know if I need something like those .lua scripts.


I just have .bwsk, .xbg, .xbt and a folder with the character's id name with another .xbg file and a .skeleton file.
It was easy to convert the textures files to DDS with you handy hex trick, but when I want to import an .xbg file, like I said, my Blender crashes.


I'm using Blender 2.78v x64.
## Post #236
- Username: llazyneiph
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 16, 2018 7:06 pm
- Post datetime: 2018-08-25T17:12:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Does anyone actually know what the .bwsk files are?
I'm looking at some of the shoe files, and since the .bwsk files are in a subfolder named '_items', I assume they're meshes? 

How the heck do you open these things? I literally can't find a single thing online about them.
## Post #237
- Username: llazyneiph
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 16, 2018 7:06 pm
- Post datetime: 2018-08-25T17:17:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Maestre, did you try to install it using the actual file or the zipped folder it came in?
Because it needs to be installed in user preferences using the zipped folder
just checking
## Post #238
- Username: ayobhd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 31, 2018 8:09 am
- Post datetime: 2018-09-02T14:02:34+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> brucektrain wrote:What Unpacked Folder or .dat/.fat where's all the cars (Vehicles) is stored? and Anybody knows there's updated of Blender importer (XBG) *since it's not importing seperate objects or deformed mesh* or Lastest Unpacker. Also How Can I convert Textures? I need it make Separate Mesh so i can work on Door Animations, Gauges Animations to Work for Assetto Corsa. 

Start here and read the thread: viewtopic.php?p=141756#p141756

I assume you're talking about the old importer for Far Cry 4, Primal, because mine is up to date, I just fricking wrote it.  And I seriously doubt anyone will ever do 'deformed mesh'. 

vehicles are under 'graphics/vehicles'

As for textures, they didn't change from Far Cry 3/ Far Cry 4 / Far Cry Primal. so you need the tool from that which can unpack the texture.LOD files. (i don't recall where to find it, honestly)

where's all the language files (subtitle) is stored? Farcry 5 ...
## Post #239
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-09-02T17:16:02+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from ayobhd
>
> 
where's all the language files (subtitle) is stored? Farcry 5 ...

oasisstrings.oasis.bin

you can't edit the file because it is encrypted
## Post #240
- Username: ayobhd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 31, 2018 8:09 am
- Post datetime: 2018-09-02T21:50:46+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mlleemiles
>
> ayobhd wrote:
where's all the language files (subtitle) is stored? Farcry 5 ...

oasisstrings.oasis.bin

you can't edit the file because it is encrypted
a cant find the files 
[Capturehh.PNG](https://xentaxbackup.github.io/file/14806_Capturehh.PNG)
## Post #241
- Username: mlleemiles
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Sep 08, 2014 6:20 pm
- Post datetime: 2018-09-03T03:16:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from ayobhd
>
> mlleemiles wrote:ayobhd wrote:
where's all the language files (subtitle) is stored? Farcry 5 ...

oasisstrings.oasis.bin

you can't edit the file because it is encrypted
a cant find the files

You need to unpack the files first, although I don't know the existent tools work with ps4 files.
## Post #242
- Username: ayobhd
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 31, 2018 8:09 am
- Post datetime: 2018-09-03T06:13:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

oasisstrings.oasis.bin

You need to unpack the files first, although I don't know the existent tools work with ps4 ...
Which files I have to unpack can you tell me ....
## Post #243
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-09-05T17:09:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

The model's eye mesh is broken.
So UV Map and Texture map do not match. 
Does anyone know why or how to solve it?
## Post #244
- Username: llazyneiph
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 16, 2018 7:06 pm
- Post datetime: 2018-09-08T10:08:29+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from TSelman61X
>
> The model's eye mesh is broken.
So UV Map and Texture map do not match. 
Does anyone know why or how to solve it?

Only way me and a friend have been doing it is just re-mapping the uv and retexture-ing it
## Post #245
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-09-14T09:29:12+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Have been away for a while. Is there a repacker yet?
## Post #246
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-09-21T01:47:41+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

GRINDERKILLER reuploaded his unpacker here:

I'm removing my temporary download in an earlier post.
[https://www107.zippyshare.com/v/N3JPZYkt/file.html](https://www107.zippyshare.com/v/N3JPZYkt/file.html)
## Post #247
- Username: connorukboy
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 29, 2018 9:53 pm
- Post datetime: 2018-10-09T22:09:07+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

[https://pre00.deviantart.net/8b2b/th/pr ... coyoxa.png](https://pre00.deviantart.net/8b2b/th/pre/f/2018/281/9/0/far_cry_5_joseph_seed__wip__by_connorukboy-dcoyoxa.png)

can anyone send me textures for josephs belt, bracelet and glasses, thats all i need lmao, i know the hair needs fixing
## Post #248
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2018-10-24T12:31:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from volfin
>
> GRINDERKILLER reuploaded his unpacker here:

I'm removing my temporary download in an earlier post.
https://www107.zippyshare.com/v/N3JPZYkt/file.html
I dont suppose it has the ability to repack yet?
## Post #249
- Username: BigTinz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 16, 2018 5:53 pm
- Post datetime: 2018-11-24T02:50:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Apparently the Primal repacker works just fine.
## Post #250
- Username: minttt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 18, 2017 9:49 am
- Post datetime: 2018-12-01T12:44:43+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Hey there 

does anybody here know how to change the stats of the weapons? Like viewmodel FOV and damage and so on...?
I managed to unpack and convert the Fcb files to Xml files. But there are nearly over 4000 of them and i got no idea how to find the right files.
Any tip would be really welcome.

Thanks!
## Post #251
- Username: afongkoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 05, 2019 10:11 pm
- Post datetime: 2019-01-05T14:19:17+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

aa.png (58.68 KiB) Viewed 303 times


So I managed to import the model to blender. But now, I still can't figure out how to convert the .xbt textures. What do I need to do to convert them?
## Post #252
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-06T04:28:55+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from afongkoi
>
> What do I need to do to convert them?
Try: [viewtopic.php?p=146821#p146821](http://forum.xentax.com/viewtopic.php?p=146821#p146821)
## Post #253
- Username: afongkoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 05, 2019 10:11 pm
- Post datetime: 2019-01-06T14:09:13+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from mono24
>
> afongkoi wrote:What do I need to do to convert them?
Try: viewtopic.php?p=146821#p146821

THX A LOT!   
[aaaaaaaaaaaaa.png](https://xentaxbackup.github.io/file/15427_aaaaaaaaaaaaa.png)
## Post #254
- Username: tschiesas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Apr 07, 2018 10:33 pm
- Post datetime: 2019-01-18T07:18:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from BigTinz
>
> Apparently the Primal repacker works just fine.
What?
So does that mean we are finally able to modify game configs?
## Post #255
- Username: kekikcilerakin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 11, 2015 5:32 am
- Post datetime: 2019-03-03T20:02:32+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Any way to repack FC New Dawn files?
## Post #256
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2019-03-08T18:55:55+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

hi all i use RavioliGameTools_v2.8 unpack most games it best most files if big files take bit time i do bnk,dirt, grid, hope this helps. as well use Extractor.exe as well GameExtractor.exe, i use RavioliGameTools on the farcry5_english.dat gave me all wwise sound files 64411 try do mp3 but i try ogg or wav next.
## Post #257
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2019-03-09T10:23:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

hi all here video me showing u how unpack dat files using RavioliGameTools_v2.8 as well play a lot audio files for u. sorry mic got echo need better one. [https://youtu.be/BeGuTn3KyNA](https://youtu.be/BeGuTn3KyNA) i made 2 parts to it need help popup ok.
## Post #258
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2019-03-27T12:04:57+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Not sure if this will help anyone but I've worked out which characters are what in the files. Not all of them but a few. So on top of Jacob, Faith, John and Joseph which were mentioned in an earlier post these are theirs and the ones that I worked out.

Lieu01(001) - John Seed
Lieu02 (002) - Jacob Seed
Lieu03 (003) - Faith Seed
Lieu04 (004) - Joseph Seed

Key01 - Nick Rye
Key02 - Mary May Fairgrave
Key03 - Eli Palmer

uni002 - Morris	
uni003 - MelvinAdams	
uni004 - Larry Parker	
uni005 - Skylar	
uni007 - Grace Armstrong	
uni008 - Holly Pepper	
uni009 - Wendell Darrah	
uni010 - Open World Hunter	
uni011 - Casey Seagal	
uni012 - Merle Briggs	
uni013 - Wheaty
uni015 - Chad Wolanski
uni023 - Shop Owner
uni024 - Sharky Boshaw
uni025 - Tammy Palmer
uni027 - Bo
uni031 - Doc Perkins
uni032 - Ryan Elliot
uni033 - Jess Black
uni034 - Willis Huntley
uni035 - Pastor Jerome Jeffries
uni037 - Open World Fisherman
uni038 - Wade Fowler
uni040 - Deputy Joey Hudson
uni042 - Hurk Drubman Senior
uni043 - Hurk
uni044 - Deputy Staci Pratz
uni046 - Clutch Nixon
uni047 - Kay Wheeler
uni048 - Kim Rye
uni049 - US Marshal Cameron Burke
uni050 - Sheriff Earl Whitehorse
uni051 - Aaron Tweak Kirby
uni052 - Dr Charles Lindsey
uni053 - Tracey Lader
uni054 - Virgil Minkler
uni055 - Zip Kupka
uni056 - Adelaide Drubman
uni057 - Xander Flynn
uni058 - Guy Marvel
uni059 - Miss Mable
uni061 - Dutch
uni062 - The Sister
uni063 - The Brother
uni064 - Scott Scooter Tillman
uni065 - Glen Parker Before
uni066 - Glen Parker After
uni067 - Dave Fowler
uni068 - George Beel
uni069 - Earl Briggs
## Post #259
- Username: Xentone420
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 19, 2019 5:47 pm
- Post datetime: 2019-04-23T13:11:13+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I'm sorry for resurrecting this old thread.

I was able to extract the geometry and import it into Blender thanks to @volfin's script. I also converted a lot of xbt files into dds but I can't figure how to see the textured file in Blender.. I mean, how can I check which textures is connected to e.g. "barn_floor_01"?

Edit: maybe I'm missing something because 90% of textures are just 128 or 64..
## Post #260
- Username: Imperator3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 21, 2010 3:06 am
- Post datetime: 2019-07-20T16:03:12+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I unpacked the resources, but some of the textures are broken. For example, the texture veh_gen_car_light_d from graphics\vehicles\land\heavy\veh_semi_classic in XnView:
[](http://vfl.ru/fotos/2e2f59c427273461.html)
And in photoshop:
[](http://vfl.ru/fotos/ac75ea7327273467.html)
How to fix it?
## Post #261
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-21T18:37:34+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Imperator3 ↑Sun Jul 21, 2019 12:03 am at Sun Jul 21, 2019 12:03 am
>
> 
I unpacked the resources, but some of the textures are broken. For example, the texture veh_gen_car_light_d from graphics\vehicles\land\heavy\veh_semi_classic in XnView:

And in photoshop:

How to fix it?

You should use another converter.
or Can you share raw texture file?
## Post #262
- Username: Imperator3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 21, 2010 3:06 am
- Post datetime: 2019-07-22T08:25:00+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from TSelman61X ↑Mon Jul 22, 2019 2:37 am at Mon Jul 22, 2019 2:37 am
>
> 
You should use another converter.
or Can you share raw texture file?
I use Robmaister converter from this post:
[viewtopic.php?f=10&t=17888&start=225#p143489](https://forum.xentax.com/viewtopic.php?f=10&t=17888&start=225#p143489)
Or do I need to use another converter?
## Post #263
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-22T15:47:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Imperator3 ↑Mon Jul 22, 2019 4:25 pm at Mon Jul 22, 2019 4:25 pm
>
> 
I use Robmaister converter from this post:
viewtopic.php?f=10&t=17888&start=225#p143489
Or do I need to use another converter?

But there are many converters.
But the problem may be in Raw textures or converter.  

To better understand, you should share sample textures.
## Post #264
- Username: Imperator3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 21, 2010 3:06 am
- Post datetime: 2019-07-22T17:29:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from TSelman61X ↑Mon Jul 22, 2019 11:47 pm at Mon Jul 22, 2019 11:47 pm
>
> 


But there are many converters.
But the problem may be in Raw textures or converter.  

To better understand, you should share sample textures.
There are two files in the archive - original xbt and converted dds.
[veh_heavy_truck_ext_m.rar](https://xentaxbackup.github.io/file/16513_veh_heavy_truck_ext_m.rar)
## Post #265
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2019-07-22T22:24:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Imperator3 ↑Tue Jul 23, 2019 1:29 am at Tue Jul 23, 2019 1:29 am
>
> 
There are two files in the archive - original xbt and converted dds.

Dude, your example is fine.  There's no problem with the texture map.
What program do you open dds files?  I am using "IntelTextureWorks_1.0.4" for photoshop. 

if you are still having problems you can send me other examples.
[SharedScreenshot.jpg](https://xentaxbackup.github.io/file/16514_SharedScreenshot.jpg)
## Post #266
- Username: Imperator3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 21, 2010 3:06 am
- Post datetime: 2019-07-23T13:30:20+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from TSelman61X ↑Tue Jul 23, 2019 6:24 am at Tue Jul 23, 2019 6:24 am
>
> 

What program do you open dds files?  I am using "IntelTextureWorks_1.0.4" for photoshop.
I use XnView Classic amd Photoshop with Nvidia DDS plugin.
## Post #267
- Username: Faithfullfaun
- Rank: advanced
- Number of posts: 79
- Joined date: Mon Nov 28, 2016 4:12 pm
- Post datetime: 2019-07-23T20:34:44+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Nvidia plugin is not very good

Use "Intel® Texture Works Plugin for Photoshop"
Or you can try use Noesis
## Post #268
- Username: padme4000
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 27, 2014 1:46 am
- Post datetime: 2019-08-28T11:03:53+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

I generally use noesis to convert FC5 textures as well, so I definitely suggest that if you don't want to use the other suggested software
## Post #269
- Username: CracksHeaven
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 30, 2019 4:45 am
- Post datetime: 2019-10-29T20:56:26+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Alright so I just started to learn how to mod and managed to extract fat and dat files with the extractor. I particulary aim to change the soundtracks in the car with the radio to add custom songs. I searched for hours but I wasn't able to find them ( I took a look in patch / common / farcry5 dat files in the folder soundbinary ). They are probably in a wem format and I listened almost all the tracks ( turned them into ogg files ) but I never found the songs. However, I found the sounds that start when you open the map menu and I might be able to modify them and repack them to use it with the Resistance mod from nexusmod. If someone knows where those radio songs are located let me know, thx
## Post #270
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2020-07-18T15:30:37+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

so i extracted all the files, i think*. is unpacking FC5 stuck at the point where we don't get the material files named correctly when extracting them, and we need to manually look for the material files/textures used by the model, by scanning the bin material files, after opening the model in blender or smthg, and seeing what materials the model uses? oh boy..

*another question, what .fat files do we need to export in order to get all the models and textures extracted?
i followed the instructions to import it into blender, they said to unpack:

common.fat
worlds/installpkg.fat
worlds/farcry5.fat
patch.fat

are there more to get all models, and textures?
## Post #271
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2020-11-08T15:15:27+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ekey ↑Wed Apr 04, 2018 8:25 am at Wed Apr 04, 2018 8:25 am
>
> 
Updated here
Code: Select all[Usage]
    FC5.Unpacker <m_FATFile> <m_Directory>

    m_FATFile - Source of FAT file
    m_Directory - Destination directory

[Examples]
    FC5.Unpacker D:\FC5\data_final\pc\common.fat D:\Unpacked\common

Im a noob and dont know how to use command line tools. it says press any key to continue and then closes the window. can someone exlpain to me how to use it
## Post #272
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2020-11-09T13:50:01+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from DV9 x Drillz ↑Sun Nov 08, 2020 11:15 pm at Sun Nov 08, 2020 11:15 pm
>
> 
Ekey wrote: ↑Wed Apr 04, 2018 8:25 am
Updated here
Code: Select all[Usage]
    FC5.Unpacker <m_FATFile> <m_Directory>

    m_FATFile - Source of FAT file
    m_Directory - Destination directory

[Examples]
    FC5.Unpacker D:\FC5\data_final\pc\common.fat D:\Unpacked\common


Im a noob and dont know how to use command line tools. it says press any key to continue and then closes the window. can someone exlpain to me how to use it

Most command line tools ask you to press a key to continue to avoid disappearance of the window.
Open a command line window and run the tool from there - then it won't disappear and you can see what really happened.
## Post #273
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2020-11-09T15:34:41+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Csimbi ↑Mon Nov 09, 2020 9:50 pm at Mon Nov 09, 2020 9:50 pm
>
> 
DV9 x Drillz wrote: ↑Sun Nov 08, 2020 11:15 pm
Ekey wrote: ↑Wed Apr 04, 2018 8:25 am
Updated here
Code: Select all[Usage]
    FC5.Unpacker <m_FATFile> <m_Directory>

    m_FATFile - Source of FAT file
    m_Directory - Destination directory

[Examples]
    FC5.Unpacker D:\FC5\data_final\pc\common.fat D:\Unpacked\common


Im a noob and dont know how to use command line tools. it says press any key to continue and then closes the window. can someone exlpain to me how to use it


Most command line tools ask you to press a key to continue to avoid disappearance of the window.
Open a command line window and run the tool from there - then it won't disappear and you can see what really happened.

Thanks for the reply! so i tried that and manged to run the tool but it doesnt unpack anything? it just repeats the usage and example
## Post #274
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2020-11-09T17:35:13+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from DV9 x Drillz ↑Mon Nov 09, 2020 11:34 pm at Mon Nov 09, 2020 11:34 pm
>
> 
Thanks for the reply! so i tried that and manged to run the tool but it doesnt unpack anything? it just repeats the usage and example
Then your inputs are wrong.
What was the command line you used?
## Post #275
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2020-11-10T14:35:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

cmd issues.jpg (129.13 KiB) Viewed 314 times


> Reply from Csimbi ↑Tue Nov 10, 2020 1:35 am at Tue Nov 10, 2020 1:35 am
>
> 
DV9 x Drillz wrote: ↑Mon Nov 09, 2020 11:34 pm
Thanks for the reply! so i tried that and manged to run the tool but it doesnt unpack anything? it just repeats the usage and example

Then your inputs are wrong.
What was the command line you used?
## Post #276
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2020-11-10T17:05:02+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

You have spaces in the parameters.
Put them in quotes else the program won't recognize them.
E.g. "G:\..." instead of G:\...
## Post #277
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2020-11-11T12:36:25+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Csimbi ↑Wed Nov 11, 2020 1:05 am at Wed Nov 11, 2020 1:05 am
>
> 
You have spaces in the parameters.
Put them in quotes else the program won't recognize them.
E.g. "G:\..." instead of G:\...

thnaks! worked like a charm
## Post #278
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2021-02-07T21:09:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

What about the sound effects? Do they have names or it's just useless numbers?
## Post #279
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2021-02-18T16:44:16+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from kloruklass ↑Mon Feb 08, 2021 5:09 am at Mon Feb 08, 2021 5:09 am
>
> 
What about the sound effects? Do they have names or it's just useless numbers?

Это имена файлов под видом хеш имнах.
## Post #280
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2021-02-19T11:06:58+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000 ↑Fri Feb 19, 2021 12:44 am at Fri Feb 19, 2021 12:44 am
>
> 
kloruklass wrote: ↑Mon Feb 08, 2021 5:09 am
What about the sound effects? Do they have names or it's just useless numbers?


Это имена файлов под видом хеш имнах.

I already extracted the sounds, and there is no way to get the file names.
## Post #281
- Username: JamesBone
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jan 08, 2022 4:43 pm
- Post datetime: 2022-01-25T06:21:09+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from invasion101 ↑Wed Apr 04, 2018 11:31 am at Wed Apr 04, 2018 11:31 am
>
> 
the new version my virus scanner is deleting it I turned my virus scanner real time protection off and I unzip it and it wont run like last version :/

Sorry, my mistake. xD
## Post #282
- Username: cevefas
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Aug 29, 2019 1:36 am
- Post datetime: 2022-07-19T05:44:30+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

how do I combine the parts
## Post #283
- Username: Nitrodax777
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 24, 2023 1:55 pm
- Post datetime: 2023-03-25T04:28:40+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

sorry for the intrusion but as mentioned, the scene importer pulls the necessary XBT file and saves them as DDS in the same directory as the imported XBG model. however it doesnt seem like all of the textures are actually found when importing a vehicle. i know the larger mip files have to be located manually as you said, which i have and thats been a non-issue. the specific problem is that none of the textures are for the interior itself except the decal textures for the gauges. i have the common, farcry5, installpkg, and patch folders unpacked explicitly in the order you posted. but in the graphics section of each directory, i cant seem to find any texture that would indicate having the actual interior details like the dash, steering wheel, seat upholstery, radio, etc. and ive looked in both the _common and vehicles folders within each graphics subfolder. im currently working with veh_semi_classic if it helps you see where i am in terms of finding the actual interior. im just kinda stumped on the whole ordeal. am i missing something? or am i just not looking hard enough?
## Post #284
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2023-03-29T14:22:58+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Nitrodax777 ↑Sat Mar 25, 2023 12:28 pm at Sat Mar 25, 2023 12:28 pm
>
> 
sorry for the intrusion but as mentioned, the scene importer pulls the necessary XBT file and saves them as DDS in the same directory as the imported XBG model. however it doesnt seem like all of the textures are actually found when importing a vehicle. i know the larger mip files have to be located manually as you said, which i have and thats been a non-issue. the specific problem is that none of the textures are for the interior itself except the decal textures for the gauges. i have the common, farcry5, installpkg, and patch folders unpacked explicitly in the order you posted. but in the graphics section of each directory, i cant seem to find any texture that would indicate having the actual interior details like the dash, steering wheel, seat upholstery, radio, etc. and ive looked in both the _common and vehicles folders within each graphics subfolder. im currently working with veh_semi_classic if it helps you see where i am in terms of finding the actual interior. im just kinda stumped on the whole ordeal. am i missing something? or am i just not looking hard enough?

Because all parts of Far Cry do not have a diffuse interior texture car except for the texture mask, the rest is used by normal maps for detailed visibility.
## Post #285
- Username: Jorg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 05, 2017 6:14 am
- Post datetime: 2023-06-17T01:23:50+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

[Latest beta of FCBastard!](https://cdn.discordapp.com/attachments/433420047097135104/477030936874319902/FCBastard1.9.818-dev_20180809-0124.7z) link is dead
## Post #286
- Username: Ganic3000
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Jul 17, 2016 3:13 am
- Post datetime: 2023-06-18T13:40:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Jorg ↑Sat Jun 17, 2023 9:23 am at Sat Jun 17, 2023 9:23 am
>
> 
Latest beta of FCBastard! link is dead
[https://downloads.fcmodding.com/](https://downloads.fcmodding.com/)
## Post #287
- Username: Jorg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 05, 2017 6:14 am
- Post datetime: 2023-06-18T21:37:04+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from Ganic3000 ↑Sun Jun 18, 2023 9:40 pm at Sun Jun 18, 2023 9:40 pm
>
> 
https://downloads.fcmodding.com/
There FCBConverter, but not FCBastard. Need for Watch Dogs.
## Post #288
- Username: masterlkm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 24, 2023 10:51 pm
- Post datetime: 2023-06-24T15:04:31+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

So I assume this tool won't work for FC6? I try to use it and I get system.IO errors, process can't access file because it is being used (screenshot attached). I realize that I might need to use the .fat file and not the .dat I tried that too and get error Invalid version of FAT index file!
Help would be appreciated, also if anyone knows a tool that can in fact extract fc6 files, please let me know.
[image_2023-06-24_170254577.png](https://xentaxbackup.github.io/file/23971_image_2023-06-24_170254577.png)
## Post #289
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2023-06-25T09:58:38+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Why'd you assume it'd work?
## Post #290
- Username: masterlkm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 24, 2023 10:51 pm
- Post datetime: 2023-06-25T13:33:10+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

Well I didn't, I only used it, hoping it would miraculously work and the files are in the same formats in both games essentially having no differences thus being recognizable by the app. That turned out to not be the case so I posted my question here. I played around a bit you know, if it works, great, if no, oh well it was to be expected.
## Post #291
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-25T14:43:42+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from masterlkm ↑Sat Jun 24, 2023 11:04 pm at Sat Jun 24, 2023 11:04 pm
>
> 
if anyone knows a tool that can in fact extract fc6 files, please let me know.
FCBConverter
## Post #292
- Username: masterlkm
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 24, 2023 10:51 pm
- Post datetime: 2023-06-26T11:45:08+00:00
- Post Title: Re: Far Cry 5 .Fat and .Dat Files

> Reply from daemon1 ↑Sun Jun 25, 2023 10:43 pm at Sun Jun 25, 2023 10:43 pm
>
> 
masterlkm wrote: ↑Sat Jun 24, 2023 11:04 pm
if anyone knows a tool that can in fact extract fc6 files, please let me know.

FCBConverter

Thank you very much.
