## Post #1
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-10-09T06:37:41+00:00
- Post Title: Dark Souls 2 file formats

I'd like to get a head start on the dark souls 2 file formats, so I can hopefully have some support for it in DSMODT when Dark Souls 2 is released in March, or shortly thereafter~

So I've gotten into the network test, and am downloading the client right now-- however, I haven't a clue on how to get these files off of my PS3 (and I'm fairly confident I don't have the hardware for it anyways >_<) so in addition to using this thread to discuss these formats, I'd also like to hear from some of the others who are in the network test, about getting some files to work with.

I can't wait to work with the dark souls 2 files! ^_^
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2013-10-11T10:00:12+00:00
- Post Title: Dark Souls 2 file formats

To answer your question,
Get some sort of way to log your PS3 network activity.
Start (or unpause) the client download.
Sniff the URL it grabs for the install package.
Unpack that package for game data using PS3 package unpacking tools.

As for formats, mostly the same as Dark Souls. At least the archives, not looked at models.
## Post #3
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2013-10-11T12:44:15+00:00
- Post Title: Dark Souls 2 file formats

Hey Rick, thanks for the reply~

I actually managed to get the package onto my computer thanks to somebody else who suggested pretty much exactly the same thing- and have discovered the same thing as you regarding formats. Some minor shuffling of values here and there, but the archives are pretty much the same.

I'd actually wanted to wait until I had some screenshots of models (hopefully in a few days!) before I posted again, but didn't want to put off thanking you for sharing the info~
## Post #4
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-24T16:04:37+00:00
- Post Title: Dark Souls 2 file formats

A lot of the models extracted using the old Dark Souls 1 script method.  Some of the new models have a different amount of parts entries than mesh entries.

