## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-01T15:58:18+00:00
- Post Title: PS3 .pam video files

PAMF0041 header.

example:

```
M Д     P 0         0      Ь   Ѕ                                        А   _ђ    А   ђЋ   ]А   БЊ   ЬА   тЉ  \А2   #€  )А   T†  MАy   …„  ¶АҐ   	¶‚  ‘АЉ   
зЂ  
Аa   ~  БАR   
I|  dАT   zz  щА]   «x                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                єD Єu±Sш  » ѓ©ЃЂр№йІЅз(  ї zа         j  Ђ« Ђ Э ЂB Ђ
 Ђ… Ђ Ђ· Ђg Ђj Ђ \ Ђ я Ђ!j Ђ!э Ђ
```


files - [http://ifolder.ru/19565929](http://ifolder.ru/19565929)

Need simple converter to avi or any simple video format.
## Post #2
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-02T17:52:04+00:00
- Post Title: PS3 .pam video files

Several files for testing and analisys - [http://ifolder.ru/19578609](http://ifolder.ru/19578609)

PMF2AVI&AT3 cant work with 6 channel .pam video files.
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-03T16:12:35+00:00
- Post Title: PS3 .pam video files

So, found not bad tools for converting to .avi and .at3 - [http://ifolder.ru/19589623](http://ifolder.ru/19589623)

New problem - any video(pam or pmf) normal converted to video. But dont extract audio from Demon Souls and White Knight Chronicles.

Files for testing - [http://ifolder.ru/19589608](http://ifolder.ru/19589608)
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-06T10:40:44+00:00
- Post Title: PS3 .pam video files

Smarter way: cut the first 0x800 bytes from the *.pam, save as *.mpg and demux with TMPGEnc. 
If you don't already know: File -> MPEG Tools... -> De-Multiplex, open *.mpg, double click on the private stream under the video and save.
You can see that both Demon's Souls and White Knight Chronicles don't have AT3 as audio codec. Will check later what it is, looks somewhat familiar.
## Post #5
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-06T11:09:38+00:00
- Post Title: PS3 .pam video files

The problem is just with .pam audio extraction. If AT3 extracts, it is not retrieved until is AT3+ (Maybe). I could be wrong.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-06T15:17:52+00:00
- Post Title: PS3 .pam video files

> Reply from Researchman
>
> The problem is just with .pam audio extraction. If AT3 extracts, it is not retrieved until is AT3+ (Maybe). I could be wrong.
To be honest I don't get what you're saying.
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-06T17:35:42+00:00
- Post Title: PS3 .pam video files

Example:

Battle Fantasia - at3 audio from .pam:


Demon Souls - at3 audio from .pam:
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-07T05:47:07+00:00
- Post Title: PS3 .pam video files

No, still don't understand. You haven't even written what's on the pics. I don't know what I see here.
## Post #9
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-07T13:38:31+00:00
- Post Title: PS3 .pam video files

As I write this, a video from .PAM easy to encode to AVI. Also easy extract standart AT3, but from Battle Fantasia can possible extract .PAM AT3 Audio. Demon Souls .PAM Audio cant extract. This is shown in the pics.

Example files - [http://ifolder.ru/19655516](http://ifolder.ru/19655516)
## Post #10
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2010-10-07T19:27:19+00:00
- Post Title: PS3 .pam video files

hi, me i have make aslo with mencoder for dump video and then put in avi, but i can't dump audio with this command mplayer -dumpaudio ICON2.pmf this generating a file with 0bytes ( i tested on Quantum Theory pam video )
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-08T22:26:28+00:00
- Post Title: PS3 .pam video files

> Reply from Researchman
>
> As I write this, a video from .PAM easy to encode to AVI. Also easy extract standart AT3, but from Battle Fantasia can possible extract .PAM AT3 Audio. Demon Souls .PAM Audio cant extract. This is shown in the pics.

Example files - http://ifolder.ru/19655516
Ok, I see what you mean. These pam files don't have an at3 stream as audio, but I don't know what it is (yet). You can demultiplex all *.pmf and *.pam files with TMPGEnc by cutting out the first 0x800 bytes and saving the file as *.mpg, then use TMPGEnc's De-multiplex (in "MPEG tools..."). I'm not sure if it works the right way with *.pam files because I wasn't able to parse the audio stream from Battle Fantasia with this method. However, the mencoder version works. But I'd change to batch file to 
```
mplayer -dumpaudio -dumpfile "%~n1.at3" "%~n1.pam"
```
 and drag *.pam files into it without renaming them. It's much less work.
You could also use a loop batch like 
```
for %%i in (*.pam) DO mplayer -dumpaudio -dumpfile "%%~ni.at3" "%%i"
```
 which will decode all the pam videos in the folder you run the batch.
## Post #12
- Username: vovmen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 09, 2010 3:12 pm
- Post datetime: 2010-10-09T07:25:35+00:00
- Post Title: PS3 .pam video files

PAM (from SDK): 
Video - MPEG-2 or AVC,
Audio - atrac3, AC3 or LPCM.

PAM Video to MKV - mkvmerge (best for MPEG-2 and H.264, but need delete code before first 0x000001BA44) ......also it is possible demux after.
## Post #13
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T12:43:39+00:00
- Post Title: PS3 .pam video files

> Reply from vovmen
>
> PAM (from SDK): 
Video - MPEG-2 or AVC,
Audio - atrac3, AC3 or LPCM.
Care to get valid headers for AC3 and LPCM? Thanks.
## Post #14
- Username: vovmen
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 09, 2010 3:12 pm
- Post datetime: 2010-10-09T14:06:23+00:00
- Post Title: PS3 .pam video files

> Reply from AlphaTwentyThree
>
> vovmen wrote:PAM (from SDK): 
Video - MPEG-2 or AVC,
Audio - atrac3, AC3 or LPCM.
Care to get valid headers for AC3 and LPCM? Thanks.

Maybe it will help...
sample PAM: AVC+AT3, AVC+LPCM, MPEG-2+AC3
[http://ifolder.ru/19683867](http://ifolder.ru/19683867)
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-09T15:05:53+00:00
- Post Title: PS3 .pam video files

The files don't contain any headers, maybe you know that? But thanks, maybe I can get them elsewhere.
## Post #16
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-09T18:04:40+00:00
- Post Title: Re: PS3 .pam video files

Sound samples - [http://ifolder.ru/19687100](http://ifolder.ru/19687100)
## Post #17
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2010-10-17T23:25:11+00:00
- Post Title: Re: PS3 .pam video files

Why any of the links don't let dl or even show captcha for dling?  Only in google translator I get captcha and dl button, not on ie, not firefox, wtf?

EDIT:  I had to use JDownloader for them.  In any case that pam pmf converter is unable to extract, rip or/and demux at3 simple and at3plus files.
## Post #18
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2011-03-15T17:58:21+00:00
- Post Title: Re: PS3 .pam video files

Extracted all your files and muxed into normal MKV, hope you like it.

I also left some files as I get them after extraction so you can test for yourself.

[PAM Files](http://www.fileserve.com/file/TPnuksU)

[AT3/AT3+ from PAM](http://www.fileserve.com/file/J3XzdZ7)

A admin can close the topic since the request was fulfilled.
## Post #19
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:33:30+00:00
- Post Title: Re: PS3 .pam video files

Thanks
## Post #20
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2011-08-13T16:25:26+00:00
- Post Title: Re: PS3 .pam video files

> Reply from Skyknight
>
> A admin can close the topic since the request was fulfilled.This is not solved at all, as they say : "Give a man a fish and you feed him for a day. Teach a man to fish and you feed him for a lifetime."
I see you successfully converted sound from Demon's Soul intro wav, fine, good for you, but how the hell did you accomplish that ? I'd really love to know... since I can't !

I extracted "private stream" with TMPGEnc out of the PAM file (since mplayer can't dump anything, contrary to what AlphaTwentyThree said), tried to convert the resulting .dat file into aa3 with different QuickBMS scripts including AlphaTwentyThree's (adding different -aa3 and/or at3- headers just in case, again with the help of AlphaTwentyThree's scripts...), but all I get is a damn blank aa3 audio file in Soundforge... 

(I went to your irc channel and politely asked the very same question... apparently people are... not too helpful... and I mean, really... but oh well, I just left silently...)

> Reply from AlphaTwentyThree
>
> You can see that both Demon's Souls and White Knight Chronicles don't have AT3 as audio codec. Will check later what it is, looks somewhat familiar.Interesting, what is it then if it's not at3 ?
## Post #21
- Username: Boulotaur2024
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Apr 04, 2011 1:12 am
- Post datetime: 2011-08-14T13:43:51+00:00
- Post Title: Re: PS3 .pam video files

Case solved (at least for Demon's Souls) !

I managed to convert every audio file to PCM using VGMToolbox.
Open VGMToolbox, go to Misc. Tools -> Stream Tools -> Video Demultiplexer



Select 'PAM' format in the listbox, then drag & drop your .PAM file onto the window...
Import the resulting .lpcm file with Audacity (File -> Import -> Raw Data).
You can leave the default import settings for all the .lpcm file except for ds_advertise_400001BD.lpcm, since it's a 6 channels 48Khz file.

Voila 

PS : a huge thank you to people who actually release *FREE* tools, not some cheezy win3.1 looking VB apps for 50$ (if you see what I mean...)
## Post #22
- Username: hirocon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 24, 2011 9:54 am
- Post datetime: 2011-11-25T05:54:40+00:00
- Post Title: Re: PS3 .pam video files

I can't download the PAM converter. the language I can't understand
please eveyone.help me to convert PAM files of PS3 game "二の国(ninokuri)"!thank you!the new game just purchased three days ago.
## Post #23
- Username: hirocon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 24, 2011 9:54 am
- Post datetime: 2011-11-25T06:12:45+00:00
- Post Title: Re: PS3 .pam video files

the game, ninokunieva, 0010.pam~evn0200.pam is no audios. but I think they hidden in that.but how to extract the audio?
s01~14 I can extract audio.It's aa3.
## Post #24
- Username: hirocon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 24, 2011 9:54 am
- Post datetime: 2011-11-25T06:18:12+00:00
- Post Title: Re: PS3 .pam video files

PS3 game "二の国(ninokuri)"!- data - 5 sdat in that.
but use vgmtoolbox_bin_r846 I can't get anything.
sdat,adat is NDS's code!
## Post #25
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-11-25T13:14:21+00:00
- Post Title: Re: PS3 .pam video files

sdat is encrypted archive it must be decrypted first.
## Post #26
- Username: Skyknight
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 23, 2010 1:26 am
- Post datetime: 2012-12-21T01:33:02+00:00
- Post Title: Re: PS3 .pam video files

Luckily you came up with a good solution Boulotaur2024    I've been working in some stuff so I couldn't get to answer a long time ago, a really long time actually but I'm back more or less
## Post #27
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-10T11:14:05+00:00
- Post Title: Re: PS3 .pam video files

The pam video player works wonderfully no need to extract or edit anything.
## Post #28
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-10T17:01:53+00:00
- Post Title: Re: PS3 .pam video files

Could be possible a link to download?
## Post #29
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-05-11T05:30:18+00:00
- Post Title: Re: PS3 .pam video files

> Reply from Researchman
>
> Could be possible a link to download?
yeah check pm comes with the video editor too
## Post #30
- Username: mono24
- Rank: veteran
- Number of posts: 133
- Joined date: Thu Apr 03, 2014 4:49 pm
- Post datetime: 2014-05-13T20:26:42+00:00
- Post Title: Re: PS3 .pam video files

> Reply from cra0
>
> Researchman wrote:Could be possible a link to download?
yeah check pm comes with the video editor too
*ahem*

Just wanted to point out I found that. hehe.

I just need my daily dose of credits that's all
## Post #31
- Username: bekar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 23, 2012 8:31 pm
- Post datetime: 2014-12-15T14:22:34+00:00
- Post Title: Re: PS3 .pam video files

> Reply from cra0
>
> The pam video player works wonderfully no need to extract or edit anything.
plaeas link to download
## Post #32
- Username: jackskellinghog
- Rank: beginner
- Number of posts: 25
- Joined date: Sun Mar 11, 2012 11:08 am
- Post datetime: 2015-03-31T16:31:33+00:00
- Post Title: Re: PS3 .pam video files

Could someone pm me the download link for the ps3 pam viewer/re-encoder please
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-04-02T02:10:40+00:00
- Post Title: Re: PS3 .pam video files

You might be able to find something in this thread that'll help with that.
[http://www.ps3hax.net/showthread.php?t=33779](http://www.ps3hax.net/showthread.php?t=33779)
## Post #34
- Username: mysis
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Aug 14, 2014 6:45 pm
- Post datetime: 2015-04-06T14:50:33+00:00
- Post Title: Re: PS3 .pam video files

Hi,

just recently i am able to convert .pam -> .mp4, any ps3 pam no matter its audio codec.

its possible because the ps3 sdk has code for a transcoder which basically is a sample for converting ps3 supported movie files on ps3 via ps3.

i had to modify the code a little bit, but successfully converted the Kingdom Hearts 358/2 Days Opening and without quality loss (quality can be changed too)

Cant make the self file public because its 99% sony code but its inside sdk so everyone who got a hold of it can compile it himself and run it on his ps3.
## Post #35
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2015-04-07T12:14:27+00:00
- Post Title: Re: PS3 .pam video files

> Cant make the self file public because its 99% sony code but its inside sdk so everyone who got a hold of it can compile it himself and run it on his ps3.
Thanks for info, but it will be useful for coders and other who understand coding and programming.

But if possible to get your converter for personal use only through PM, its will be fine.
## Post #36
- Username: akramserry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 06, 2019 8:43 pm
- Post datetime: 2019-02-06T12:47:17+00:00
- Post Title: Re: PS3 .pam video files

can someone please send me download link for the ps3 pam viewer and composer
or tell me how to rencode pam files
also if there is a bik remuxer it would be wonderfull
thanks in advance
## Post #37
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-02-09T02:29:26+00:00
- Post Title: Re: PS3 .pam video files

> Reply from akramserry
>
> can someone please send me download link for the ps3 pam viewer and composer
The only way is t use Sony's legit software PAMF Tools and that in this forum is a big NO NO, highly illegal, plus Google will provide all the link you need once you search for it.
As for bik, there is VGMToolbox de-muxer, and also you need to use RADTools for encoding, but as for re-muxing back to bik, not sure one even exists.
## Post #38
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-12T12:32:03+00:00
- Post Title: Re: PS3 .pam video files

Hello everybody! I have a problem with extracting video and audio files from pam video files, usually it works fine with vgmtoolbox, but its showing that it doesnt have a header. Pam files are from Street Fighter 4 Vanilla Version which came out in 2008, I have uploaded a bunch of them here:
[https://mega.nz/folder/1jBwQT5I#6shT7sqoAZrVmKNmDL8b2g](https://mega.nz/folder/1jBwQT5I#6shT7sqoAZrVmKNmDL8b2g)
I want to extract them after mux them with MKV muxer to be able to play them at highest possible bitrate, which is about 20mbps (don't want to convert video files, cuz it will lose some quality).
## Post #39
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-12T21:05:52+00:00
- Post Title: Re: PS3 .pam video files

> Reply from arsijin ↑Fri Mar 12, 2021 8:32 pm at Fri Mar 12, 2021 8:32 pm
>
> ...I have a problem with extracting video and audio files from pam video files... ...but its showing that it doesnt have a header...
That's because those files are fully encrypted .SDAT videos, made with Sony's PAMF proprietary encoder then encrypted, they are Sony digital retail PKG files, not disc, you'll have to decrypt them back to .DAT first, using the .RAP key of the PKG, then you'll be able to demux them using vgmtoolbox, i tested couple of your samples and they demux and play just fine
## Post #40
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-12T23:34:40+00:00
- Post Title: Re: PS3 .pam video files

thx mono24, I really appreciate the reply and I'm so happy that they are demuxable, the thing is I'm a noob around here, is there any way that you can teach me or help me about it? cuz to me these things are very new)) I would really appreciate it
## Post #41
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-13T08:26:18+00:00
- Post Title: Re: PS3 .pam video files

> Reply from arsijin ↑Sat Mar 13, 2021 7:34 am at Sat Mar 13, 2021 7:34 am
>
> ...is there any way that you can teach me or help me about it?...
I have no clue what/how/where you got your PKG, but you should be able to decrypt the files using TrueAncestor EDAT Rebuilder in order to demux everything using the PKGs RAP decryption key.
Once you'll get tool mentioned you'll see folders in which to place the required files, before running the executable.
Your encrypted files should be named .SDAT, placed in the appropriate folder, the same for the RAP key, then you'll get decrypted .DAT files which then you can demux.
## Post #42
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-13T09:44:45+00:00
- Post Title: Re: PS3 .pam video files

> Reply from mono24 ↑Sat Mar 13, 2021 4:26 pm at Sat Mar 13, 2021 4:26 pm
>
> 
arsijin wrote: ↑Sat Mar 13, 2021 7:34 am...is there any way that you can teach me or help me about it?...
I have no clue what/how/where you got your PKG, but you should be able to decrypt the files using TrueAncestor EDAT Rebuilder in order to demux everything using the PKGs RAP decryption key.
Once you'll get tool mentioned you'll see folders in which to place the required files, before running the executable.
Your encrypted files should be named .SDAT, placed in the appropriate folder, the same for the RAP key, then you'll get decrypted .DAT files which then you can demux.
Thx again for the reply, I got the tool TrueAncestor EDAT Rebuilder, I've renamed my Pam files to sdat and put them in sdat folder, chose to decrypt sdat files, then the tool located sdat renamed files, I chose to decrypt all sdat files and it didn't work, certainly I'm doing something wrong, plz educate me furhter 
[](https://imageban.ru)

[](https://imageban.ru)
and I diidnt get about 
PKGs RAP decryption key
Rap key
## Post #43
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-13T16:13:34+00:00
- Post Title: Re: PS3 .pam video files

> Reply from arsijin ↑Sat Mar 13, 2021 5:44 pm at Sat Mar 13, 2021 5:44 pm
>
> and I diidnt get about 
PKGs RAP decryption key
Rap key
You forgot to put the RAP key in the raps folder, from where ever you got the PKG you must download the retail RAP key as well, with out it you will never be able to decrypt anything as its specific to that PKG and its assets.
## Post #44
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-13T16:26:58+00:00
- Post Title: Re: PS3 .pam video files

> Reply from mono24 ↑Sat Mar 13, 2021 5:05 am at Sat Mar 13, 2021 5:05 am
>
> 
i tested couple of your samples and they demux and play just finesorry, I've got that pkg long time ago, and it seems I will never find it or make it, is there any way that you could help me?
## Post #45
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-13T16:35:50+00:00
- Post Title: Re: PS3 .pam video files

> Reply from arsijin ↑Sun Mar 14, 2021 12:26 am at Sun Mar 14, 2021 12:26 am
>
> ...is there any way that you could help me?
Then you'll need to get the key yourself using psnstuff v03.07.09 by slimshady451, and its database.
If you google it, mediafire links are still available for both of them.

edit: ...
## Post #46
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-13T17:06:42+00:00
- Post Title: Re: PS3 .pam video files

mono24 thanx for everything, FINALLY I could decrypt them, my problem was with outdated java))
## Post #47
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-03-13T17:27:07+00:00
- Post Title: Re: PS3 .pam video files

Go back to the last post i edited.
## Post #48
- Username: arsijin
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 02, 2015 6:35 pm
- Post datetime: 2021-03-13T17:32:25+00:00
- Post Title: Re: PS3 .pam video files

mono24, I have figured it out with your help, big problem was my outdated java.
