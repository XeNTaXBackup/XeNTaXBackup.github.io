## Post #1
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-22T21:02:04+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Hey, 
I have several PS2 .CVM files I need to extract, but I can't find anything on how to do this. I spent hours searching the internet for an extractor or other such tool, but I found nothing. Can someone give me a hand? I have tried ISObuster, at the advice of some websites, but it doesn't work for certain games. This file contains the models and data I need to work with, so if anyone can help me get past this obstacle, that would be great. I would post the .CVMs online for people to look at, but they are 550 MB in size, and uploading them wouldn't work.
Thanks,
DarkScion
## Post #2
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2011-01-22T22:05:56+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Try this [http://www.shenmuedojo.net/forum/viewtopic.php?p=868620](http://www.shenmuedojo.net/forum/viewtopic.php?p=868620)
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-01-23T06:39:22+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Each CVM[ROFS] has different version.
What's the Name of the Game?
## Post #4
- Username: NecessAndAry
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 28, 2010 9:51 am
- Post datetime: 2011-01-23T11:31:33+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

DELETED
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-01-24T01:17:55+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

just use ultraiso or winrar. If it doesn't work it's encrypted
## Post #6
- Username: DarkScion
- Rank: veteran
- Number of posts: 82
- Joined date: Sun Dec 05, 2010 10:41 am
- Post datetime: 2011-01-24T15:48:45+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

The game is called Naruto Shippuden: Ultimate Ninja 4... Sorry I didn't respond earlier, for some reason I wasn't recieving notifications of replies in my email. I will check out the link you mentioned, and see if it works.
Thanks,
DarkScion

EDIT:
The CVMs are newer than that program, and are encrypted. The program doesn't work for encrypted CVMs... There must be a program for converting newer .CVM files...
## Post #7
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-01-24T18:11:51+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Unfortunately, as far as I know, no one ever cracked the CVM TOC Encryption
## Post #8
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-08-12T06:20:02+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

I have a work around solution for the encrypted TOC problem in newer ROFS files. I wanted to do some work on Virtual On:MARZ for PS2 but it has one of these encrypted TOC, what a pain. So I ran the game in PCSX2 and made a save state after things got running. I opened the state(they are zip files) and pulled the eeMemory.bin out and opened it in a hex editor. I looked around until I found something that looks like a TOC, naturally the game needs it unencrypted in RAM for it to be used. I found the TOC data but was unable to inject it in to the CVM file properly so I just worked out the entry data, which is very simple, and wrote a really shitty ripper for it. This is definitely working on ROFSROFSBLD Ver.1.43 2002-11-26 files. I didn't take the time to figure out how to tell how many files there are, I just let my crappy ripper run until it reads null entry data after the TOC and then quit. The entry format looks like this:

```
dword null
dword offset	(mult by 0x800 then add 0x1800 to get real offset)
short unk
char *filename	(null padded, not sure how much to pad. I just read until null then read the padding until !null then seek back 1byte)
```
## Post #9
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-08-14T18:22:34+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from ameneko
>
> I have a work around solution for the encrypted TOC problem in newer ROFS files. I wanted to do some work on Virtual On:MARZ for PS2 but it has one of these encrypted TOC, what a pain. So I ran the game in PCSX2 and made a save state after things got running. I opened the state(they are zip files) and pulled the eeMemory.bin out and opened it in a hex editor. I looked around until I found something that looks like a TOC, naturally the game needs it unencrypted in RAM for it to be used. I found the TOC data but was unable to inject it in to the CVM file properly so I just worked out the entry data, which is very simple, and wrote a really shitty ripper for it. This is definitely working on ROFSROFSBLD Ver.1.43 2002-11-26 files. I didn't take the time to figure out how to tell how many files there are, I just let my crappy ripper run until it reads null entry data after the TOC and then quit. The entry format looks like this:
Code: Select alldword size in bytes
dword null
dword offset	(mult by 0x800 then add 0x1800 to get real offset)
short unk
char *filename	(null padded, not sure how much to pad. I just read until null then read the padding until !null then seek back 1byte)
Hi, ameneko
I want to rip the model from the Dennou Senki Virtual-On: Marz PS2[SLPM-65303].
I have a question for you.
Could you show me how this eeMemory.bin file works?
If possible, can you make a bms script to unpacked eeMemory.bin file? or unpack tool ...
[http://www.mediafire.com/file/kkaidock3 ... eMemory.7z](http://www.mediafire.com/file/kkaidock3koic66/eeMemory.7z)
Thanks for your time
## Post #10
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2011-08-29T19:18:27+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

I've been using Apache 3 for .cvm files. It's worked with Tales of the Abyss, Persona 3 FES, Persona 4, and Catherine.
## Post #11
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-08-30T13:19:50+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from oathkeeper9918
>
> I've been using Apache 3 for .cvm files. It's worked with Tales of the Abyss, Persona 3 FES, Persona 4, and Catherine.
It's impossible to open CMV.
## Post #12
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-30T15:51:50+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

How do I extract Naruto Ultimate ninja 5 data.cvm?

It's possible to extract them by changing the format to .iso and cutting off some data with hex editor.
Worked with persona 4 and persona 3 fes, but didn't work for naruto ultimate ninja 5.
## Post #13
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-08-31T09:48:08+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Some, not all, CVM have an encrypted table of contents. My workaround is for those files. I should note that my math is not quite right for calculating the final offset and I'll update as soon as I remember what I did exactly  As for a script/tool to automate it; I could write one to handle the work of extracting once you have the unencrypted TOC or something to patch the TOC into the CVM to make a proper ISO out of it in some cases. I'm not sure that you can automate extracting the unencrypted TOC from the eeMemory.bin and I'm not really interested in doing so. When I get a chance I suppose I can write up some decent instructions on how to do this manually with a hex editor, it isn't difficult.
## Post #14
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2011-10-16T19:42:42+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

I would like to extract the video+audio files from Sakura Wars on PS2, but it uses a encrypted CVM file, has anyone figured out a way on how to do this ? i did have a look at the TOC in eeMemory.bin and try to calculate the address's but i had no luck (either i messed up or have misunderstood the method or maybe that method doesn't work for this game) here is a picture of my eeMemory.bin TOC of the file i want to extract highlighted in black
[](http://imageshack.us/photo/my-images/695/hexl.png/)
## Post #15
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-08-19T07:29:27+00:00
- Post Title: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from ddkram
>
> I would like to extract the video+audio files from Sakura Wars on PS2
That Sakura Wars game is made by Sega Wow Overworks, who used CVM container for all their PS2 games. 
And just like in other cases some of them are encrypted while others are not. Shinobi (PS2) for example was non-encrypted and can be oped with Ultra iso, while its sequel Kunoichi was encrypted.
## Post #16
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-08-25T11:14:35+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from MiLØ
>
> 
That Sakura Wars game is made by Sega Wow Overworks, who used CVM container for all their PS2 games. 
And just like in other cases some of them are encrypted while others are not. Shinobi (PS2) for example was non-encrypted and can be oped with Ultra iso, while its sequel Kunoichi was encrypted.
Thanks for the information, i did try UltraISO and a few other ISO programs on this but since it doesn't have a TOC none of them worked, but it can be extracted using the method posted by ameneko (i was just doing it wrong last time) which was useful for some files, but some of the files i extract appear to be encrypted some how, for example the movies are in a SFC format which appears to be a encrypted version of SFD video format so i now need to work out how to decode these encrypted files (which i have no idea how to do since i can't find any info on this format anywhere so it may have only been used on this game)
## Post #17
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-08-28T05:58:38+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from ddkram
>
> Thanks for the information, i did try UltraISO and a few other ISO programs on this but since it doesn't have a TOC none of them worked, but it can be extracted using the method posted by ameneko (i was just doing it wrong last time) which was useful for some files, but some of the files i extract appear to be encrypted some how, for example the movies are in a SFC format which appears to be a encrypted version of SFD video format so i now need to work out how to decode these encrypted files (which i have no idea how to do since i can't find any info on this format anywhere so it may have only been used on this game)
Oh I actually didn't get it myself what was the method that ameneko used.