[](http://www.imagebam.com/image/35dae3322627106) [](http://www.imagebam.com/image/f23ab6322627122) 

[](http://www.imagebam.com/image/7b248c322627134) [](http://www.imagebam.com/image/8c3cbc322627162) 

[](http://www.imagebam.com/image/f88789322627183) [](http://www.imagebam.com/image/2f5b49322627212)
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-24T17:40:56+00:00
- Post Title: Dark Souls 2 file formats

Could you try my apha script with models which aren't working? It's "raw" and unfinished but I want to know will it work or not. Thanks
[DS_2_PC.7z](https://xentaxbackup.github.io/file/7253_DS_2_PC.7z)
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-25T06:18:29+00:00
- Post Title: Dark Souls 2 file formats

So guys, 6 downloads - any one could report about Dark Souls  2 models? I tried script with Dark Souls 1 models nicely (I have the game), but didn't have much of DS 2 models.
## Post #7
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-25T14:48:01+00:00
- Post Title: Dark Souls 2 file formats

> Reply from zaramot
>
> So guys, 6 downloads - any one could report about Dark Souls  2 models? I tried script with Dark Souls 1 models nicely (I have the game), but didn't have much of DS 2 models.

I tried your script on the Dark Souls 2 Xbox360 .flver files, but they didn't load.  I'll try some more tests later today.

After further testing, I changed readshort, readlong, and readfloat to readBEshort, readBElong, and readBEfloat, and the Xbox360 models are loading.
I also had to comment out a part of the bone reading, but it may also have to do with the console version of the files.

Testing on more models currently.

A lot of the models are loading with just those changed.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-25T16:06:30+00:00
- Post Title: Dark Souls 2 file formats

Ah, it's for PC version for Xbox-360 use this one

EDIT: Updated Xbox-360 script a bit
[Dark_Souls_2.7z](https://xentaxbackup.github.io/file/7259_Dark_Souls_2.7z)
## Post #9
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-25T16:28:00+00:00
- Post Title: Dark Souls 2 file formats

> Reply from zaramot
>
> Ah, it's for PC version for Xbox-360 use this one

It works great.  Will test on more models later.
## Post #10
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-04-25T16:31:19+00:00
- Post Title: Dark Souls 2 file formats

> Reply from zaramot
>
> Ah, it's for PC version for Xbox-360 use this one

Hi Would you be so kind and help with localization of DS2 for X360 and PC ?
## Post #11
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-04-25T17:13:59+00:00
- Post Title: Dark Souls 2 file formats

The c1000 model is loading a little different between the converted pc script, and the xbox360 script.

The model on the left is the pc script with reversed endianness and bone node info commented out, and the model on the right is the untouched xbox360 script.
I had to move the uvs' around and scale them to get to line up, what I did in the other screen shots was:

```
tu = (tu * (8192));
tv = (tv * (8192));

//Flipping
tv = ((tv * (-1)) + 1);

```

[](http://www.imagebam.com/image/4f8e09322804838) [](http://www.imagebam.com/image/1a07c1322816438)
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-04-25T18:36:23+00:00
- Post Title: Dark Souls 2 file formats

Cool! Thanks for all the testing, I guess I should download Xbox-360 or PC version of Dark Souls 2, or if script will fail for some models, you can upload them and send me via PM?
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-04-26T09:29:52+00:00
- Post Title: Dark Souls 2 file formats

Can anyone please write bms script for GameData1.bdt and GameData1.bhd(index) files ?
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-01T07:33:57+00:00
- Post Title: Dark Souls 2 file formats

> Reply from michalss
>
> Can anyone please write bms script for GameData1.bdt and GameData1.bhd(index) files ?
What the problems? Use try use [Rick tools](http://svn.gib.me/public/darksouls/trunk/)
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-01T17:39:40+00:00
- Post Title: Dark Souls 2 file formats

> Reply from Ekey
>
> michalss wrote:Can anyone please write bms script for GameData1.bdt and GameData1.bhd(index) files ?
What the problems? Use try use Rick tools

Can unpack only, but not repack also does not work for X360 , also no support for GameData1.bdt and bhd  also there are text files as container i dont know structure
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-01T19:21:16+00:00
- Post Title: Re: Dark Souls 2 file formats

Can you share small packs from xbox / pc?
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-02T05:15:27+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Ekey
>
> Can you share small packs from xbox / pc?

Sure Ekey  Thx for help.... It is over 2GB of size, do you want complete archives ?
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-02T07:51:27+00:00
- Post Title: Re: Dark Souls 2 file formats

Oh lol. Seems better to download the full game
## Post #19
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-03T20:24:52+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Ekey
>
> Oh lol. Seems better to download the full game

I have sent you all files 

BTW extract/repack of bhd file is possible for me now  but texts giving me hard time
## Post #20
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-09T16:09:11+00:00
- Post Title: Re: Dark Souls 2 file formats

Is it possible to extract  PC bhd/bdt files? Rick's tools crash.
## Post #21
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2014-05-09T19:31:05+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from erik945
>
> Is it possible to extract  PC bhd/bdt files? Rick's tools crash.PC archives have both encrypted headers and encrypted files within its data.

Due to the newness of the game and the fact that multiplayer is central to the game, I will not be providing any of my personal research for Dark Souls II publicly (nor will I provide it privately). Cheating was a big problem with the first game, and while there is cheating in Dark Souls II, I am not going to help it get worse for the time being.
## Post #22
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2014-05-09T20:18:36+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Rick
>
> erik945 wrote:Is it possible to extract  PC bhd/bdt files? Rick's tools crash.PC archives have both encrypted headers and encrypted files within its data.

Due to the newness of the game and the fact that multiplayer is central to the game, I will not be providing any of my personal research for Dark Souls II publicly (nor will I provide it privately). Cheating was a big problem with the first game, and while there is cheating in Dark Souls II, I am not going to help it get worse for the time being.

Im with you in this, but Rick can you please at least help me with localization files for X360, its giving me hard time .... Archives for X360 is pretty easy, i actually planning to localize this game for consoles only. However loc files are kind of strange .... Our community never cheating just care of translations to our language...

Thx
## Post #23
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2014-05-09T20:30:49+00:00
- Post Title: Re: Dark Souls 2 file formats

Ok, no problem, thank you!
PS or Xbox have a better textures?
## Post #24
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-05-12T07:03:23+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Rick
>
> erik945 wrote:Is it possible to extract  PC bhd/bdt files? Rick's tools crash.PC archives have both encrypted headers and encrypted files within its data.

Due to the newness of the game and the fact that multiplayer is central to the game, I will not be providing any of my personal research for Dark Souls II publicly (nor will I provide it privately). Cheating was a big problem with the first game, and while there is cheating in Dark Souls II, I am not going to help it get worse for the time being.

Understandable, I'd really like to access the game files but I do understand not wanting to make cheating/hacking easier than it already is since the game is very focused on online play, hopefully something can be released later. 
(I prefer offline mode myself but I've never really liked multiplayer that much.)
## Post #25
- Username: Swennet
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 22, 2013 4:50 am
- Post datetime: 2014-05-23T18:13:22+00:00
- Post Title: Re: Dark Souls 2 file formats

I would really like to access the audio files of Dark Souls 2. Is it possible to extract these from any version of the game? (PC, PS3, X360) Would save me a lot of trouble!
## Post #26
- Username: hellkitedrake
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 31, 2014 8:03 pm
- Post datetime: 2014-06-20T00:17:20+00:00
- Post Title: Re: Dark Souls 2 file formats

-
## Post #27
- Username: XiNAVRO
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 1:39 am
- Post datetime: 2014-07-17T03:08:48+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Rick
>
> PC archives have both encrypted headers and encrypted files within its data.

Due to the newness of the game and the fact that multiplayer is central to the game, I will not be providing any of my personal research for Dark Souls II publicly (nor will I provide it privately). Cheating was a big problem with the first game, and while there is cheating in Dark Souls II, I am not going to help it get worse for the time being.
Bummer. I completely understand and agree on your decision - however, as a person who is looking into Dark Souls files to grab the armors and weapons for other games (namely Skyrim) it' is a shame that I cannot extract the files without using GeDoSaTo and Ninja Ripper.
## Post #28
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-26T09:47:44+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Ekey
>
> michalss wrote:Can anyone please write bms script for GameData1.bdt and GameData1.bhd(index) files ?
What the problems? Use try use Rick toolsHello my friend, can you write a tutorial for this tool very thank
## Post #29
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-08-05T15:04:57+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from zaramot
>
> Ah, it's for PC version for Xbox-360 use this one

EDIT: Updated Xbox-360 script a bitHello my friend, I extract the Dark Souls 2 Xbox file, you do not see *.flver, how do I import model, thank you for your help
## Post #30
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-08-05T17:19:33+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from Rick
>
> To answer your question,
Get some sort of way to log your PS3 network activity.
Start (or unpause) the client download.
Sniff the URL it grabs for the install package.
Unpack that package for game data using PS3 package unpacking tools.

As for formats, mostly the same as . At least the archives, not looked at models.Hello my friend, I have tried to extract Dark Souls 2 bnd file with your script, but failed. Can teach us how to modify the script so that the script can be applied to Dark Souls 2 , I want to extract to flver file. Thank you for your help
## Post #31
- Username: vit3z
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 28, 2014 7:14 pm
- Post datetime: 2014-08-28T11:23:05+00:00
- Post Title: Re: Dark Souls 2 file formats

Hello guys, since I can't extract the DS2 files, and I'm really looking for one model in particular for now. 
I know it's kinda weird can someone please send me the Ancient Dragon model, I've tried using Ninja Ripper to get it, but it doesn't work. For some reason. Worked for Skyrim...
## Post #32
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-08-13T10:55:46+00:00
- Post Title: Re: Dark Souls 2 file formats

I try to resurrect this thread. there is a way to open the archives file dark souls 2 on pc?
## Post #33
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-08-15T11:51:24+00:00
- Post Title: Re: Dark Souls 2 file formats

Very unlikely in near future, there are reasons for that. But you can extract Xbox-360 files
## Post #34
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-08-15T19:53:08+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from zaramot
>
> Very unlikely in near future, there are reasons for that. But you can extract Xbox-360 files

as you say? I tried but all are in another format!
## Post #35
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-02T13:29:56+00:00
- Post Title: Re: Dark Souls 2 file formats

please I ask you on my knees, how do you open the archives of dark soul file.bdt 2 ????
## Post #36
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-02T18:33:16+00:00
- Post Title: Re: Dark Souls 2 file formats

Well, no need to falling on your knees. You have xbox-360 version? You should run offzip on files
## Post #37
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T06:13:33+00:00
- Post Title: Re: Dark Souls 2 file formats

ok I could do it, but I can not find the file flver! what can I do?
## Post #38
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-09-03T10:19:16+00:00
- Post Title: Re: Dark Souls 2 file formats

Dark Souls II bdt, bnd and dcx unpacking tool - [https://github.com/Atvaark/BinderTool](https://github.com/Atvaark/BinderTool)
## Post #39
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T10:45:05+00:00
- Post Title: Re: Dark Souls 2 file formats

I already tried this tools but do not know how it works!
## Post #40
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-03T11:31:09+00:00
- Post Title: Re: Dark Souls 2 file formats

You're getting files with .dat extension? Somewhere in this thread I posted script for Xbox-360 version models, this script is for .dat files - but you can edit some line and rename .dat to .flver if you want. Pick a character or armor - use offzip on it and post this file here. It was quite a long time ago, so I forgot what there in Dark Souls II xD
## Post #41
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T12:21:23+00:00
- Post Title: Re: Dark Souls 2 file formats

then I do not know how to use well offzip, I tried it and I found these types of files. file.bnd, .dat, .fss, .nvg, .tpf, .waaw and flv_file. Your script zaramot law already files flver.

edit: zaramot I made an amazing discovery! your first script dark souls 2 is able to import models with the skeleton of the first !!!!!! Now you just have to fix the skeleton because it makes errors: /
## Post #42
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-09-03T15:35:52+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from dibe91
>
> I already tried this tools but do not know how it works!
Before use you need to compile this source code. Anyway, i hope that Atvaark not against if I share compiled version here?

Download: [here](https://www.sendspace.com/file/375y7z)

```
  BinderTool file_path [output_path]
```


Open BinderTool.bat and add path's for input file and output directory

Example:

```
BinderTool "E:\Games\Dark Souls II\GameDataEbl.bdt"
```


Or if you want to unpack to specified folder

Example:

```
BinderTool "E:\Games\Dark Souls II\GameDataEbl.bdt" "E:\My unpacked files\GameDataEbl"
```


Save BAT, Close BAT, Run BAT = Profit.
## Post #43
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-03T17:49:16+00:00
- Post Title: Re: Dark Souls 2 file formats

Ekey thank you! I had the exe file but it's alright! zaramot files models are in another form. are formatted files flv_file.
## Post #44
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-09-06T06:56:09+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from zaramot
>
> Could you try my apha script with models which aren't working? It's "raw" and unfinished but I want to know will it work or not. Thanks

I tried to edit your first script Dark Soul 2 and I can confirm that the matter be models of Dark Soul 2 that those of Dark Souls. the problem is that the skeletons are not correct! the bones are out of the model, and there is also the usual mistake that bone right moves the mesh left and vice versa.
## Post #45
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-06T15:17:52+00:00
- Post Title: Re: Dark Souls 2 file formats

Yeah, I know about skeleton issues. As for wrong weights (left arm bones moving right arm of geometry), don't know which script you edited, I have other which doesn't have this problem. I abandoned Dark Souls 1/2 reversing due to poor models and textures quality, I don't like them - there are a lot better 3d models IMHO
## Post #46
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-11-16T20:57:22+00:00
- Post Title: Re: Dark Souls 2 file formats

Hey there guys!

I'm resurrecting this thread, because I'd like to translate the game on PC. Can anyone help me with the fmg files (can't decrypt them, but there are some where I can see text), and how I could import them back in?
## Post #47
- Username: Imamonke
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 03, 2016 5:45 pm
- Post datetime: 2016-01-03T09:50:45+00:00
- Post Title: Re: Dark Souls 2 file formats

I don't suppose there's a way for someone without a xbox copy of DS 2 to get their hands on the models/textures/maps? I've been itching to make some animations with them, but I've come up at dead-ends no matter where I look.
## Post #48
- Username: hoang vinh
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Nov 22, 2015 3:54 pm
- Post datetime: 2016-01-03T10:57:57+00:00
- Post Title: Re: Dark Souls 2 file formats

> Reply from TheReaperCooL
>
> Hey there guys!

I'm resurrecting this thread, because I'd like to translate the game on PC. Can anyone help me with the fmg files (can't decrypt them, but there are some where I can see text), and how I could import them back in?

You can read this topic : [http://zenhax.com/viewtopic.php?f=12&t=1933](http://zenhax.com/viewtopic.php?f=12&t=1933)
## Post #49
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-10T18:16:24+00:00
- Post Title: Re: Dark Souls 2 file formats

Hey, do someone have Fume Knight model? I found only textures,but no .flv mesh
I unpack all alot files, try to search by number, but still no found.
## Post #50
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2019-10-18T05:17:53+00:00
- Post Title: Re: Dark Souls 2 file formats

Bit of a necro, but I feel this is relevant to this thread, I've been trying to track down DS2 player animations for a while assuming they were .hkx like the other games in the series but as it turns out, that's not the case
They are in .nsa format  
afaik no one's looked into this format so I wonder if anyone would be interested in taking a look at them and figure out what's going on here. .hkx is used in other places, just not characters and unlike 1 and 3 there's no .anibnd with all the .hkx files ready to import into Max.
## Post #51
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-06-13T15:39:35+00:00
- Post Title: Re: Dark Souls 2 file formats

Hi!
Does anyone have tne numbers of armor sets from dark souls 2?

I try to find some, but it take alot times in 3ds max to import any mesh
