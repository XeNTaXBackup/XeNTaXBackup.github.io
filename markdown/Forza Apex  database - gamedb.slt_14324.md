## Post #1
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-09T20:32:52+00:00
- Post Title: Forza Apex  database - gamedb.slt

Hi,

I have problems with reading new gamedb.slt from latest forza.
I was always using that [http://sqlitebrowser.org/](http://sqlitebrowser.org/) program for get cars specs, torque curves and many more etc.

Can somebody help me with opening the new slt file please?

This doesn't work
Forza Apex
[http://www80.zippyshare.com/v/5z3vbkjk/file.html](http://www80.zippyshare.com/v/5z3vbkjk/file.html)

This works
Forza Horizon 2 (Fast7 DLC)
[http://www80.zippyshare.com/v/1tNEd1Vy/file.html](http://www80.zippyshare.com/v/1tNEd1Vy/file.html)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-09T21:41:13+00:00
- Post Title: Forza Apex  database - gamedb.slt

> Reply from TomWin
>
> This doesn't work
Forza Apexinvalid file format: look into the file - might be compressed.

> This works
>
> Forza Horizon 2 (Fast7 DLC)Because it starts with "SQLite format 3".
## Post #3
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-11T16:15:23+00:00
- Post Title: Forza Apex  database - gamedb.slt

How to uncompress that? I have no idea of programing
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-11T20:29:51+00:00
- Post Title: Forza Apex  database - gamedb.slt

offzip doesn't find any valid zip data

you might try a comtype scan using quickbms:
[viewtopic.php?f=16&t=13222&p=108886&hil ... an#p108886](http://forum.xentax.com/viewtopic.php?f=16&t=13222&p=108886&hilit=comtype_scan#p108886)
## Post #5
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-12T14:41:30+00:00
- Post Title: Forza Apex  database - gamedb.slt

No it doesn't work
## Post #6
- Username: TheAdmiester
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jan 04, 2017 5:04 am
- Post datetime: 2017-01-03T21:07:07+00:00
- Post Title: Forza Apex  database - gamedb.slt

Hey, bumping this thread.

Forza Horizon 3 (which has mostly the same cars as Forza Apex) has an encrypted gamedb file (known as gamedbrc.slt). Turn10/PG had a massive cock-up today and released a dev build of the game -which happens to include an unencrypted gamedbrc.slt.

Here's the file, it can be opened in SQLite3/DBBrowser: [http://www22.zippyshare.com/v/XxS52znS/file.html](http://www22.zippyshare.com/v/XxS52znS/file.html)

Proof:


If anyone needs any other files from this opened build, let me know.
## Post #7
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2017-01-05T22:59:16+00:00
- Post Title: Forza Apex  database - gamedb.slt

thing is,and I am surprised no one has posted about this yet in this thread at least,playground games had a massive oops moment and accidently uploaded forza Horizon 3 v.37.2 DEV BUILD. not even joking. but only for the pc users. (it's since been replaced so don't try to download it off the MS store it's not there anymore) not only did it give everyone who got it full access to FH3 debug options and a full list of all the planned cars coming to the game but the files themselves were completely decrypted! again not a joke I've seen it myself I just sadly wasn't there to grab the accidental build this tuesday as I had to remove the game off my system for space for other projects. duh!

 but if anyone still has the build (and redditors are posting screens of the files and some of the unreleased cars IN GAME. then you have a fully decryted FH3 archive that this forum could really use to help us make the tools to access the games files. there are so many cars and the levels themselves are something I so want to work with for a variety of reasons.

 I am not bumping this just because. for I doubt that this version of the game is just isolated to those who kept the dev build and didn't update. someone somewhere has to have it uploaded for anyone to grab. I don't know this for sure but I am pretty sure I'd have at least grabbed the unencrypted archive files and mediafired them for this forum if nothing else.
for more info and to maybe start the hunting here is an article showing the unencrypted file system and such: [https://www.gtplanet.net/the-forza-hori ... -917-more/](https://www.gtplanet.net/the-forza-horizon-3-leaks-continue-lola-t70-honda-s800-porsche-917-more/) [https://ar12gaming.com/articles/forza-h ... sche-files](https://ar12gaming.com/articles/forza-horizon-3-porsche-files)

 for you porche lovers out there you may see that we'll be getting porsche cars in FH3 as EA's contract or need for speed was for last year. anyways happy hunting.
## Post #8
- Username: TheAdmiester
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jan 04, 2017 5:04 am
- Post datetime: 2017-01-06T05:02:45+00:00
- Post Title: Forza Apex  database - gamedb.slt

> Reply from octaviousrex
>
> thing is,and I am surprised no one has posted about this yet in this thread at least,playground games had a massive oops moment and accidently uploaded forza Horizon 3 v.37.2 DEV BUILD. not even joking. but only for the pc users. (it's since been replaced so don't try to download it off the MS store it's not there anymore) not only did it give everyone who got it full access to FH3 debug options and a full list of all the planned cars coming to the game but the files themselves were completely decrypted! again not a joke I've seen it myself I just sadly wasn't there to grab the accidental build this tuesday as I had to remove the game off my system for space for other projects. duh!

 but if anyone still has the build (and redditors are posting screens of the files and some of the unreleased cars IN GAME. then you have a fully decryted FH3 archive that this forum could really use to help us make the tools to access the games files. there are so many cars and the levels themselves are something I so want to work with for a variety of reasons.

 I am not bumping this just because. for I doubt that this version of the game is just isolated to those who kept the dev build and didn't update. someone somewhere has to have it uploaded for anyone to grab. I don't know this for sure but I am pretty sure I'd have at least grabbed the unencrypted archive files and mediafired them for this forum if nothing else.
for more info and to maybe start the hunting here is an article showing the unencrypted file system and such: https://www.gtplanet.net/the-forza-hori ... -917-more/ https://ar12gaming.com/articles/forza-h ... sche-files

 for you porche lovers out there you may see that we'll be getting porsche cars in FH3 as EA's contract or need for speed was for last year. anyways happy hunting.

I'm one of the people who has the build (and quite possibly the ONLY person who has dumped a decrypted/unprotected copy), what files do you need?
## Post #9
- Username: TheAdmiester
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jan 04, 2017 5:04 am
- Post datetime: 2017-03-05T22:46:38+00:00
- Post Title: Forza Apex  database - gamedb.slt

Hey, just bumping because I'd appreciate some help.

Soon enough Forza's DLC is going to include cars that don't have any row in the unencrypted leaked database file. Is it possible for someone to investigate how to open and/or dump this database file?

[http://www62.zippyshare.com/v/b9FmbsCZ/file.html](http://www62.zippyshare.com/v/b9FmbsCZ/file.html)

It has no SQLite 3 headers like the unencrypted verison, and the data within (in HxD) is garbled whereas the leaked version shows table names and so on. I know the game executes certain SQL queries while it's running to select cars/parts and so on, so it might be possible to hijack one of those queries with a debugger to try and dump the database, but that would be a last resort IMO, and a lot more complex.
## Post #10
- Username: volvorwd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 03, 2017 5:44 am
- Post datetime: 2017-03-06T15:37:37+00:00
- Post Title: Forza Apex  database - gamedb.slt

> Reply from TheAdmiester
>
>  I'm one of the people who has the build (and quite possibly the ONLY person who has dumped a decrypted/unprotected copy), what files do you need?

Is there a way i could possibly get a copy of all of it or atleast eveything to deal w the car models & there textures? looking for materialbin so i can get the rest of the textures for the car models.
## Post #11
- Username: TheAdmiester
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jan 04, 2017 5:04 am
- Post datetime: 2017-03-07T20:12:19+00:00
- Post Title: Forza Apex  database - gamedb.slt

I've done some digging in the game's .exes and I've found the following stuff mentioned:

- TransformIT (encryption maybe?)
- Microsoft's Crypto libraries such as bcrypt.dll
- RSA 1024 "Client" and "Server" and "Private" keys
- "gamedb_obfusctationseed"
- "gamedb_encryptionkey"


But I don't know where to go to find any of these variables. I'd REALLY appreciate some help trying to open these new databases.
## Post #12
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-15T03:22:25+00:00
- Post Title: Forza Apex  database - gamedb.slt

I've successfully decrypted gamedb.slt file from the latest version of every Forza game from FM6: Apex to FH5. I don't know what encryption method it uses. I just changed some registers at runtime using x64dbg to extract it from process memory.
There are two stages of encryption. Some files, like zipmanifest.xml only use the first one, while gamedb.slt uses both. It's stores in memory in encrypted form after the first stage and is read by chunks of 100 and 1024 bytes.
Sometimes the game modifies the "Schema cookie" field of the header and then re-encrypts the first 40 bytes of the file. So it looks like the executable has an encryption algorithm for the second stage at least.
The file is not compressed, it even has 36 extra bytes, and 16 extra byter per 0x20000 actual bytes.

I uploaded a kind of tutorial on YouTube with the process of extracting this file:
[https://youtu.be/jOIT7nVqjRI](https://youtu.be/jOIT7nVqjRI)

Download link:
[https://mega.nz/folder/btYnBayQ#VVFbwoZ8uxli2xfTmmvadw](https://mega.nz/folder/btYnBayQ#VVFbwoZ8uxli2xfTmmvadw)
## Post #13
- Username: umisery
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 21, 2018 12:17 pm
- Post datetime: 2023-07-15T13:21:15+00:00
- Post Title: Forza Apex  database - gamedb.slt

This is incredible! You reckon it's possible to make the game load the decrypted DB?
## Post #14
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-15T13:44:21+00:00
- Post Title: Forza Apex  database - gamedb.slt

I think no. This encryption method is common for different file type (slt, xml and ini). So I don't think it checks if it's encrypted or not. I also think it's impossible to re-encrypt these files, because there is no reason not to use asymmetric encryption. It may be possible with .dll patch, but I don't know about it.
## Post #15
- Username: umisery
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jan 21, 2018 12:17 pm
- Post datetime: 2023-07-15T14:07:03+00:00
- Post Title: Forza Apex  database - gamedb.slt

Damn, that's sad. It's amazing what you've achieved, but would be awesome if we could get the game to work with the decrypted DB. So far the only game to do so if the developer build of Forza Horizon 3.
## Post #16
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-16T15:26:50+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

> Reply from Doliman100 ↑Sat Jul 15, 2023 9:44 pm at Sat Jul 15, 2023 9:44 pm
>
> 
I think no. This encryption method is common for different file type (slt, xml and ini). So I don't think it checks if it's encrypted or not. I also think it's impossible to re-encrypt these files, because there is no reason not to use asymmetric encryption. It may be possible with .dll patch, but I don't know about it.

do you think we can use this to extract the audio files from the cars? i have tried with the "G_I6TTC_Asian_Street_1_Exh.zip", following the same steps as in your video, and have got no success.

is there any thing that should be done differently?
## Post #17
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-16T18:11:35+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

The tutorial shows a shortcut. I spent some time debugging the executable starting with CreateFile and ReadFile. The main idea is to use Dump breakpoints to follow bytes the game reads from the file.
Note that the audio files are only loaded during gameplay, and not immediately after the executable is launched. So, you need to look at *-Engine.xml file of your current car (for Mitsubishi Lancer Evolution IX MR it is "media\Audio\ModularCars\MIT_LancerEvoIXMR_06-Engine.xml"). Then find any audio file that is mentioned there, for example "G_I4TM_Asian_Street_2_Exh". This file will be loaded some time after you click Continue on the main menu. You can sure this with [Process Monitor](https://download.sysinternals.com/files/ProcessMonitor.zip) application. I attached an example of reading G_I4TM_Asian_Street_2_Exh.zip.
Now, set kernelbase.dll.CreateFileA breakpoint condition to wait for substring "G_I4TM_Asian_Street_2_Exh.zip". Note, that there is kernelbase instead of kernel32. You can click RMB by CreateFile record at Process Monitor > Properties > Stack and find it there.
After that, put a breakpoint on kernelbase.dll.ReadFile without a condition. Now you can have fun from this place.
[Logfile-G_I4TM_Asian_Street_2_Exh.zip](https://xentaxbackup.github.io/file/24077_Logfile-G_I4TM_Asian_Street_2_Exh.zip)
## Post #18
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-16T18:50:05+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

From time to time you can scan the entire memory looking for WAV headers "RIFF" or "WAVEfmt ".

```
findallmem 0x0,"57415645666D74203200000002000100"
```


I also recommend choosing a file that exists in Forza Horizon 3 OpusDev. So you can search for fragments of it or just compare.

```
V10NM_M6E64_Exh.zip
V10NM_M6E64_InL.zip
V10NM_M6E64_InR.zip
V10NM_M6E64_Int.zip
V8NM_SVTRaptor_Eng.zip
V8NM_SVTRaptor_Exh.zip
V8NM_SVTRaptor_InL.zip
V8NM_SVTRaptor_InR.zip
V8NM_SVTRaptor_Int.zip
```


You can look not only at .wav files, but also at any others files that are included in .zip, such as .txt or .dat. The goal is to find a function after which decrypted fragments appear in memory. You can also search for filenames, e.g. "Exh_Acc_V8NM_SVTRaptor.txt".
## Post #19
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-16T19:01:09+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

I Have been able to create the breakpoint, and find when it's loaded, but i am unable to see any recgonizable data..

do you think it's possible for a tutorial video on .zip files? there has been years going into how to obtain the audio files from the game without any success, since horizon 3 came out.

it would be a major help for the modding community, would improve audio quality on many games!
## Post #20
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-17T04:14:55+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

Maybe later this summer. I haven't found a way to extract the audio files yet.
## Post #21
- Username: smurf100
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 30, 2022 4:15 am
- Post datetime: 2023-07-17T16:08:31+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

i appreciate it alot, it would finally place an end to this, now 2 year long quest!

hope that it is possible, thank you for all you have done!
## Post #22
- Username: Doliman100
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Oct 28, 2021 4:17 pm
- Post datetime: 2023-07-17T21:32:13+00:00
- Post Title: Re: Forza Apex  database - gamedb.slt

I posted today's researchers to [[Help] Forza Horizon 4 zip archives](https://forum.xentax.com/viewtopic.php?p=193242#p193242), as this discussion is closer to that topic.
