## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-23T23:43:25+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Here is a quickbms script to extract all files from the ps3 version with full names.
Update Noesis to the latest version to load the models.
If animations look wrong it is because it is the wrong model to go with those animations.

[FF13-LR.7z](https://xentaxbackup.github.io/file/6794_FF13-LR.7z)
## Post #2
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2013-11-25T04:24:24+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Can be used in the Xbox360?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-25T04:39:26+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I have not bothered to dump the file table from memory on the 360 version.
If someone wants to send me a memory dump i can add it.
## Post #4
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-25T16:27:16+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I wrote a suite that decrypts the file table directly for both ps3 and xbox360.  I'm going to release it soon when I finish up the trb format.

Atm, you can extract, mod, and completely rebuild the white data for all 3 games in the series.
## Post #5
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-11-26T02:09:29+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

> Reply from EcheloCross
>
> I wrote a suite that decrypts the file table directly for both ps3 and xbox360.  I'm going to release it soon when I finish up the trb format.

Atm, you can extract, mod, and completely rebuild the white data for all 3 games in the series.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-26T02:20:59+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Whatever you do, don't share your info with chrrox, and hurry before anyone else bothers spending an hour or 2 to figure it out themselves. You alone deserve credit for all of the forthcoming nude mods. God speed, my son.
## Post #7
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-26T03:38:00+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I'm sensing a bit of non like for graphics mods.  Sorry if I offended anyone.
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-26T08:12:36+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Your senses are a bit off the mark there. I was mocking the fact that you're withholding information that could be trivially obtained with a few moments of live debugging, but which would save anyone else who cared the effort and would demonstrably assist chrrox's existing effort. The apparent conclusion is that receiving exclusive honors for all of the forthcoming nude mods must be very important to you.
## Post #9
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-26T15:09:08+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I could give a @#$% less about credit for nude mods.  Stop trying to get all intellectual on me.
You can mod much more than graphics too.  The battle database, ai, items, weapons.

chrrox, info is sent.

MrAdults, will you post some detailed info about the trb format's SEDBWRB blocks, and SEDBSKL blocks?



General question...

Is it ok to post a tool that contains the decryption keys?
## Post #10
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-11-26T15:28:24+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I have a question about that, do you think it would be possible to port Lightning's costumes from XIII-2/LR to the original XIII?

Also, would it be possible to port Serah and Noel over say Sazh and Snow if you copied all the models, voices and animations? It would be glitchy and weird, but cool
## Post #11
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-26T15:47:15+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I haven't tried replacing xiii-1 data with any newer data yet.  I do know that in xiii-2, you can load different models by replacing the trb and imgb, then changing the some of the references in the trb to the original character's id.

example:

c201 = lightning, m001 = red dog monster

replace c201.x360.trb and c201.x360.imgb with m001.x360.trb and m001.x360.imgb, (rename the m001 ones to c201)
Edit most references in m001.x360.trb from m001 to c201.  If you edit all references, it will break the skeleton.   

For models like serah in xiii-2 though they have the same skeleton, so you can edit all references and get her original costume for in-game play.
## Post #12
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-11-26T16:16:16+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Against my better judgement......
If nothing else you can print the code out, make paper airplanes, and fly dog turds into your neighbors' kid's hair.

[](https://skydrive.live.com/redir?resid=5563CAB21EADBF2%21521)
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-26T17:18:09+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

I already did, quite a few years ago. You can try to track that down, or just go steal nohbdy's code from the FF14 dat digger. The format is the same. He also handles anims, which I never did, that is where both TheDude and I got the specs. [https://github.com/nohbdy/ffxivmodelvie ... aster/src/](https://github.com/nohbdy/ffxivmodelviewer/blob/master/src/)
## Post #14
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-26T18:15:53+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

Thanks for the link.  I have the info you posted years ago when xiii-1 came out.  It has helped quite a bit for the binary template I made.  I was just hoping you may have some more info to add to that, or even the sections of source code used in Noesis that relate to final fantasy.  It would help people out greatly to be able to see the source it uses.  Probably would have saved me a lot of time in the past few years too.
## Post #15
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-11-26T19:17:16+00:00
- Post Title: Final Fantasy 13 Lightning Returns (JAP)

There's a link embedded in that image above.
Just wanted to throw that out there...
Not sure if anyone got that.
## Post #16
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-11-26T20:54:18+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Thanks for the link TheDude.

Here is the crypto tool.  Its been updated to work for all resources now, besides ps3 save data.

```
-d <filename> 1 - Decrypts a save for ffxiii-1.
-e <filename> 1 - Encrypts a save for ffxiii-1.
-d <filename> 2 - Decrypts a save or a filelist for ffxiii-2.
-e <filename> 2 - Encrypts a save or a filelist for ffxiii-2.
-d <filename> 3 - Decrypts a save or a filelist for ffxiii-3.
-e <filename> 3 - Encrypts a save or a filelist for ffxiii-3.
-d <filename> S - Decrypts a script (.clb) for any game in the series.
-e <filename> S - Encrypts a script (.clb) for any game in the series.

```


Enjoy.
[ffxiiicrypt.zip](https://xentaxbackup.github.io/file/6828_ffxiiicrypt.zip)
## Post #17
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2013-11-27T03:05:01+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Where to download 3dmax Script
## Post #18
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-27T03:48:11+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from qq99q1
>
> Where to download 3dmax Script

Errrmmm... there's no maxscript for importing models, but there's something called noesis that supports all the three FFXIII from both consoles:

[http://oasis.xentax.com/](http://oasis.xentax.com/)

And you can export it to whatever you want.
## Post #19
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2013-11-28T02:19:58+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Noesis can't do mods
## Post #20
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-11-28T05:40:45+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Thanks for the script chrrox. Glad to extract cutscenes properly.
## Post #21
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-11-29T12:59:06+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I keep getting errors when extracting from white_img2.ps3 and white_img.ps3. It'll extract so much, then give me 2 errors:

Error: The compressed zlib/deflate input is wrong or incomplete <-3>

Error: There is an error with the decompression the returned output size is negative <-1>

I'm using quickbms 0.5.28.
## Post #22
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2013-11-30T20:17:02+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I got those errors as well with the latest quickbms, but it appears to have still pulled a bunch of the files.  But for img and img2 it returned different negative values...
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-30T21:51:12+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

The script has been tested on all files you will have to show me your command line to see whats going on.
this is only for the japanese ps3 release.
## Post #24
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-12-05T21:49:49+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Turns out I had the Asia version, not the japanese one. The one that's needed is BLJM60558, not BCAS20279. Managed to get it to extract now though 

Does this work on the DLC too?
## Post #25
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-12-06T01:07:25+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Just use Noesis for decryption+extraction, it handles all regions (including DLC) without the need for the giant silly series of filename compares you'll notice if you disassemble ff13crypt.exe.  It also auto-decrypts the .clb files.
## Post #26
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2013-12-06T04:28:52+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

ff13crypt -d white_p0000013img_c.ps3.bin 3 
Cannot extract dlc
## Post #27
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-06T05:11:15+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from qq99q1
>
> ff13crypt -d white_p0000013img_c.ps3.bin 3 
Cannot extract dlc

Noesis decripted the first FFXIII LR nicely.
## Post #28
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2013-12-07T21:18:35+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from MrAdults
>
> Just use Noesis for decryption+extraction, it handles all regions (including DLC) without the need for the giant silly series of filename compares you'll notice if you disassemble ff13crypt.exe.  It also auto-decrypts the .clb files.

The silly compares have been removed.  filelists and clb are now decrypted and encrypted by parsing their header like it should have been in the first place.  I'll update the tool in the post in a few.

I didn't know noesis did any decryption.  Was that added in v4.091?
## Post #29
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-12-07T22:19:36+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Full extraction of XIII-2 as well, nice  

It's kinda cool watching XIII-2 Hope use XIII-1's animations.
## Post #30
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2013-12-09T14:23:41+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I only have x360 iso. After extracting iso file, i got x360.bin files.

Someone can help me create quickbms for xbox360 file version ? (i dont have any coding or hexing skills)

Thank in advanced.
## Post #31
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-09T15:58:43+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

bms for what??
## Post #32
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2013-12-09T16:23:49+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from Darko
>
> bms for what??

bms for extract .trb and .bin from white_img.x360.bin or white_img2.x360.bin.

Chrox only share bms script for ps3 .bin files.
## Post #33
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2013-12-09T16:28:51+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Try noesis then, click on the filelists.
## Post #34
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-12-09T16:46:23+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from goder2910
>
> Darko wrote:bms for what??

bms for extract .trb and .bin from white_img.x360.bin or white_img2.x360.bin.

Chrox only share bms script for ps3 .bin files.
 Did you read the whole thread?? Rich said Noesis can unpack now lightning returns files.
## Post #35
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2013-12-10T01:16:54+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Below is my steps:

- Extract .bin file from x360 iso
- After that , i get bunch of .bin file like white.image.x360.bin, white.image2.x360.bin, ..v..v.
- Then, i click on extracted filelist.x360.bin file
- Choose white.image.x360.bin
- Voila, ton of .trb file is extracted.

My fault is just click on white.image.x360.bin.

Thank ultimaespio, Darko.
## Post #36
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-12-26T21:25:55+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

noesis always crash when i tried to extract white_z0100_img.x360.bin (and the rest of the file that contain white_zxxxx_img.x360.bin name) other than that its extract fine

BTW im using JAP demo version,any suggestion???
## Post #37
- Username: akasha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 10, 2014 5:22 am
- Post datetime: 2014-01-11T03:03:14+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from aagems
>
> noesis always crash when i tried to extract white_z0100_img.x360.bin (and the rest of the file that contain white_zxxxx_img.x360.bin name) other than that its extract fine

BTW im using JAP demo version,any suggestion???

I could find the filelists for the zone files in white_img2c.ps3.bin, in the zone folder. Maybe that is also the location for your demo version.
## Post #38
- Username: akasha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 10, 2014 5:22 am
- Post datetime: 2014-01-12T02:54:54+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I extracted both white_img and white_img2.ps3.bin, but I couldn't find any npc characters (though I found monsters, weapons and summon model files)..
Does anyone know where npc models are?
## Post #39
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2014-01-14T16:30:47+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from akasha
>
> I extracted both white_img and white_img2.ps3.bin, but I couldn't find any npc characters (though I found monsters, weapons and summon model files)..
Does anyone know where npc models are?

They're in the z0100 bin.  

n921 <-- from z0100


n930 <-- from z0100


m383 <-- from img
## Post #40
- Username: akasha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 10, 2014 5:22 am
- Post datetime: 2014-01-19T17:26:32+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from EcheloCross
>
> akasha wrote:I extracted both white_img and white_img2.ps3.bin, but I couldn't find any npc characters (though I found monsters, weapons and summon model files)..
Does anyone know where npc models are?

They're in the z0100 bin.  

n921 <-- from z0100


n930 <-- from z0100


m383 <-- from img

Thanks!!   
Hm, I expected to find Bhunivelze's model with the NPCs, but no luck  where's god??   
Also, sorry being the annoying n00b brat, but do anyone know if there's a way to port some model's animation to be used with another character? attempting to just load them swapped ended up in some really ugly mess...
I'd like to learn more about how to access and use the animation data and effects, too If someone has any hint or know anywhere I can look up, the info would be greatly appreciated!
## Post #41
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-01-19T17:32:38+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I've been having a look through the DLCs, and there doesn't seem to be any victory animations in there. It's just Idle/jumping/running animations.
## Post #42
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2014-02-14T08:47:53+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

how do i extract from white_z0100e_img.ps3.bin file in zone folder?  I tried bms script but it doesnt extract.  and noesis gives me error too.  there is no filelist in zone folder.  i have BLES01811 version.  any help?
## Post #43
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-02-25T11:18:21+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from khanbot
>
> how do i extract from white_z0100e_img.ps3.bin file in zone folder?  I tried bms script but it doesnt extract.  and noesis gives me error too.  there is no filelist in zone folder.  i have BLES01811 version.  any help?

Hi.

Was anyone able to figure this out at all? Having no luck here.
## Post #44
- Username: timshundo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 28, 2014 12:18 pm
- Post datetime: 2014-02-28T10:55:41+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from lionheartuk
>
> khanbot wrote:how do i extract from white_z0100e_img.ps3.bin file in zone folder?  I tried bms script but it doesnt extract.  and noesis gives me error too.  there is no filelist in zone folder.  i have BLES01811 version.  any help?

Hi.

Was anyone able to figure this out at all? Having no luck here.

Because, like me, we have the US version of the disc, denoted by the "e" after z0100 in the filename. I'm on a quest to extract a bunch of sound effects from the english version and the bms script posted here isn't going to work.

Is there any chance we could get a version of the script that works on english version files/ is there a way i can make the script myself?

Thanks!
## Post #45
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2014-02-28T11:04:24+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from timshundo
>
> 
Because, like me, we have the US version of the disc, denoted by the "e" after z0100 in the filename. I'm on a quest to extract a bunch of sound effects from the english version and the bms script posted here isn't going to work.

Is there any chance we could get a version of the script that works on english version files/ is there a way i can make the script myself?

Thanks!

I have the ES version of the disk and Noesis extract this file correctly. It's simple, download the last version of Noesis. Go to folder where you copy the files from the disk. Open filelist or fileliste with double-click, click in the new window click in extract, and in the new dialog select the file z0100. (If you slect filelist select the z0100 file without "e" and if you select fileliste select the z0100 file with "e")

Sorry for my bad english.
## Post #46
- Username: timshundo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 28, 2014 12:18 pm
- Post datetime: 2014-03-03T10:29:23+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from gokuhs
>
> timshundo wrote:
Because, like me, we have the US version of the disc, denoted by the "e" after z0100 in the filename. I'm on a quest to extract a bunch of sound effects from the english version and the bms script posted here isn't going to work.

Is there any chance we could get a version of the script that works on english version files/ is there a way i can make the script myself?

Thanks! 

I have the ES version of the disk and Noesis extract this file correctly. It's simple, download the last version of Noesis. Go to folder where you copy the files from the disk. Open filelist or fileliste with double-click, click in the new window click in extract, and in the new dialog select the file z0100. (If you slect filelist select the z0100 file without "e" and if you select fileliste select the z0100 file with "e")

Sorry for my bad english.

Sorry, to be more specific: Noesis opens the z0100 files with corresponding filelist files correctly which is where the char models are, but the files i want to extract are in the zone folder which won't open through Noesis and only can be opened with a quickbms script.

I'm trying to get to music/sound/voiceover files so the bins that Noesis has the ability to open on it's own doesn't help me.

Hope that makes sense.  Any help would be so appreciated guys!
## Post #47
- Username: timshundo
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-03-04T01:45:45+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Noesis has no problem extracting zone archives, you just need to correlate the right filelist bin with the right data bin for the zone.
## Post #48
- Username: timshundo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 28, 2014 12:18 pm
- Post datetime: 2014-03-04T11:13:19+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from MrAdults
>
> Noesis has no problem extracting zone archives, you just need to correlate the right filelist bin with the right data bin for the zone.

Ah you're totally right. I don't know how I missed those filelists before.

Thanks!
## Post #49
- Username: timshundo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 28, 2014 12:18 pm
- Post datetime: 2014-03-04T12:55:12+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Hate to be a bother but:

So I've extracted most of the sound files which is awesome. Most of them are .ps3.scd audio files which if renamed to .mp3 play just fine.

The issue I'm having though are that some files, mainly the ones I want, are bundled in ".ps3.wpd" files. They're in the same folders as the other sound files but unreadable by anything my noob ass throws at them. The headers are readable and clearly spell out the file names of the SCD files that are bundled within:

ft_hope_.ps3.wpd

> WPD
>
> ft_hope_gs0Är@scdft_hope_ic0tQ@scdft_hope_ir0≈ÄE@scdft_hope_ir1h@scdft_hope_ir2sÄW@scdft_hope_sd0ÀÖ¿scdft_hope_sl0QR¿scdft_hope_sl1§o¿scdft_hope_st0=¿scdft_hope_wd0RK¿scdSEDBSSCF

Could someone take a look at the file and help me out? Sample WPD attached.

Thanks!
[ft_hope_.ps3.wpd.zip](https://xentaxbackup.github.io/file/7069_ft_hope_.ps3.wpd.zip)
## Post #50
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2014-03-04T13:01:00+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

The sound files in the WPD files are usually just the same as what's in the individual ones, just packaged together. If you get VGMstream you can play the WPD versions.
## Post #51
- Username: timshundo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 28, 2014 12:18 pm
- Post datetime: 2014-03-04T20:23:05+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from ultimaespio
>
> The sound files in the WPD files are usually just the same as what's in the individual ones, just packaged together. If you get VGMstream you can play the WPD versions.

Right, I figured. My question is how do I unpack those sound files from the WPD? I can't get vgmstream to do anything with the wpd.
## Post #52
- Username: gokuhs
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Jul 10, 2012 4:02 pm
- Post datetime: 2014-03-05T07:22:21+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from timshundo
>
> Right, I figured. My question is how do I unpack those sound files from the WPD? I can't get vgmstream to do anything with the wpd.

I have the same problem.
## Post #53
- Username: COKEORPEPSI50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu May 24, 2012 11:31 am
- Post datetime: 2014-03-14T00:27:49+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I've been trying to extract audio from XIII and XIII-2 from files in the Zone folder, but I've been unsuccessful.
## Post #54
- Username: cippyboy
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Sep 27, 2007 3:49 am
- Post datetime: 2014-04-03T14:48:16+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Posting here cause it's been like 2 years since I worked on this but I just wanted to post the code to extract FFXIII/FFXIII-2 (maybe LR too) TRB model files and convert them to .FBX .

I did almost the exact same work the Noesis tool does because hey, whoever owns that or other tools just doesn't want to share any source code.
[FFXIII TRB Extractor.zip](https://xentaxbackup.github.io/file/7169_FFXIII TRB Extractor.zip)
## Post #55
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-04-10T07:48:03+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Sorry to rain on your parade, but code for the Noesis FF13 loader has been all over the internet and pastebins for the last several years. Not to mention nohbdy's code repository.

Edit: Here, 2 seconds of googling: [https://github.com/nohbdy/ffxivmodelvie ... master/src](https://github.com/nohbdy/ffxivmodelviewer/tree/master/src)
Everything you could possibly want regarding specs, source, and handling of all kinds of data types including geometry and animation. Open Source Jesus appreciates the martyrdom nonetheless.
## Post #56
- Username: amandabyyy
- Rank: beginner
- Number of posts: 22
- Joined date: Mon May 31, 2010 3:08 pm
- Post datetime: 2014-07-08T22:08:01+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I'm trying to use the latest Noesis to extract the zone files with the file lists.  It crashes when I try to extract z0100.  Sounds extract fine.  Does anyone else have the same problem?  Is there a way I could get an older Noesis?
## Post #57
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2014-07-22T05:09:02+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from MrAdults
>
> Sorry to rain on your parade, but code for the Noesis FF13 loader has been all over the internet and pastebins for the last several years. Not to mention nohbdy's code repository.

Edit: Here, 2 seconds of googling: https://github.com/nohbdy/ffxivmodelvie ... master/src
Everything you could possibly want regarding specs, source, and handling of all kinds of data types including geometry and animation. Open Source Jesus appreciates the martyrdom nonetheless.
That's the FFXIV model viewer. Final Fantasy 13 is FFXIII. Do they use the same format?
## Post #58
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2014-07-22T15:35:45+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

FFXIV originally used the same format.
Then, when they remade it, they made it better, more dynamic, more..... synergistic and able to cope with the increasing demands of a lonely planet spinning its way toward damnation amid the fear and despair of a broken human race.But who is left to fight for all that is good and pure and gets you smashed for under a fiver? Yes, it's the surprising adventures of me, Sir Digby Chicken-Caesar.
## Post #59
- Username: SuperShadic2017
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 8:50 am
- Post datetime: 2014-12-24T22:15:23+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

I'm trying to export the .x360 files from the xbox 360 version (obviously). I'm running into trouble when opening them in noesis. Only the filelists can be opened at all, and when I try to export them, it has "Error: Cannot write '[FILE]', bad offset." for a ton of files. I have the x360 extension checked in the assosiactions, but it still doesn't work. I've followed this thread and I saw some people got 360 to work. Do I need to resort to the PS3 version?
## Post #60
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2015-01-17T18:04:09+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Did you try QuickBMS?
## Post #61
- Username: kiraepyon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 04, 2015 9:36 am
- Post datetime: 2015-07-11T12:21:47+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

First, I would like to thank for the work you had to produce these extractors.

Second, if possible, I would like help, because I am unable to extract the JP version of the file with the QuickBMS (get the message Error: in this MEMORY_FILE script has not Been used / declared yet).

Also, I can not use the extractor made by Echelo (the program automatically closes soon after opening), and Noesis crashes when I try to open something to extract.

Someone could direct me to correct my mistake?

Thanks for listening!
## Post #62
- Username: rainhawk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 10, 2015 1:28 am
- Post datetime: 2015-11-28T06:03:09+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

Almost feels like I'm dragging this thread up from the grave... But does anybody know where the buildings and environments are? I seem to have found characters and weapons and stuff like that. Are they in a different location?
## Post #63
- Username: peronmls
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 05, 2011 6:21 am
- Post datetime: 2020-08-19T01:21:44+00:00
- Post Title: Re: Final Fantasy 13 Lightning Returns (JAP)

> Reply from EcheloCross ↑Wed Nov 27, 2013 4:54 am at Wed Nov 27, 2013 4:54 am
>
> 
Thanks for the link TheDude.

Here is the crypto tool.  Its been updated to work for all resources now, besides ps3 save data.
Code: Select allUsage:
-d <filename> 1 - Decrypts a save for ffxiii-1.
-e <filename> 1 - Encrypts a save for ffxiii-1.
-d <filename> 2 - Decrypts a save or a filelist for ffxiii-2.
-e <filename> 2 - Encrypts a save or a filelist for ffxiii-2.
-d <filename> 3 - Decrypts a save or a filelist for ffxiii-3.
-e <filename> 3 - Encrypts a save or a filelist for ffxiii-3.
-d <filename> S - Decrypts a script (.clb) for any game in the series.
-e <filename> S - Encrypts a script (.clb) for any game in the series.


Enjoy.

It fails to decrypt filelistu.win32.bin and filelistc.win32.bin every time. I tried setting it to FF13 and FF132 and get the same issue. Why?