Is there some kind of guide on how to dump PS2 games ram?
## Post #18
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-08-28T12:03:38+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from MiLØ
>
> 
Oh I actually didn't get it myself what was the method that ameneko used.

Is there some kind of guide on how to dump PS2 games ram?
There isn't any sort of guide, all you have to do is run the game in a emulator called PCSX2 which can be gotten from [www.pcsx2.net](http://www.pcsx2.net) and while the game is running make a Save State (basicly a memory dump) and then close Pcsx2 and then open the save state file in any program that can open zip files and extract eeMemory.bin and if you look inside eeMemory.bin with a hex editor you will see the TOC for where the files are inside the CVM (you then need to multiply it by 0x800 then add 0x1800 in hex to get the exact location).
## Post #19
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-08-28T19:19:10+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from ddkram
>
> There isn't any sort of guide, all you have to do is run the game in a emulator called PCSX2 which can be gotten from http://www.pcsx2.net and while the game is running make a Save State (basicly a memory dump) and then close Pcsx2 and then open the save state file in any program that can open zip files and extract eeMemory.bin and if you look inside eeMemory.bin with a hex editor you will see the TOC for where the files are inside the CVM (you then need to multiply it by 0x800 then add 0x1800 in hex to get the exact location).
That's what I was hoping it it would not involve - working with the hex editor. This type of stuff is just too hardcore and I got no necessary skills or knowledge. 
But thanks for explanation.
## Post #20
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-28T19:47:06+00:00
- Post Title: Re: PS2 .CVM archive extraction

its very simple
just copy paste thats all then its a normal iso file you can read with anything.
## Post #21
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-08-30T11:08:40+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> its very simple
just copy paste thats all then its a normal iso file you can read with anything.
On a normal CVM that works fine but a encrypted CVM is different, it has a encrypted TOC so no program (released publicly to date) can read it.
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-30T11:46:53+00:00
- Post Title: Re: PS2 .CVM archive extraction

that's why you paste in the toc from the save state.
## Post #23
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-08-30T12:53:29+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> that's why you paste in the toc from the save state.
I have tried to paste the TOC from the save state but not had much luck (i could be doing something wrong though), can you show me any examples on how to do it ? because everytime i try i get a corrupt ISO (meaning it shows a few files with gibberish names and wrong filesize's) but to me it looks like the start of the TOC is missing from the savestate (again this could just be me) which includes the folder information and disc label.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-30T21:31:36+00:00
- Post Title: Re: PS2 .CVM archive extraction

just pm me the encryptesd header of the cvm and the save state
and ill send you the proper iso header
## Post #25
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-08-31T10:10:44+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> just pm me the encryptesd header of the cvm and the save state
and ill send you the proper iso header
I desperately need your help.
Could you please check PM.
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-31T20:19:30+00:00
- Post Title: Re: PS2 .CVM archive extraction

here is the quickbms to extract the file you sent me.
I assume its naruto?

so this is virtual on
[naruto.rar](https://xentaxbackup.github.io/file/5733_naruto.rar)
## Post #27
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-08-31T20:40:58+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> just pm me the encryptesd header of the cvm and the save state
and ill send you the proper iso header
Ok i am uploading now and i will send you a PM with a link in a moment, the zip i am sending will have the first 17MB (the number of MB was just random number) of the encrypted CVM and a pcsx2 save state. Any help is very much appreciated.
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-31T23:01:59+00:00
- Post Title: Re: PS2 .CVM archive extraction

what game are you sending?
## Post #29
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-09-01T06:29:50+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> what game are you sending?
well i made the zip i sent the same name of the game but the games full name is "Sakura Wars 5 So Long, My Love"
## Post #30
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-01T09:01:37+00:00
- Post Title: Re: PS2 .CVM archive extraction

> Reply from chrrox
>
> here is the quickbms to extract the file you sent me.
I assume its naruto?
No,	
I'm sure it's Virtual-On.
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-01T11:26:36+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

here is for Sakura Wars 5 So Long, My Love
[sakura.7z](https://xentaxbackup.github.io/file/5738_sakura.7z)
## Post #32
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-01T12:14:23+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from ddkram
>
> chrrox wrote:what game are you sending?
well i made the zip i sent the same name of the game but the games full name is "Sakura Wars 5 So Long, My Love"
Could I know "Sakura Wars 5 So Long, My Love"'s  Product ID?
SLPM-67009 Product ID failed to extract cvm.
## Post #33
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-01T12:44:29+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

SLUS-21930
[http://www.gamefaqs.com/ps2/561890-saku ... -love/data](http://www.gamefaqs.com/ps2/561890-sakura-wars-so-long-my-love/data)
show the error you get also.
## Post #34
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-01T13:23:42+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from chrrox
>
> SLUS-21930
http://www.gamefaqs.com/ps2/561890-saku ... -love/data
show the error you get also.
An error message

And, data looks really strange.

If you want, I can send you the cut file.
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-01T14:36:04+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

ill need a big sample of the cvm and the memory dump the versions might be different.
## Post #36
- Username: ddkram
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 17, 2011 3:26 am
- Post datetime: 2012-09-01T16:04:56+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

I forgot to mention mine was from the premium edition NTSC-U (the game comes with 2 discs, 1 has English audio the other has Japanese, my files where from the jap audio disc since i wanted to extract the files from the jap disc) so this could be the reason why our dumps are different.
Anyway thanks for the BMS chrrox, i am extracting now and so far everything is looking good .
## Post #37
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-01T16:22:24+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

here is the other bms for the same game should work on your file now.
[sakura2.7z](https://xentaxbackup.github.io/file/5741_sakura2.7z)
## Post #38
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-09-01T16:47:00+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from chrrox
>
> here is the other bms for the same game should work on your file now.
Thank you very much for your bms script.
## Post #39
- Username: Gromber
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Oct 06, 2010 4:42 am
- Post datetime: 2012-11-20T19:32:33+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

yakuza 1/2  .cvm solution?
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-20T20:41:09+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

if they are encryted i need a save state and a sample from the start of the iso.
## Post #41
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2014-03-05T08:31:42+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Please, help extract cvm. All files in archive. [http://yadi.sk/d/3tSOnSFrJtGW2](http://yadi.sk/d/3tSOnSFrJtGW2)
## Post #42
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2014-03-08T20:24:38+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Up.
## Post #43
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-06-30T08:01:33+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from ameneko
>
> I have a work around solution for the encrypted TOC problem in newer ROFS files. I wanted to do some work on Virtual On:MARZ for PS2 but it has one of these encrypted TOC, what a pain. So I ran the game in PCSX2 and made a save state after things got running. I opened the state(they are zip files) and pulled the eeMemory.bin out and opened it in a hex editor. I looked around until I found something that looks like a TOC, naturally the game needs it unencrypted in RAM for it to be used.
> Reply from ddkram
>
> all you have to do is run the game in a emulator called PCSX2 which can be gotten from http://www.pcsx2.net and while the game is running make a Save State (basicly a memory dump) and then close Pcsx2 and then open the save state file in any program that can open zip files and extract eeMemory.bin and if you look inside eeMemory.bin with a hex editor you will see the TOC for where the files are inside the CVM (you then need to multiply it by 0x800 then add 0x1800 in hex to get the exact location).
> Reply from chrrox
>
> its very simple
just copy paste thats all then its a normal iso file you can read with anything.

Ok can someone help me with this method extracting CVM? It would be really really great because I tried and just get stuck on these simplest steps which are suppose to be so easy. 

So the game is Nightshade (PS2) by Sega. 

I created a save state in PCSX2, looked inside eeMemory.bin for TOC, found it. It starts at 00D3A2C0, because the next thing after zeroes is where it starts, right? I'm a total noob.



The end of TOC is at 00D4B063. 

Aaand that's that's where I get stuck. The next step is suppose to be "multiply it by 0x800" and "then add 0x1800 in hex to get the exact location". So multiply what? Do I select a block using the start & end offset and then multiply the whole thing on 0x800? And how to multiply? HxD doesn't have this function, so I tried Hex Workshop > Data Operations > Multiply... but it doesn't let me enter 0x800 as a value to be multiply on. So am I even attempting the right thing?



And what would be the next step?... sorry for all these noobish questions but I could really use an advise from someone who has done this thing before and can give exact instructions for these several steps, steps for dummies so to speak because otherwise the vague instructions aimed at someone who already knows what they're doing with hexing, make no sense to me.

Here's a save state: 
[https://mega.co.nz/#!koVF3bZR!PDJm1VrLx ... vcaOwo_J7Y](https://mega.co.nz/#!koVF3bZR!PDJm1VrLx2FDHtBkYeNn_Ch7raEbtL8xTvcaOwo_J7Y)

And here's the first+last 10 MB of ROFSSMP.CVM, from Nightshade's ISO if it might be useful. Was cut with Watoo File Cutter. 
[https://mega.co.nz/#!5g1XmQbY!FmImsCyxo ... VPyPZgNnas](https://mega.co.nz/#!5g1XmQbY!FmImsCyxopHFo8r27Le75yTX9eY67W_9gVPyPZgNnas)
## Post #44
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-07-07T12:33:16+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Bump.
## Post #45
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2014-07-15T04:11:34+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

Bump²
## Post #46
- Username: zetper
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 23, 2014 2:39 am
- Post datetime: 2016-08-06T20:12:27+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

> Reply from MiLØ
>
> Bump²
Нello MiLØ command to unpack the .CVM from the game Nightshade [SLUS-20810] Region: NTSC
cvm_tool.exe split -p PJ234110 ROFSSMP.CVM ROFSSMP.iso ROFSSMP.hdr
the program cvm_tool_02.zip here [viewtopic.php?f=21&t=2776&hilit](http://forum.xentax.com/viewtopic.php?f=21&t=2776&hilit)
## Post #47
- Username: nexxusdrako
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 05, 2018 11:56 pm
- Post datetime: 2019-05-11T10:44:33+00:00
- Post Title: Re: (PS2) Naruto Shippuden: Ultimate Ninja 4 .CVM

I hate to necro an old thread but I'm currently trying to work with an old PS2 game named Let's Make A Soccer Team that uses the same ROFS/CVM encryption. I can send the first 30MB of the CVM and the save state's eeMemory.bin if need be. Let me know if any of you are willing.
